---
title: Übersicht über EventPipe
description: Hier erfahren Sie mehr über EventPipe und die Verwendung dieser Komponente für die Ablaufverfolgung von .NET-Anwendungen, um Leistungsprobleme diagnostizieren zu können.
ms.date: 11/09/2020
ms.topic: overview
ms.openlocfilehash: 00378c4f409b307afa9183e40de6078cdafd3ae7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820617"
---
# <a name="eventpipe"></a>EventPipe

EventPipe ist eine Runtimekomponente, die wie ETW oder LTTng zum Erfassen von Ablaufverfolgungsdaten verwendet werden kann. EventPipe soll es .NET-Entwicklern ermöglichen, die Aktivitäten ihrer .NET-Anwendungen problemlos nachverfolgen zu können, ohne sich dabei auf plattformspezifische und betriebssystemnative Komponenten wie ETW oder LTTng verlassen zu müssen.

EventPipe ist der Mechanismus hinter vielen der Diagnosetools und kann zum Verarbeiten von Ereignissen, die von der Runtime ausgegeben werden, sowie von benutzerdefinierten Ereignissen verwendet werden, die mit [EventSource](xref:System.Diagnostics.Tracing.EventSource) geschrieben wurden.

Dieser Artikel bietet eine allgemeine Übersicht über EventPipe, und es wird beschrieben, wann und wie EventPipe verwendet werden sollte und wie die Komponente Ihren Anforderungen entsprechend konfiguriert werden kann.

## <a name="eventpipe-basics"></a>EventPipe-Grundlagen

EventPipe aggregiert Ereignisse, die von Runtimekomponenten (z. B. Just-In-Time-Compiler oder Garbage Collector) ausgegeben werden, und Ereignisse, die aus [EventSource](xref:System.Diagnostics.Tracing.EventSource)-Instanzen in den Bibliotheken und im Benutzercode geschrieben werden.

Die Ereignisse werden dann serialisiert und können direkt in eine Datei geschrieben oder über einen prozessexternen Diagnoseport genutzt werden. Unter Windows werden Diagnoseports als `NamedPipe`s implementiert. Auf Nicht-Windows-Plattformen wie Linux oder macOS werden sie mithilfe von Unix Domain Sockets implementiert. Weitere Informationen zum Diagnoseport und die Interaktion mit diesem über das benutzerdefinierte, prozessübergreifende Kommunikationsprotokoll finden Sie in der [Dokumentation zum IPC-Diagnoseprotokoll](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md).

EventPipe schreibt die serialisierten Ereignisse dann im `.nettrace`-Dateiformat entweder als Stream über die Diagnoseports oder direkt in eine Datei. Weitere Informationen zum EventPipe-Serialisierungsformat finden Sie in der [Dokumentation zum EventPipe-Format](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md).

## <a name="eventpipe-vs-etwlttng"></a>EventPipe im Vergleich zu ETW/LTTng

EventPipe ist Teil der .NET-Runtime (CoreCLR) und so konzipiert, dass diese Komponente auf allen Plattformen, die .NET Core unterstützt, auf dieselbe Weise funktioniert. Dadurch können auf EventPipe basierende Ablaufverfolgungstools wie `dotnet-counters`, `dotnet-gcdump` und `dotnet-trace` problemlos plattformübergreifend verwendet werden.

Da EventPipe jedoch eine integrierte Runtimekomponente ist, ist der zugehörige Bereich auf verwalteten Code und die Runtime selbst beschränkt. EventPipe kann nicht zum Nachverfolgen detaillierterer Ereignisse wie das Auflösen von nativen Codestapeln oder das Abrufen verschiedener Kernelereignisse verwendet werden. Wenn Sie die C/C++-Interop in Ihrer App verwenden, die Runtime selbst überwachen (in C++ geschrieben) oder eine genauere Diagnose des App-Verhaltens haben möchten, die Kernelereignisse erfordert (d. h. threadnative, den Kontext wechselnde Ereignisse), sollten Sie ETW oder [perf/LTTng](./trace-perfcollect-lttng.md) verwenden.

Ein weiterer wichtiger Unterschied zwischen EventPipe und ETW/LTTng besteht in den Anforderungen für die Berechtigungen für Administratoren und Root-Benutzer. Sie müssen Administrator oder Root-Benutzer sein, um eine Anwendung mithilfe von ETW oder LTTng nachverfolgen zu können. Wenn Sie EventPipe verwenden, können Sie Anwendungen nachverfolgen, solange die Ablaufverfolgung (z. B. `dotnet-trace`) für den Benutzer ausgeführt wird, der die Anwendung gestartet hat.

Die folgende Tabelle ist eine Zusammenfassung der Unterschiede zwischen EventPipe und ETW/LTTng.

|Funktion|EventPipe|ETW|LTTng|
|-------|---------|---|-----------|
|Plattformübergreifend|Ja|Nein (nur unter Windows)|Nein (nur für unterstützte Linux-Distributionen)|
|Anfordern von Berechtigungen für Administratoren und Root-Benutzer|Nein|Ja|Ja|
|Abrufen von Betriebssystem- oder Kernelereignissen|Nein|Ja|Ja|
|Auflösen nativer Aufruflisten|Nein|Ja|Ja|

