---
title: Protokollierung und Ablaufverfolgung – .NET Core
description: Eine Einführung in die Protokollierung und Ablaufverfolgung mit .NET Core.
ms.date: 10/12/2020
ms.openlocfilehash: fac8eeed63e8737ad42699d81b421747b207c69a
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753626"
---
# <a name="net-core-logging-and-tracing"></a>Protokollierung und Ablaufverfolgung mit .NET Core

Protokollierung und Ablaufverfolgung sind eigentlich zwei Bezeichnungen für dieselbe Technik. Diese einfache Technik wurde seit den Frühzeiten der Computer verwendet. Sie umfasst einfach das Instrumentieren einer Anwendung zum Schreiben einer Ausgabe, die später verwendet werden soll.

## <a name="reasons-to-use-logging-and-tracing"></a>Gründe für die Verwendung von Protokollierung und Ablaufverfolgung

Diese einfache Technik ist überraschend leistungsfähig. Sie kann in Situationen verwendet werden, in denen ein Debugger versagt:

- Probleme, die über einen längeren Zeitraum auftreten, können mit einem herkömmlichen Debugger schwierig zu debuggen sein. Protokolle ermöglichen eine ausführliche nachträgliche Überprüfung über einen längeren Zeitraum. Im Gegensatz dazu sind Debugger auf Echtzeitanalysen beschränkt.
- Multithreadanwendungen und verteilte Anwendungen sind häufig schwierig zu debuggen.  Durch das Anfügen eines Debuggers wird häufig das Verhalten geändert. Ausführliche Protokolle können nach Bedarf analysiert werden, um komplexe Systeme zu verstehen.
- Probleme in verteilten Anwendungen können aus einer komplexen Interaktion zwischen vielen Komponenten entstehen, und es ist möglicherweise nicht sinnvoll, mit jedem Teil des Systems einen Debugger zu verbinden.
- Viele Dienste sollten nicht verzögert werden. Das Anfügen eines Debuggers verursacht häufig Timeoutfehler.
- Probleme sind nicht immer vorhersehbar. Protokollierung und Ablaufverfolgung sind auf einen geringen Mehraufwand ausgelegt, sodass Programme immer aufzeichnen können, falls ein Problem auftritt.

## <a name="net-core-apis"></a>.NET Core-APIs

### <a name="print-style-apis"></a>Ausgabeformat-APIs

Die Klassen <xref:System.Console?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace?displayProperty=nameWithType> und <xref:System.Diagnostics.Debug?displayProperty=nameWithType> stellen jeweils ähnliche Ausgabeformat-APIs bereit, die für die Protokollierung gut geeignet sind.

Welche Ausgabeformat-API Sie verwenden, ist Ihnen überlassen. Hauptunterschiede:

- <xref:System.Console?displayProperty=nameWithType>
  - Immer aktiviert und schreibt immer in die Konsole.
  - Nützlich für Informationen, die dem Kunden möglicherweise im Release gezeigt werden müssen.
  - Da es sich um den einfachsten Ansatz handelt, wird er häufig für temporäres Ad-hoc-Debuggen verwendet. Dieser Debugcode wird häufig nicht in die Quellcodeverwaltung eingecheckt.
- <xref:System.Diagnostics.Trace?displayProperty=nameWithType>
  - Ist nur aktiviert, wenn `TRACE` durch Hinzufügen von `#define TRACE` zur Quelle oder durch Angabe der Option `/d:TRACE` bei der Kompilierung definiert ist.
  - Schreibt in angefügte <xref:System.Diagnostics.Trace.Listeners>, standardmäßig <xref:System.Diagnostics.DefaultTraceListener>.
  - Verwenden Sie diese API zum Erstellen von Protokollen, die in den meisten Builds aktiviert werden.
- <xref:System.Diagnostics.Debug?displayProperty=nameWithType>
  - Ist nur aktiviert, wenn `DEBUG` durch Hinzufügen von `#define DEBUG` zur Quelle oder durch Angabe der Option `/d:DEBUG` bei der Kompilierung definiert ist.
  - Schreibt in einen angefügten Debugger.
  - Schreibt bei `*nix` in stderr, wenn `COMPlus_DebugWriteToStdErr` festgelegt ist.
  - Verwenden Sie diese API zum Erstellen von Protokollen, die nur in Debugbuilds aktiviert werden.

### <a name="logging-events"></a>Protokollieren von Ereignissen

Die folgenden APIs sind eher ereignisorientiert. Anstelle von einfachen Zeichenfolgen protokollieren sie Ereignisobjekte.

