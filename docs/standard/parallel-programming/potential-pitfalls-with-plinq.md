---
title: Potenzielle Fehler bei PLINQ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
ms.openlocfilehash: 1e1763132cd0ee8f1135e562c36ce4adf603f5af
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822242"
---
# <a name="potential-pitfalls-with-plinq"></a>Potenzielle Fehler bei PLINQ

In vielen Fällen kann PLINQ erhebliche Leistungssteigerungen gegenüber sequenziellen LINQ to Objects-Abfragen bieten. Die Parallelisierung der Abfragenausführung erhöht jedoch die Komplexität des Vorgangs, was Probleme nach sich ziehen kann, die in sequenziellem Code weniger häufig oder gar nicht vorkommen. In diesem Thema sind bestimmte Fehlerquellen aufgeführt, die beim Schreiben von PLINQ-Abfragen vermieden werden sollten.

## <a name="dont-assume-that-parallel-is-always-faster"></a>Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist

In einigen Fällen bewirkt Parallelisierung, dass eine PLINQ-Abfrage langsamer als die entsprechende LINQ to Objects-Abfrage ausgeführt wird. Eine Faustregel besagt, dass die Geschwindigkeit von Abfragen mit wenigen Quellelementen und schnellen Benutzerdelegaten wahrscheinlich kaum zunimmt. Da jedoch viele Faktoren Einfluss auf die Leistung haben, sollten Sie immer die tatsächlichen Ergebnisse messen, bevor Sie über die Verwendung von PLINQ entscheiden. Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ (Grundlagen zur Beschleunigung in PLINQ)](understanding-speedup-in-plinq.md).

## <a name="avoid-writing-to-shared-memory-locations"></a>Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben

Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben. Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen. Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung. Es empfiehlt sich daher, den Zugriff auf den Freigabezustand in einer PLINQ-Abfrage zu vermeiden oder so weit wie möglich einzuschränken.

## <a name="avoid-over-parallelization"></a>Vermeiden Sie eine zu starke Parallelisierung

Mithilfe der `AsParallel`-Methode übernehmen Sie den Mehraufwand für das Partitionieren der Quellsammlung und das Synchronisieren der Arbeitsthreads. Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt. Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung. Achten Sie daher darauf, dass Sie eine Abfrage nicht zu stark parallelisieren.

Eine zu starke Parallelisierung tritt vor allem in geschachtelten Abfragen auf, wie im folgenden Codeausschnitt gezeigt.