## <a name="use-eventpipe-to-trace-your-net-application"></a>Verwenden von EventPipe zum Nachverfolgen der .NET-Anwendung

Sie können EventPipe verwenden, um Ihre .NET-Anwendung auf unterschiedlichste Weise nachzuverfolgen:

* Verwenden Sie eines der [Diagnosetools](#tools-that-use-eventpipe), die auf EventPipe basieren.

* Verwenden Sie die [Microsoft.Diagnostics.NETCore.Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md)-Bibliothek, um Ihr eigenes Tool zum Konfigurieren und Starten von EventPipe-Sitzungen zu erstellen.

* Verwenden Sie [Umgebungsvariablen](#trace-using-environment-variables) zum Starten von EventPipe.

Nachdem Sie eine `nettrace`-Datei erstellt haben, die Ihre EventPipe-Ereignisse enthält, können Sie die Datei in [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) oder Visual Studio anzeigen. Auf Nicht-Windows-Plattformen können Sie die `nettrace`-Datei mithilfe des Befehls [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) in das `speedscope`- oder `Chromium`-Ablaufverfolgungsformat konvertieren und mit [`speedscope`](https://www.speedscope.app/) oder Chrome DevTools anzeigen.

Sie können EventPipe-Ablaufnachverfolgungen mit [TraceEvent](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md) auch programmgesteuert analysieren.

### <a name="tools-that-use-eventpipe"></a>Tools, die EventPipe verwenden

Dies ist die einfachste Möglichkeit, EventPipe zum Nachverfolgen Ihrer Anwendung zu verwenden. Weitere Informationen zur Verwendung dieser Tools finden Sie in der Dokumentation zu den einzelnen Tools.

* [dotnet-counters](./dotnet-counters.md) ermöglicht Ihnen das Überwachen und Erfassen von verschiedenen Metriken, die von der .NET-Runtime und Kernbibliotheken ausgegeben werden. Dies ist ebenfalls für benutzerdefinierte Metriken möglich, die Sie selbst schreiben.

* Mit [dotnet-gcdump](./dotnet-gcdump.md) können Sie GC-Heapspeicherabbilder von Liveprozessen erfassen, um den verwalteten Heap einer Anwendung zu analysieren.

* [dotnet-trace](./dotnet-trace.md) ermöglicht das Erfassen von Ablaufnachverfolgungen von Anwendungen, um die Leistung zu analysieren.

## <a name="trace-using-environment-variables"></a>Ablaufverfolgung mithilfe von Umgebungsvariablen

Der bevorzugte Mechanismus für die Verwendung von EventPipe ist die Verwendung der Bibliothek `dotnet-trace` oder `Microsoft.Diagnostics.NETCore.Client`.

Sie können jedoch die folgenden Umgebungsvariablen verwenden, um eine EventPipe-Sitzung für eine App einzurichten und die Ablaufverfolgung direkt in eine Datei zu schreiben. Beenden Sie die Anwendung, um die Ablaufverfolgung zu beenden.

* `COMPlus_EnableEventPipe`: Legen Sie diese Umgebungsvariable auf `1` fest, um eine EventPipe-Sitzung zu starten, die die Ablaufverfolgung direkt in eine Datei schreibt. Der Standardwert ist `0`.

* `COMPlus_EventPipeOutputPath`: Dies ist der Pfad zur ausgegebenen EventPipe-Ablaufverfolgungsdatei, wenn diese für die Ausführung über `COMPlus_EnableEventPipe` konfiguriert ist. Der Standardwert ist `trace.nettrace`, der in demselben Verzeichnis erstellt wird, über das die App ausgeführt wird.

* `COMPlus_CircularBufferMB`: Dies ist die Größe des von EventPipe verwendeten internen Puffers, wenn eine Ausführung über `COMPlus_EnableEventPipe` konfiguriert ist.

* `COMPlus_EventPipeConfig`: Hiermit wird die EventPipe-Sitzungskonfiguration eingerichtet, wenn eine EventPipe-Sitzung mit `COMPlus_EnableEventPipe` gestartet wird.

  Die Syntax ist wie folgt:

  `<provider>:<keyword>:<level>`

  Sie können auch mehrere Anbieter angeben, indem Sie sie mit einem Komma verketten:

  `<provider1>:<keyword1>:<level1>,<provider2>:<keyword2>:<level2>`

  Wenn diese Umgebungsvariable nicht festgelegt ist, EventPipe aber durch `COMPlus_EnableEventPipe` aktiviert wird, wird die Ablaufverfolgung gestartet, indem die folgenden Anbieter mit den folgenden Schlüsselwörtern und Ebenen aktiviert werden:

  - `Microsoft-Windows-DotNETRuntime:4c14fccbd:5`
  - `Microsoft-Windows-DotNETRuntimePrivate:4002000b:5`
  - `Microsoft-DotNETCore-SampleProfiler:0:5`