- <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType>
  - EventSource ist die primäre Stamm-API für die .NET Core-Ablaufverfolgung.
  - In allen .NET-Standardversionen verfügbar.
  - Ermöglicht nur die Ablaufverfolgung serialisierbarer Objekte.
  - Kann innerhalb des Prozesses über alle [EventListener](xref:System.Diagnostics.Tracing.EventListener)-Instanzen, die für die Verwendung von EventSource konfiguriert sind, genutzt werden
  - Kann außerhalb des Prozesses über Folgendes verwendet werden:
    - [.NET Core-EventPipe](./eventpipe.md) auf allen Plattformen
    - [Ereignisablaufverfolgung für Windows (ETW)](/windows/win32/etw/event-tracing-portal)
    - [LTTng-Ablaufverfolgungs-Framework für Linux](https://lttng.org/)
      - Exemplarische Vorgehensweise: [Erfassen einer LTTng-Ablaufverfolgung mit PerfCollect](trace-perfcollect-lttng.md)

- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>
  - Enthalten in .NET Core sowie als [NuGet-Paket](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource) für .NET Framework.
  - Ermöglicht die prozessinterne Ablaufverfolgung von nicht serialisierbaren Objekten.
  - Schließt eine Bridge ein, damit ausgewählte Felder der protokollierten Objekte in eine <xref:System.Diagnostics.Tracing.EventSource> geschrieben werden können.

- <xref:System.Diagnostics.Activity?displayProperty=nameWithType>
  - Bietet eine eindeutige Methode zum Identifizieren von Protokollmeldungen, die sich aus einer bestimmten Aktivität oder Transaktion ergeben. Dieses Objekt kann zum dienstübergreifenden Korrelieren von Protokollen verwendet werden.

- <xref:System.Diagnostics.EventLog?displayProperty=nameWithType>
  - Nur Windows.
  - Schreibt Nachrichten in das Windows-Ereignisprotokoll.
  - Systemadministratoren erwarten, dass schwerwiegende Anwendungsfehlermeldungen im Windows-Ereignisprotokoll aufgeführt werden.

## <a name="ilogger-and-logging-frameworks"></a>ILogger und Protokollierungsframeworks

Die Low-Level-APIs sind möglicherweise nicht die richtige Wahl für Ihre Protokollierungsanforderungen. Ein Protokollierungsframework ist eventuell besser geeignet.

Über die <xref:Microsoft.Extensions.Logging.ILogger>-Schnittstelle wurde eine gemeinsame Protokollierungsschnittstelle erstellt, bei der die Protokollierungen mithilfe einer Abhängigkeitsinjektion eingefügt werden können.

Damit Sie beispielsweise die beste Wahl für Ihre Anwendung treffen können, bietet .NET Unterstützung für integrierte Frameworks sowie für Frameworks von Drittanbietern:

- [Integrierte .NET-Protokollierungsanbieter](../extensions/logging-providers.md#built-in-logging-providers)
- [Dritte .NET-Protokollierungsanbieter](../extensions/logging-providers.md#third-party-logging-providers)

## <a name="logging-related-references"></a>Verweise zur Protokollierung

- [Vorgehensweise: Bedingtes Kompilieren mit Ablaufverfolgung und Debuggen](../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)

- [Vorgehensweise: Hinzufügen von Ablaufverfolgungsanweisungen zu Anwendungscode](../../framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)

- [Die .NET-Protokollierung](../extensions/logging.md) bietet eine Übersicht über die unterstützten Protokollierungstechniken.

- Die [C#-Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) kann das Schreiben von Protokollierungscode vereinfachen.

- [Ereignisliste für Runtimeanbieter](../../fundamentals/diagnostics/runtime-events.md)

- [Bekannte Ereignisanbieter in .NET](well-known-event-providers.md)

- Die <xref:System.Exception.Message?displayProperty=nameWithType>-Eigenschaft ist nützlich für das Protokollieren von Ausnahmen.

- Die <xref:System.Diagnostics.StackTrace?displayProperty=nameWithType>-Klasse kann nützlich sein, um in Ihren Protokollen Stapelinformationen bereitzustellen.

## <a name="performance-considerations"></a>Überlegungen zur Leistung

Die Zeichenfolgenformatierung kann eine deutliche CPU-Verarbeitungszeit beanspruchen.

Bei leistungskritischen Anwendungen empfiehlt sich Folgendes:

- Vermeiden Sie umfassende Protokollierung, wenn diese nicht überprüft wird. Vermeiden Sie das Erstellen aufwendiger Protokollierungsnachrichten, indem Sie zuerst überprüfen, ob die Protokollierung aktiviert ist.
- Protokollieren Sie nur nützliche Informationen.
- Verschieben Sie anspruchsvolle Formatierung in die Analysephase.