[!code-csharp[PLINQ#20](~/samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
[!code-vb[PLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]

In diesem Fall sollte idealerweise nur die äußere Datenquelle (customers) parallelisiert werden, sofern nicht eine oder mehrere der folgenden Bedingungen erfüllt sind:

- Von der internen Datenquelle (cust.Orders) ist bekannt, dass sie sehr groß ist.

- Sie führen für jede Bestellung eine umfangreiche Berechnung aus. (Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.)

- Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.

In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln. Weitere Informationen finden Sie unter [Vorgehensweise: Messen der Leistung von PLINQ-Abfragen](how-to-measure-plinq-query-performance.md).

## <a name="avoid-calls-to-non-thread-safe-methods"></a>Vermeiden Sie den Aufruf nicht threadsicherer Methoden

Das Schreiben in nicht threadsichere Instanzmethoden von einer PLINQ-Abfrage aus kann zu Datenbeschädigungen führen, die im Programm möglicherweise unerkannt bleiben. Dies kann auch zu Ausnahmen führen. Im folgenden Beispiel würden mehrere Threads gleichzeitig versuchen, die `FileStream.Write`-Methode aufzurufen, was von der Klasse nicht unterstützt wird.

```vb
Dim fs As FileStream = File.OpenWrite(…)
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))
```

```csharp
FileStream fs = File.OpenWrite(...);
a.AsParallel().Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));
```

## <a name="limit-calls-to-thread-safe-methods"></a>Beschränken Sie Aufrufe auf threadsichere Methoden

Die meisten statischen Methoden in .NET sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden. Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.

> [!NOTE]
> Sie können dies testen, indem Sie in Ihre Abfragen Aufrufe von <xref:System.Console.WriteLine%2A> einfügen. Diese Methode wird jedoch nur in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet. Nutzen Sie sie nicht in PLINQ-Abfragen.

## <a name="avoid-unnecessary-ordering-operations"></a>Vermeiden Sie unnötige Sortiervorgänge

Wenn PLINQ eine Abfrage in Parallelverarbeitung ausführt, wird die Quellsequenz in Partitionen unterteilt, die parallel auf mehreren Threads verarbeitet werden können. Standardmäßig ist die Reihenfolge, in der die Partitionen verarbeitet und die Ergebnisse übermittelt werden, nicht vorhersagbar (außer für Operatoren wie `OrderBy`). Sie können PLINQ anweisen, die Reihenfolge aller Quellsequenzen beizubehalten, aber dies wirkt sich negativ auf die Leistung aus. Die bewährte Methode besteht darin, Abfragen nach Möglichkeit so zu strukturieren, dass sie nicht von der Beibehaltung der Reihenfolge abhängig sind. Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](order-preservation-in-plinq.md).

## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Bevorzugen Sie nach Möglichkeit „ForAll“ gegenüber „ForEach“

PLINQ führt eine Abfrage zwar in mehreren Threads aus, doch wenn Sie die Ergebnisse in einer `foreach`-Schleife (`For Each` in Visual Basic) verarbeiten, müssen die Ergebnisse der Abfrage wieder in einem Thread zusammengeführt werden, und der Enumerator muss seriell darauf zugreifen. In einigen Fällen ist dies unvermeidlich. Verwenden Sie jedoch nach Möglichkeit die `ForAll`-Methode, um zu ermöglichen, dass jeder Thread seine eigenen Ergebnisse ausgibt, z.B. durch Schreiben in eine threadsichere Sammlung wie <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.

Dieses Problem gilt auch für <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Mit anderen Worten, `source.AsParallel().Where().ForAll(...)` sollte stark bevorzugt werden gegenüber `Parallel.ForEach(source.AsParallel().Where(), ...)`.

## <a name="be-aware-of-thread-affinity-issues"></a>Beachten Sie Threadaffinitätsprobleme

Einige Technologien, z. B. COM-Interoperabilität für STA-Komponenten (Singlethread-Apartment), Windows Forms und Windows Presentation Foundation (WPF), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss. Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde. Wenn Sie versuchen, in einer PLINQ-Abfrage auf den Freigabezustand eines Windows Forms-Steuerelements zuzugreifen, wird eine Ausnahme ausgelöst, wenn Sie den Debugger ausführen. (Diese Einstellung kann deaktiviert werden.) Wenn die Abfrage jedoch im Benutzeroberflächenthread verarbeitet wird, können Sie über die `foreach`-Schleife, die die Abfrageergebnisse aufzählt, auf das Steuerelement zugreifen, weil dieser Code in nur einem Thread ausgeführt wird.

## <a name="dont-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Gehen Sie nicht davon aus, dass Iterationen von „ForEach“, „For“ und „ForAll“ immer parallel ausgeführt werden.

Beachten Sie unbedingt, dass einzelne Iterationen in einer <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>- oder <xref:System.Linq.ParallelEnumerable.ForAll%2A>-Schleife parallel ausgeführt werden können, jedoch nicht parallel ausgeführt werden müssen. Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist.

Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:

```vb
Dim mre = New ManualResetEventSlim()
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll(Sub(j)
   If j = Environment.ProcessorCount Then
       Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Set()
   Else
       Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)
       mre.Wait()
   End If
End Sub) ' deadlocks
```

```csharp
ManualResetEventSlim mre = new ManualResetEventSlim();
Enumerable.Range(0, Environment.ProcessorCount * 100).AsParallel().ForAll((j) =>
{
    if (j == Environment.ProcessorCount)
    {
        Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Set();
    }
    else
    {
        Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);
        mre.Wait();
    }
}); //deadlocks
```

In diesem Beispiel wird durch eine Iteration ein Ereignis festgelegt, und alle anderen Iterationen warten auf das Ereignis. Die wartenden Iterationen können erst nach Abschluss der ereignisauslösenden Iteration abgeschlossen werden. Es ist jedoch möglich, dass die wartenden Iterationen alle Threads blockieren, die zur Ausführung der parallelen Schleife verwendet werden, bevor die ereignisauslösende Iteration überhaupt ausgeführt werden kann. Dies führt zu einem Deadlock. Die ereignisauslösende Iteration wird niemals ausgeführt, und die wartenden Iterationen werden zu keinem Zeitpunkt aktiviert.

Insbesondere sollte eine Iteration einer parallelen Schleife nie auf den Fortschritt einer anderen Iteration der Schleife warten. Wenn von der parallelen Schleife entschieden wird, die Iterationen sequenziell zu planen, jedoch in der entgegengesetzten Reihenfolge, tritt ein Deadlock auf.

## <a name="see-also"></a>Siehe auch

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](introduction-to-plinq.md)
