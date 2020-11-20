---
title: Ablaufverfolgung von .NET-Anwendungen mit perfcollect
description: In diesem Tutorial werden Sie Schritt für Schritt durch das Erfassen einer Ablaufverfolgung mit perfcollect in .NET geleitet.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 376c957833924a9991e574557671ea3c8503d7c2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507240"
---
# <a name="trace-net-applications-with-perfcollect"></a>Ablaufverfolgung von .NET-Anwendungen mit perfcollect

**Dieser Artikel gilt für: ✔️** .NET Core 2.1 SDK und neuere Versionen

Wenn unter Linux Leistungsprobleme auftreten, können Sie mit `perfcollect` eine Ablaufverfolgung erfassen, um detaillierte Informationen zu den Vorgängen auf dem Computer zum Zeitpunkt des Leistungsproblems zu sammeln.

Bei `perfcollect` handelt es sich um ein Bash-Skript, das das [Linux Trace Toolkit Next Generation (LTTng)](https://lttng.org) verwendet, um Ereignisse zu erfassen, die von der Runtime oder einer beliebigen [EventSource](xref:System.Diagnostics.Tracing.EventListener)-Klasse geschrieben wurden. Zudem verwendet es [perf](https://perf.wiki.kernel.org/), um CPU-Beispiele des Zielprozesses zu sammeln.

## <a name="prepare-your-machine"></a>Vorbereiten Ihres Computers

Führen Sie die folgenden Schritte durch, um Ihren Computer für das Erfassen einer Leistungsablaufverfolgung mit `perfcollect` vorzubereiten.

> [!NOTE]
> Wenn Sie sich in einer Containerumgebung befinden, muss Ihr Container über `SYS_ADMIN`-Funktionen verfügen. Weitere Informationen zur Ablaufverfolgung von Anwendungen innerhalb von Containern mithilfe von perfcollect finden Sie unter [Sammeln von Diagnosen in Containern](./diagnostics-in-containers.md).

1. Laden Sie `perfcollect` herunter.

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. Sorgen Sie dafür, dass das Skript ausführbar ist.

    > ```bash
    > chmod +x perfcollect
    > ```

3. Installieren Sie die für die Ablaufverfolgung erforderlichen Komponenten. Dabei handelt es sich um die eigentlichen Ablaufverfolgungsbibliotheken.

    > ```bash
    > sudo ./perfcollect install
    > ```

    Auf diese Weise werden die folgenden erforderlichen Komponenten auf Ihrem Computer installiert:

    1. `perf`: Dies ist das Linux-Subsystem zu Leistungsereignissen und die begleitende Anwendung zur Benutzermodusanzeige/-sammlung. `perf` ist Teil der Linux-Kernelquelle, wird bei der Standardeinstellung normalerweise jedoch nicht installiert.

    2. `LTTng`: Dies wird zum Erfassen von Ereignisdaten verwendet, die zur Laufzeit von CoreCLR ausgegeben werden. Diese Daten werden dann verwendet, um das Verhalten verschiedener Runtimekomponenten wie GC, JIT und Threadpool zu analysieren.

Die neuesten Versionen von .NET Core und das Linux-Leistungstool unterstützen die automatische Auflösung von Methodennamen für Frameworkcode. Wenn Sie mit Version 3.1 oder einer früheren Version von .NET Core arbeiten, ist ein zusätzlicher Schritt erforderlich. Weitere Informationen finden Sie unter [Auflösen von Frameworksymbolen](#resolve-framework-symbols).

Zum Auflösen von Methodennamen nativer Runtime-DLLs (z. B. libcoreclr.so) löst `perfcollect` beim Konvertieren von Daten Symbole für diese auf. Allerdings trifft dies nur zu, wenn die Symbole für diese Binärdateien vorhanden sind. Weitere Informationen finden Sie im Abschnitt [Abrufen von Symbolen für die native Runtime](#get-symbols-for-the-native-runtime).

## <a name="collect-a-trace"></a>Erfassen einer Ablaufverfolgung

1. Sie benötigen zwei Shells: eine zum Steuern der Ablaufverfolgung, als **[Trace]** bezeichnet, und eine zum Ausführen der Anwendung, als **[App]** bezeichnet.

2. **[Trace]** Starten Sie die Ablaufverfolgung.

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    Erwartete Ausgabe:

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. **[App]** Richten Sie die Anwendungsshell mit den folgenden Umgebungsvariablen ein. Dies ermöglicht die CoreCLR-Konfiguration für die Ablaufverfolgung.

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. **[App]** Führen Sie die App aus, und zwar so lange wie nötig, um das Leistungsproblem zu erfassen. Die genaue Ausführungsdauer kann auch nur sehr kurz sein, solange das Zeitfenster, in dem das zu untersuchende Leistungsproblem auftritt, ausreichend erfasst wird.

    > ```bash
    > dotnet run
    > ```

5. **[Trace]** Halten Sie die Ablaufverfolgung an. Drücken Sie dazu STRG+C.

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    Die komprimierte Ablaufverfolgungsdatei ist jetzt im aktuellen Arbeitsverzeichnis gespeichert.

## <a name="view-a-trace"></a>Anzeigen einer Ablaufverfolgung

Es gibt mehrere Möglichkeiten, die erfasste Ablaufverfolgung anzuzeigen. Ablaufverfolgungen werden am besten mithilfe von [PerfView](https://aka.ms/perfview) unter Windows angezeigt. Sie können aber auch direkt unter Linux mithilfe von `PerfCollect` selbst oder mit `TraceCompass` angezeigt werden.

### <a name="use-perfcollect-to-view-the-trace-file"></a>Verwenden von perfcollect zum Anzeigen der Ablaufverfolgungsdatei

Sie können perfcollect selbst verwenden, um die erfasste Ablaufverfolgung anzuzeigen. Führen Sie zu diesem Zweck den folgenden Befehl aus:

```bash
./perfcollect view sampleTrace.trace.zip
```

Dadurch wird standardmäßig die CPU-Überwachung der Anwendung mithilfe von `perf` angezeigt.

Zum Anzeigen der über `LTTng` erfassten Ereignisse können Sie das Flag `-viewer lttng` übergeben, um die einzelnen Ereignisse anzuzeigen:

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

Dadurch wird der `babeltrace`-Viewer zum Drucken der Nutzdaten der Ereignisse verwendet:

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a>Verwenden von PerfView zum Öffnen der Ablaufverfolgungsdatei

Zum Anzeigen einer Aggregatansicht sowohl des CPU-Beispiels als auch der Ereignisse können Sie `PerfView` auf einem Windows-Computer verwenden.

1. Kopieren Sie die trace.zip-Datei von Linux auf einen Windows-Computer.

2. Laden Sie PerfView über den folgenden Link herunter: <https://aka.ms/perfview>.

3. Führen Sie PerfView.exe aus.

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

PerfView zeigt die Liste der Ansichten an, die auf der Grundlage der in der Ablaufverfolgungsdatei enthaltenen Daten unterstützt werden.

- Wählen Sie für CPU-Untersuchungen **CPU-Stapel** aus.

- Wählen Sie für detaillierte Informationen **GCStats** aus.

- Wählen Sie für JIT-Informationen pro Prozess/Modul/Methode **JITStats** aus.

- Wenn für die von Ihnen benötigten Informationen keine Ansicht vorhanden ist, können Sie versuchen, die Ereignisse in der Rohdatenansicht für Ereignisse anzuzeigen.  Wählen Sie **Ereignisse** aus.

Weitere Informationen zum Interpretieren von Ansichten in PerfView finden Sie unter den Hilfeverknüpfungen in der Ansicht selbst oder im Hauptfenster von PerfView unter **Help > Users Guide** (Hilfe > Benutzerleitfaden).

### <a name="use-tracecompass-to-open-the-trace-file"></a>Verwenden von TraceCompass zum Öffnen der Ablaufverfolgungsdatei

[Eclipse Trace Compass](https://www.eclipse.org/tracecompass/) ist eine weitere Option zum Anzeigen der Ablaufverfolgungen. `TraceCompass` funktioniert auch auf Linux-Computern, sodass Sie die Ablaufverfolgung nicht auf einen Windows-Computer verschieben müssen. Wenn Sie `TraceCompass` zum Öffnen Ihrer Ablaufverfolgungsdatei verwenden möchten, müssen Sie die Datei entzippen.

```bash
unzip myTrace.trace.zip
```

`perfcollect` speichert die erfasste LTTng-Ablaufverfolgung in einem CTF-Dateiformat in einem Unterverzeichnis von `lttngTrace`. Die CTF-Datei wird in einem Verzeichnis ähnlich dem folgenden gespeichert: `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.

Sie können die CTF-Ablaufverfolgungsdatei in `TraceCompass` öffnen, indem Sie auf `File -> Open Trace` und dann auf die `metadata`-Datei klicken.

Weitere Informationen finden Sie in der [`TraceCompass`-Dokumentation](https://www.eclipse.org/tracecompass/).

## <a name="resolve-framework-symbols"></a>Auflösen von Frameworksymbolen

Frameworksymbole müssen manuell generiert werden, wenn die Ablaufverfolgung erfasst wird. Sie unterscheiden sich von Symbolen auf App-Ebene, da das Framework vorkompiliert ist, während der App-Code JIT-kompiliert ist. Bei Frameworkcode, der in nativen Code vorkompiliert wurde, müssen Sie für die Generierung der Zuordnung vom nativen Code zum Namen der Methoden `crossgen` aufrufen.

`perfcollect` kann die meisten Details verarbeiten, `crossgen` muss jedoch verfügbar sein. Es wird in der Standardeinstellung nicht mit der .NET-Verteilung installiert. Wenn `crossgen` nicht vorhanden ist, werden Sie von `perfcollect` gewarnt und auf diese Anweisungen verwiesen. Sie müssen exakt die richtige Version von crossgen für die verwendete Runtime abrufen, um Fehler zu beheben. Wenn Sie das crossgen-Tool im gleichen Verzeichnis wie die .NET-Runtime-DLLs (z. B. libcoreclr.so) ablegen, kann `perfcollect` es finden und für Sie die Frameworksymbole der Ablaufverfolgungsdatei hinzufügen.

Normalerweise wird beim Erstellen einer .NET-Anwendung nur die DLL für den von Ihnen geschriebenen Code generiert. Dabei wird eine Shared Runtime für den Rest verwendet.   Sie können jedoch auch eine sogenannte „eigenständige“ Version einer Anwendung generieren, die alle Runtime-DLLs enthält. `crossgen` ist Teil des NuGet-Pakets, das zum Erstellen eigenständiger Apps verwendet wird. Eine Möglichkeit zum Abrufen der richtigen `crossgen`-Version ist daher, ein eigenständiges Paket Ihrer Anwendung zu erstellen.

Beispiel:

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

Dadurch wird eine neue Hallo Welt-Anwendung als eigenständige App erstellt.

Als Nebeneffekt der Erstellung einer eigenständigen Anwendung lädt das .NET-Tool ein NuGet-Paket mit dem Namen „runtime.linux-x64.microsoft.netcore.app“ herunter und legt es im Verzeichnis „~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION“ ab, wobei VERSION für die Versionsnummer Ihrer .NET Core-Runtime (z. B. 2.1.0) steht. Darunter befindet sich ein Toolverzeichnis, innerhalb dessen sich das von Ihnen benötigte crossgen-Tool befindet. Ab .NET Core 3.0 ist das Paketverzeichnis „~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION“.

Das `crossgen`-Tool muss neben der Runtime abgelegt werden, die tatsächlich von Ihrer Anwendung verwendet wird. In der Regel verwendet Ihre App die unter „/usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION“ installierte freigegebene Version von .NET Core, wobei VERSION für die Versionsnummer der .NET-Runtime steht. Da es sich um einen freigegebenen Speicherort handelt, müssen Sie Administrator sein, um diesen zu ändern. Wenn die VERSION 2.1.0 ist, lauten die Befehle zum Aktualisieren von `crossgen` wie folgt:

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

Sobald Sie diesen Schritt abgeschlossen haben, verwendet `perfcollect` crossgen zum Einschließen von Frameworksymbolen. Die von `perfcollect` üblicherweise ausgegebene Warnung sollte nicht mehr angezeigt werden. Dies muss nur einmal pro Computer erfolgen (bis Sie die Runtime aktualisieren).

### <a name="alternative-turn-off-use-of-precompiled-code"></a>Alternative: Deaktivieren der Verwendung von vorkompiliertem Code

Wenn Sie die .NET-Runtime nicht aktualisieren (`crossgen` nicht hinzufügen) können oder die oben beschriebene Prozedur aus irgendeinem Grund nicht funktioniert, können Sie einen anderen Ansatz zum Abrufen von Frameworksymbolen verwenden. Sie können die Runtime anweisen, den vorkompilierten Frameworkcode einfach nicht zu verwenden. Der Code wird JIT-kompiliert, und `crossgen` wird nicht benötigt.

> [!NOTE]
> Wenn Sie sich für diesen Ansatz entscheiden, könnte sich die Startzeit Ihrer Anwendung verlängern.

Hierfür können Sie die folgende Umgebungsvariable hinzufügen:

```bash
export COMPlus_ZapDisable=1
```

Mit dieser Änderung müssten die Symbole für den gesamten .NET-Code abgerufen werden.

## <a name="get-symbols-for-the-native-runtime"></a>Abrufen von Symbolen für die native Runtime

In den meisten Fällen sind Sie an Ihrem eigenen Code interessiert, den `perfcollect` standardmäßig auflöst. Manchmal ist es hilfreich zu wissen, was innerhalb der .NET-DLLs vor sich geht (wovon der letzte Abschnitt handelte). Manchmal ist es aber auch interessant, was in den nativen Runtime-DLLs (in der Regel libcoreclr.so) geschieht.  `perfcollect` löst die Symbole für diese auf, wenn deren Daten konvertiert werden. Dies ist jedoch nur der Fall, wenn die Symbole für diese nativen DLLs vorhanden sind (und sich neben der Bibliothek befinden, der sie dienen).

Sie können hierfür den globalen Befehl [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) verwenden. So verwenden Sie „dotnet-symbol“ zum Abrufen von Symbolen der nativen Runtime:

1. Installieren Sie `dotnet-symbol`:

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. Laden Sie die Symbole herunter. Wenn Sie die Version 2.1.0 der .NET Core-Runtime installiert haben, lautet der Befehl hierfür folgendermaßen:

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. Kopieren Sie die Symbole in das richtige Verzeichnis.

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    Wenn dies nicht möglich ist, weil Sie keinen Schreibzugriff auf das entsprechende Verzeichnis haben, können Sie die Symbole mithilfe von `perf buildid-cache` hinzufügen.

Danach sollten symbolische Namen für die nativen DLLs zurückgegeben werden, wenn Sie `perfcollect` ausführen.

## <a name="collect-in-a-docker-container"></a>Sammeln in einem Docker-Container

Weitere Informationen zur Verwendung von `perfcollect` in Containerumgebungen finden Sie unter [Sammeln von Diagnosen in Containern](./diagnostics-in-containers.md).
