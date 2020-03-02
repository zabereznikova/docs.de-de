---
title: Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core
description: Erfahren Sie, wie Sie entladbaren AssemblyLoadContext zum Laden und Entladen von verwalteten Assemblys verwenden und wie Sie Probleme beheben können, die den Erfolg des Entladevorgangs verhindern.
author: janvorli
ms.author: janvorli
ms.date: 02/05/2019
ms.openlocfilehash: 267c2209556b66ab3541c9c79c99d7eceb2024da
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159740"
---
# <a name="how-to-use-and-debug-assembly-unloadability-in-net-core"></a>Verwenden und Debuggen von Assemblyentladbarkeit in .NET Core

Ab .NET Core 3.0 wird die Möglichkeit unterstützt, eine Gruppe von Assemblys zu laden und später zu entladen. In .NET Framework wurden benutzerdefinierte App-Domänen zu diesem Zweck verwendet, .NET Core unterstützt jedoch nur eine einzelne App-Standarddomäne.

.NET Core 3.0 und höhere Versionen unterstützen Entladbarkeit über <xref:System.Runtime.Loader.AssemblyLoadContext>. Sie können eine Gruppe von Assemblys in einen entladbaren `AssemblyLoadContext` laden, Methoden in ihnen ausführen oder sie einfach mithilfe von Reflektion untersuchen und schließlich den `AssemblyLoadContext` entladen. Dadurch werden die Assemblys entladen, die in den `AssemblyLoadContext` geladen wurden.

Es gibt einen bemerkenswerten Unterschied zwischen dem Entladen mithilfe von `AssemblyLoadContext` und der Verwendung von AppDomains. Mit AppDomains wird das Entladen erzwungen. Zum Zeitpunkt der Entladung werden beispielsweise alle Threads abgebrochen, die in der Ziel-AppDomain ausgeführt werden. Außerdem werden unter anderem verwaltete COM-Objekte gelöscht, die in der Ziel-AppDomain erstellt wurden. Mit `AssemblyLoadContext` ist den Entladevorgang „kooperativ“. Durch Aufrufen der <xref:System.Runtime.Loader.AssemblyLoadContext.Unload%2A?displayProperty=nameWithType>-Methode wird der Entladevorgang nur initiiert. Das Entladen wird abgeschlossen, nachdem die folgenden Bedingungen erfüllt sind:

- Es gibt keine Threads, die über Methoden aus den Assemblys in ihren Aufruflisten verfügen, die in den `AssemblyLoadContext` geladen werden.
- Auf keinen der Typen aus den in den `AssemblyLoadContext` geladenen Assemblys, auf keine Instanzen dieser Typen und auf keine der Assemblys selbst wird durch Folgendes verwiesen:
  - Verweise außerhalb des `AssemblyLoadContext`, ausgenommen schwache Verweise (<xref:System.WeakReference> oder <xref:System.WeakReference%601>).
  - Starke GC-Handles (Garbage Collector) ([GCHandleType.Normal](xref:System.Runtime.InteropServices.GCHandleType.Normal) oder [GCHandleType.pinned](xref:System.Runtime.InteropServices.GCHandleType.Pinned)) sowohl innerhalb als auch außerhalb des `AssemblyLoadContext`.

## <a name="use-collectible-assemblyloadcontext"></a>Verwenden des entladbaren „AssemblyLoadContext“-Objekts

