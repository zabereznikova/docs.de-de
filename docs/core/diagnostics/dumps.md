---
title: Speicherabbilder – .NET
description: Eine Einführung in Speicherabbilder in .NET
ms.date: 10/12/2020
ms.openlocfilehash: f68d9bd804350366625df014df4d9ca0641d5d4d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188555"
---
# <a name="dumps"></a>Dumps

Ein Speicherabbild ist eine Datei, die eine Momentaufnahme eines Prozesses zum Zeitpunkt der Erstellung enthält und zur Untersuchung des Zustands Ihrer Anwendung nützlich sein kann. Mithilfe von Speicherabbildern können Sie Ihre .NET-Anwendung selbst dann debuggen, wenn sich das Anfügen eines Debuggers schwierig gestaltet, z. B. in Umgebungen für die Produktion oder für Continuous Integration. Speicherabbilder ermöglichen es Ihnen, den Zustand des problematischen Prozesses zu erfassen und den Prozess zu untersuchen, ohne die Anwendung beenden zu müssen.

## <a name="collect-dumps"></a>Erfassen von Speicherabbildern

Je nachdem, auf welcher Plattform Sie Ihre App ausführen, können Speicherabbilder auf verschiedene Arten gesammelt werden.

> [!NOTE]
> Das Erfassen eines Speicherabbilds in einem Container erfordert die Funktion PTRACE, die über `--cap-add=SYS_PTRACE` oder `--privileged` hinzugefügt werden kann.
> [!NOTE]
> Speicherabbilder können vertrauliche Informationen aufweisen, da sie die vollständigen Arbeitsspeicherdaten des laufenden Prozesses enthalten. Bedenken Sie beim Arbeiten mit Speicherabbildern alle Sicherheitseinschränkungen und -richtlinien.

### <a name="collecting-dumps-on-crash"></a>Erfassen von Speicherabbildern bei einem Absturz

Sie können Ihre Anwendung mithilfe von Umgebungsvariablen so konfigurieren, dass bei einem Absturz ein Speicherabbild erfasst wird. Dies ist hilfreich, wenn Sie der Ursache eines Absturzes auf den Grund gehen möchten. Das Erfassen eines Speicherabbilds beim Auslösen einer Ausnahme kann Ihnen z. B. helfen, ein Problem zu erkennen, indem Sie den Zustand der App zum Zeitpunkt des Absturzes untersuchen.

In der folgenden Tabelle sind die Umgebungsvariablen aufgeführt, die Sie für die Erfassung von Speicherabbildern bei einem Absturz konfigurieren können.

|Umgebungsvariable|BESCHREIBUNG|Standardwert|
|-------|---------|---|
|`COMPlus_DbgEnableMiniDump`|Wenn die Variable auf 1 festgelegt ist, wird ein Kernspeicherabbild erstellt.|0|
|`COMPlus_DbgMiniDumpType`|Der Typ des zu erfassenden Speicherabbilds. Weitere Informationen finden Sie in der Tabelle weiter unten.|2 (`MiniDumpWithPrivateReadWriteMemory`)|
|`COMPlus_DbgMiniDumpName`|Pfad zu einer Datei, in die das Speicherabbild geschrieben werden soll|`/tmp/coredump.<pid>`|
|`COMPlus_CreateDumpDiagnostics`|Wenn die Variable auf 1 festgelegt ist, wird die Diagnoseprotokollierung des Speicherabbildprozesses aktiviert.|0|

In der folgenden Tabelle sind alle Optionen aufgeführt, die Sie für die Variable `COMPlus_DbgMiniDumpType` verwenden können, die als Wert angegeben werden kann. Wenn Sie `COMPlus_DbgMiniDumpType` z. B. auf 1 festlegen, wird ein Speicherabbild des Typs `MiniDumpNormal` bei einem Absturz erfasst.

|Wert|Name|BESCHREIBUNG|
|-----|----|-----------|
|1|`MiniDumpNormal`|Es werden nur die Informationen aufgenommen, die zum Erfassen von Stapelüberwachungen für alle vorhandenen Threads in einem Prozess erforderlich sind. Heaparbeitsspeicher und -informationen der GC sind eingeschränkt.|
|2|`MiniDumpWithPrivateReadWriteMemory`|Es werden nur die GC-Heaps und -Informationen aufgenommen, die zum Erfassen von Stapelüberwachungen für alle vorhandenen Threads in einem Prozess erforderlich sind.|
|3|`MiniDumpFilterTriage`|Es werden nur die Informationen aufgenommen, die zum Erfassen von Stapelüberwachungen für alle vorhandenen Threads in einem Prozess erforderlich sind. Heaparbeitsspeicher und -informationen der GC sind eingeschränkt.|
|4|`MiniDumpWithFullMemory`|Es wird der gesamte verfügbare Arbeitsspeicher im Prozess aufgenommen. Die Rohdaten des Arbeitsspeichers sind am Ende enthalten, sodass die ursprünglichen Strukturen direkt ohne die unformatierten Arbeitsspeicherinformationen zugeordnet werden können. Diese Option kann zu einer sehr großen Datei führen.|

### <a name="collecting-dumps-at-specific-point-in-time"></a>Sammeln von Speicherabbildern zu einem bestimmten Zeitpunkt

Speicherabbilder sollten auch erfasst werden, wenn eine App noch nicht abgestürzt ist. Wenn Sie z. B. den Zustand einer Anwendung untersuchen möchten, die sich anscheinend in einem Deadlock befindet, ist es nicht hilfreich, Umgebungsvariablen zum Erfassen von Speicherabbildern bei einem Absturz zu konfigurieren, da die App noch immer ausgeführt wird.

Zum Erfassen eines Speicherabbilds zu einem benutzerdefinierten Zeitpunkt können Sie `dotnet-dump` verwenden. Hierbei handelt es sich um ein CLI-Tool zum Erfassen und Analysieren von Speicherabbildern. Weitere Informationen zum Erfassen von Speicherabbildern mit `dotnet-dump` finden Sie unter [Hilfsprogramm zu Sammeln und Analysieren von Speicherabbildern](dotnet-dump.md).

## <a name="analyze-dumps"></a>Analysieren von Speicherabbildern

Sie können Speicherabbilder mithilfe des CLI-Tools [`dotnet-dump`](dotnet-dump.md) oder mithilfe von [Visual Studio](/visualstudio/debugger/using-dump-files) analysieren.

> [!NOTE]
> Mithilfe von Visual Studio, Version 16.8 und höher können Sie [Linux-Speicherabbilder öffnen](https://devblogs.microsoft.com/visualstudio/linux-managed-memory-dump-debugging/), die unter .NET Core 3.1.7 oder höher erstellt wurden.  
> [!NOTE]
> Wenn natives Debuggen erforderlich ist, kann die [SOS-Debuggererweiterung](sos-debugging-extension.md) mit [LLDB unter Linux und macOS](debug-linux-dumps.md#analyze-dumps-on-linux)verwendet werden. SOS wird auch für [WinDbg/cdb](/windows-hardware/drivers/debugger/debugger-download-tools) unter Windows unterstützt, aber die Verwendung von Visual Studio wird empfohlen.

## <a name="see-also"></a>Siehe auch

Informieren Sie sich auch darüber, wie Sie mithilfe von Speicherabbildern Probleme in Ihrer .NET-Anwendung diagnostizieren können.

* Im Tutorial [Debuggen von Linux-Speicherabbildern](debug-linux-dumps.md) werden Sie durch das Debuggen eines unter Linux erfassten Speicherabbilds geführt.

* Im Tutorial [Debuggen von Deadlocks](debug-deadlock.md) werden Sie durch das Debuggen eines Deadlocks in einer .NET-Anwendung mithilfe von Speicherabbildern geführt.