Dieser Abschnitt enthält ein detailliertes schrittweises Tutorial, das eine einfache Möglichkeit zeigt, eine .NET Core-Anwendung in einen entladbaren `AssemblyLoadContext` zu laden, ihren Einstiegspunkt auszuführen und sie dann zu entladen. Das vollständige Beispiel finden Sie unter [https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading](https://github.com/dotnet/samples/tree/master/core/tutorials/Unloading).

### <a name="create-a-collectible-assemblyloadcontext"></a>Erstellen eines entladbaren AssemblyLoadContext

Sie müssen die Klasse von <xref:System.Runtime.Loader.AssemblyLoadContext> ableiten und ihre <xref:System.Runtime.Loader.AssemblyLoadContext.Load%2A?displayProperty=nameWithType>-Methode überladen. Diese Methode löst Verweise auf alle Assemblys auf, die Abhängigkeiten von in diesen `AssemblyLoadContext` geladenen Assemblys sind.

Der folgende Code ist ein Beispiel für den einfachsten benutzerdefinierten `AssemblyLoadContext`:

[!code-csharp[Simple custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/simple_example.cs#1)]

Wie Sie sehen können, gibt die `Load`-Methode `null` zurück. Dies bedeutet, dass alle Abhängigkeitsassemblys in den Standardkontext geladen werden und der neue Kontext nur die Assemblys enthält, die explizit in ihn geladen wurden.

Wenn Sie einige oder alle Abhängigkeiten in den `AssemblyLoadContext` laden möchten, können Sie `AssemblyDependencyResolver` in der `Load`-Methode verwenden. `AssemblyDependencyResolver` löst die Assemblynamen in absolute Assemblydateipfade auf. Der Konfliktlöser verwendet die Datei *.deps.json* und Assemblydateien im Verzeichnis der Hauptassembly, die in den Kontext geladen wurde.

[!code-csharp[Advanced custom AssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/complex_assemblyloadcontext.cs)]

### <a name="use-a-custom-collectible-assemblyloadcontext"></a>Verwenden eines benutzerdefinierten entladbaren AssemblyLoadContext

In diesem Abschnitt wird davon ausgegangen, dass die einfachere Version von `TestAssemblyLoadContext` verwendet wird.

Sie können eine Instanz des benutzerdefinierten `AssemblyLoadContext` erstellen und eine Assembly wie folgt in diesen laden:

[!code-csharp[Part 1](~/samples/snippets/standard/assembly/unloading/simple_example.cs#3)]

Für jede der Assemblys, auf die von der geladenen Assembly verwiesen wird, wird die `TestAssemblyLoadContext.Load`-Methode aufgerufen, sodass der `TestAssemblyLoadContext` entscheiden kann, von wo die Assembly abgerufen werden soll. In unserem Fall wird `null` zurückgegeben, um anzugeben, dass sie in den Standardkontext aus Speicherorten geladen werden soll, die die Runtime zum Laden von Assemblys standardmäßig verwendet.

Da nun eine Assembly geladen wurde, können Sie eine Methode daraus ausführen. Führen Sie die `Main`-Methode aus:

[!code-csharp[Part 2](~/samples/snippets/standard/assembly/unloading/simple_example.cs#4)]

Nachdem die `Main`-Methode abgeschlossen wurde, können Sie das Entladen einleiten, indem Sie entweder die `Unload`-Methode für den benutzerdefinierten `AssemblyLoadContext` aufrufen oder den Verweis auf den `AssemblyLoadContext` entfernen:

[!code-csharp[Part 3](~/samples/snippets/standard/assembly/unloading/simple_example.cs#5)]

Dies reicht aus, um die Testassembly zu entladen. Bringen wird all dies in einer separaten, nicht inlinefähigen Methode zusammen, um sicherzustellen, dass `TestAssemblyLoadContext`, `Assembly` und `MethodInfo` (der `Assembly.EntryPoint`) nicht durch Stackslotverweise (reale oder durch JIT eingeführte lokale Variablen) aktiv gehalten werden. Dies könnte den `TestAssemblyLoadContext` aktiv lassen und das Entladen verhindern.

Geben Sie außerdem einen schwachen Verweis auf den `AssemblyLoadContext` zurück, damit Sie ihn später verwenden können, um den Abschluss des Entladevorgangs zu erkennen.

[!code-csharp[Part 4](~/samples/snippets/standard/assembly/unloading/simple_example.cs#2)]

Nun können Sie diese Funktion ausführen, um die Assembly zu laden, auszuführen und zu entladen.

[!code-csharp[Part 5](~/samples/snippets/standard/assembly/unloading/simple_example.cs#6)]

Das Entladen wird jedoch nicht sofort beendet. Wie bereits erwähnt, verwendet der Vorgang den Garbage Collector, um alle Objekte aus der Testassembly zu erfassen. In vielen Fällen ist es nicht erforderlich, auf den Abschluss des Entladevorgangs zu warten. Es gibt jedoch Fälle, in denen es nützlich zu wissen ist, dass der Entladevorgang abgeschlossen wurde. Beispielsweise, wenn Sie die Assemblydatei löschen möchten, die vom Datenträger in den benutzerdefinierten `AssemblyLoadContext` geladen wurde. In einem solchen Fall kann der folgende Codeausschnitt verwendet werden. Er löst eine Garbage Collection aus und wartet auf ausstehende Finalizer in einer Schleife, bis der schwache Verweis auf den benutzerdefinierten `AssemblyLoadContext` auf `null` festgelegt wurde, um anzugeben, dass das Zielobjekt erfasst wurde. In den meisten Fällen ist nur ein Durchlauf durch die Schleife erforderlich. Für komplexere Fälle, in denen Objekte, die durch den im `AssemblyLoadContext` ausgeführten Code erstellt wurden, über Finalizer verfügen, sind möglicherweise weitere Durchgänge erforderlich.

[!code-csharp[Part 6](~/samples/snippets/standard/assembly/unloading/simple_example.cs#7)]

### <a name="the-unloading-event"></a>Das Unloading-Ereignis

In einigen Fällen kann es erforderlich sein, dass der Code, der in einen benutzerdefinierten `AssemblyLoadContext` geladen wird, einige Bereinigungsaufgaben durchführt, wenn das Entladen initiiert wird. Beispielsweise kann es erforderlich sein, Threads zu beenden und einige GC-Handles zu bereinigen. Das `Unloading`-Ereignis kann in solchen Fällen verwendet werden. Ein Handler, der die erforderliche Bereinigung ausführt, kann mit diesem Ereignis verknüpft werden.

### <a name="troubleshoot-unloadability-issues"></a>Behandlung bei Problemen mit der Entladbarkeit

Aufgrund der kooperativen Natur der Entladung kann leicht vergessen werden, dass Verweise die Objekte ggf. in einem entladbaren `AssemblyLoadContext` aktiv halten und das Entladen verhindern können. Hier ist eine Zusammenfassung der Entitäten (einige davon nicht offensichtlich), die die Verweise enthalten können:

- Reguläre Verweise, die außerhalb des entladbaren `AssemblyLoadContext` enthalten und in einem Stackslot oder einem Prozessorregister gespeichert sind (lokale Variablen von Methoden, entweder explizit durch den Benutzercode oder implizit durch den JIT-Compiler erstellt), eine statische Variable oder ein starkes (fixierendes) GC-Handle und Transitivität, die auf Folgendes verweist:
  - Eine Assembly, die in den entladbaren `AssemblyLoadContext` geladen wurde.
  - Ein Typ aus einer solchen Assembly.
  - Eine Instanz eines Typs aus einer solchen Assembly.
- Threads, die Code aus einer Assembly ausführen, die in den entladbaren `AssemblyLoadContext` geladen wurde.
- Instanzen von benutzerdefinierten, nicht entladbaren `AssemblyLoadContext`-Typen, die im entladbaren `AssemblyLoadContext` erstellt wurden.
- Ausstehende <xref:System.Threading.RegisteredWaitHandle>-Instanzen, bei denen Rückrufe auf Methoden im benutzerdefinierten `AssemblyLoadContext` festgelegt sind.

> [!TIP]
> Objektverweise, die in Stackslots oder Prozessorregistern gespeichert sind und das Entladen eines `AssemblyLoadContext` verhindern könnten, können in folgenden Situationen auftreten:
>
> - Wenn Ergebnisse eines Funktionsaufrufs direkt an eine andere Funktion übergeben werden, obwohl keine vom Benutzer erstellte lokale Variable vorhanden ist.
> - Wenn der JIT-Compiler einen Verweis auf ein Objekt beibehält, das zu einem bestimmten Zeitpunkt in einer Methode verfügbar war.

## <a name="debug-unloading-issues"></a>Debuggen von Problemen beim Entladen

Das Debuggen von Problemen beim Entladen kann mühsam sein. Es können Situationen eintreten, in denen Sie nicht wissen, was einen `AssemblyLoadContext` aktiv halten könnte, aber das Entladen schlägt fehl. Die beste Waffe bei einem solchen Problem ist WinDbg (LLDB unter Unix) mit dem SOS-Plug-In. Sie müssen herausfinden, was einen `LoaderAllocator`, der zu dem jeweiligen `AssemblyLoadContext` gehört, aktiv bleiben lässt. Mit dem SOS-Plug-In können Sie GC-Heapobjekte, ihre Hierarchien und Stämme überprüfen.

Um das Plug-In in den Debugger zu laden, geben Sie den folgenden Befehl in der Debuggerbefehlszeile ein:

In WinDbg (in WinDbg scheint dies automatisch beim Einstieg in die .NET Core-Anwendung zu geschehen):

```console
.loadby sos coreclr
```

In LLDB:

```console
plugin load /path/to/libsosplugin.so
```

Debuggen wir ein Beispielprogramm, das Probleme beim Entladen hat. Der Quellcode ist unten enthalten. Wenn Sie ihn unter WinDbg ausführen, steigt das Programm direkt nach dem Versuch, den Erfolg des Entladevorgangs zu überprüfen, in den Debugger ein. Sie können dann mit der Suche nach den „Schuldigen“ beginnen.

> [!TIP]
> Wenn Sie mit LLDB unter Unix debuggen, wird den SOS-Befehlen in den folgenden Beispielen kein `!` vorangestellt.

```console
!dumpheap -type LoaderAllocator
```

Dieser Befehl sichert alle Objekte mit einem Typnamen, der `LoaderAllocator` enthält, aus dem GC-Heap. Im Folgenden ein Beispiel:

```console
         Address               MT     Size
000002b78000ce40 00007ffadc93a288       48
000002b78000ceb0 00007ffadc93a218       24

Statistics:
              MT    Count    TotalSize Class Name
00007ffadc93a218        1           24 System.Reflection.LoaderAllocatorScout
00007ffadc93a288        1           48 System.Reflection.LoaderAllocator
Total 2 objects
```

Überprüfen Sie im Abschnitt „Statistics“ unten die `MT` (`MethodTable`), die zu `System.Reflection.LoaderAllocator` gehört. Dies ist das Objekt, für das wir uns interessieren. Suchen Sie dann in der Liste am Anfang den Eintrag mit `MT`, der diesem Eintrag entspricht, und rufen Sie die Adresse des Objekts selbst ab. In unserem Fall lautet der Wert „000002b78000ce40“.

Nachdem wir nun die Adresse des `LoaderAllocator`-Objekts kennen, können wir einen anderen Befehl verwenden, um seine GC-Stämme zu finden:

```console
!gcroot -all 0x000002b78000ce40
```

Dieser Befehl sichert die Kette von Objektverweisen, die zur `LoaderAllocator`-Instanz führen. Die Liste beginnt mit dem Stamm, bei dem es sich um die Entität handelt, die den `LoaderAllocator` aktiv hält und daher den Kern des Problems darstellt. Der Stamm kann ein Stackslot, ein Prozessorregister, ein GC-Handle oder eine statische Variable sein.

Hier ist ein Beispiel für die Ausgabe des `gcroot`-Befehls:

```console
Thread 4ac:
    000000cf9499dd20 00007ffa7d0236bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
        rbp-20: 000000cf9499dd90
            ->  000002b78000d328 System.Reflection.RuntimeMethodInfo
            ->  000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
            ->  000002b78000d1d0 System.RuntimeType
            ->  000002b78000ce40 System.Reflection.LoaderAllocator

HandleTable:
    000002b7f8a81198 (strong handle)
    -> 000002b78000d948 test.Test
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

    000002b7f8a815f8 (pinned handle)
    -> 000002b790001038 System.Object[]
    -> 000002b78000d390 example.TestInfo
    -> 000002b78000d328 System.Reflection.RuntimeMethodInfo
    -> 000002b78000d1f8 System.RuntimeType+RuntimeTypeCache
    -> 000002b78000d1d0 System.RuntimeType
    -> 000002b78000ce40 System.Reflection.LoaderAllocator

Found 3 roots.
```

Im nächsten Schritt müssen Sie herausfinden, wo sich der Stamm befindet, damit Sie das Problem beheben können. Im einfachsten Fall ist der Stamm ein Stackslot oder ein Prozessorregister. In diesem Fall zeigt `gcroot` den Namen der Funktion an, deren Frame den Stamm und den Thread enthält, der diese Funktion ausführt. Ein schwieriger Fall liegt vor, wenn der Stamm eine statische Variable oder ein GC-Handle ist.

Im vorherigen Beispiel ist der erste Stamm eine lokale Variable vom Typ `System.Reflection.RuntimeMethodInfo`, die im Frame der Funktion `example.Program.Main(System.String[])` bei Adresse `rbp-20` gespeichert ist (`rbp` ist das Prozessorregister `rbp`, und -20 ist ein hexadezimaler Offset von diesem Register).

Der zweite Stamm ist ein normales (starkes) `GCHandle`, das einen Verweis auf eine Instanz der `test.Test`-Klasse enthält.

Der dritte Stamm ist ein fixiertes `GCHandle`. Es handelt sich hierbei tatsächlich um eine statische Variable, aber leider gibt es keine Möglichkeit, dies zu erkennen. Statische Variablen für Verweistypen werden in einem verwalteten Objektarray in internen Laufzeitstrukturen gespeichert.

Ein weiterer Fall, der das Entladen eines `AssemblyLoadContext` verhindern kann: Wenn ein Thread über einen Frame einer Methode aus einer Assembly verfügt, die in den `AssemblyLoadContext` auf ihrem Stapel geladen wurde. Sie können dies überprüfen, indem Sie die verwalteten Aufruflisten aller Threads sichern:

```console
~*e !clrstack
```

Der Befehl bedeutet „Befehl `!clrstack` auf alle Threads anwenden“. Die folgende Abbildung zeigt die Ausgabe dieses Befehls für das Beispiel. Leider bietet LLDB unter Unix keine Möglichkeit, einen Befehl auf alle Threads anzuwenden, sodass Sie die Threads manuell wechseln und den Befehl `clrstack` wiederholen müssen. Ignorieren Sie alle Threads, bei denen der Debugger „Unable to walk the managed stack“ (Verwalteter Stapel kann nicht durchlaufen werden) anzeigt.

```console
OS Thread Id: 0x6ba8 (0)
        Child SP               IP Call Site
0000001fc697d5c8 00007ffb50d9de12 [HelperMethodFrame: 0000001fc697d5c8] System.Diagnostics.Debugger.BreakInternal()
0000001fc697d6d0 00007ffa864765fa System.Diagnostics.Debugger.Break()
0000001fc697d700 00007ffa864736bc example.Program.Main(System.String[]) [E:\unloadability\example\Program.cs @ 70]
0000001fc697d998 00007ffae5fdc1e3 [GCFrame: 0000001fc697d998]
0000001fc697df28 00007ffae5fdc1e3 [GCFrame: 0000001fc697df28]
OS Thread Id: 0x2ae4 (1)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x61a4 (2)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x7fdc (3)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5390 (4)
Unable to walk the managed stack. The current thread is likely not a
managed thread. You can run !threads to get a list of managed threads in
the process
Failed to start stack walk: 80070057
OS Thread Id: 0x5ec8 (5)
        Child SP               IP Call Site
0000001fc70ff6e0 00007ffb5437f6e4 [DebuggerU2MCatchHandlerFrame: 0000001fc70ff6e0]
OS Thread Id: 0x4624 (6)
        Child SP               IP Call Site
GetFrameContext failed: 1
0000000000000000 0000000000000000
OS Thread Id: 0x60bc (7)
        Child SP               IP Call Site
0000001fc727f158 00007ffb5437fce4 [HelperMethodFrame: 0000001fc727f158] System.Threading.Thread.SleepInternal(Int32)
0000001fc727f260 00007ffb37ea7c2b System.Threading.Thread.Sleep(Int32)
0000001fc727f290 00007ffa865005b3 test.Program.ThreadProc() [E:\unloadability\test\Program.cs @ 17]
0000001fc727f2c0 00007ffb37ea6a5b System.Threading.Thread.ThreadMain_ThreadStart()
0000001fc727f2f0 00007ffadbc4cbe3 System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object)
0000001fc727f568 00007ffae5fdc1e3 [GCFrame: 0000001fc727f568]
0000001fc727f7f0 00007ffae5fdc1e3 [DebuggerU2MCatchHandlerFrame: 0000001fc727f7f0]

```

Wie Sie erkennen können, weist der letzte Thread `test.Program.ThreadProc()` auf. Dabei handelt es sich um eine Funktion aus der Assembly, die in den `AssemblyLoadContext` geladen wird, sodass der `AssemblyLoadContext` aktiv bleibt.

## <a name="example-source-with-unloadability-issues"></a>Beispielquellcode mit Problemen bei der Entladbarkeit

Der folgende Code wird im vorherigen Debugbeispiel verwendet.

### <a name="main-testing-program"></a>Haupttestprogramm

[!code-csharp[Main testing program](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_main.cs)]

## <a name="program-loaded-into-the-testassemblyloadcontext"></a>In den TestAssemblyLoadContext geladenes Programm

Der folgende Code stellt die Datei *test.dll* dar, die der `ExecuteAndUnload`-Methode im Haupttestprogramm übergeben wird.

[!code-csharp[Program loaded into the TestAssemblyLoadContext](~/samples/snippets/standard/assembly/unloading/unloadability_issues_example_test.cs)]
