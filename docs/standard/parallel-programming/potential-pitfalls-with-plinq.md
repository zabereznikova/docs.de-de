---
title: Potenzielle Fehler bei PLINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a>Potenzielle Fehler bei PLINQ
In vielen Fällen kann PLINQ erhebliche Leistungssteigerungen über sequenzielle LINQ to Objects-Abfragen bieten. Die Arbeit parallelisieren der Ausführung der Abfrage führt jedoch die Komplexität, die zu Problemen führen kann, die in sequenziellen Code sind nicht so üblich oder gar nicht auftreten. Dieses Thema enthält einige Methoden, um zu vermeiden, wenn Sie PLINQ-Abfragen schreiben.  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a>Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist.  
 In einigen Fällen Parallelisierung bewirkt, dass eine PLINQ-Abfrage langsamer als die LINQ in entsprechende Objekte ausgeführt. Einfache Faustregel ist, dass Abfragen mit wenigen Quellelementen und schnellen Benutzerdelegaten wahrscheinlich erheblich. Da viele Faktoren bei der Leistung beteiligt sind, empfehlen wir jedoch, dass tatsächlichen Ergebnisse zu messen, bevor Sie entscheiden, ob PLINQ verwenden. Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ (Grundlagen zur Beschleunigung in PLINQ)](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="avoid-writing-to-shared-memory-locations"></a>Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben.  
 Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben. Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen. Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung. Aus diesem Grund wird empfohlen, dass Sie vermeiden, oder mindestens begrenzen, den Zugriff auf gemeinsam genutzten Zustand in einer PLINQ-Abfrage so weit wie möglich.  
  
## <a name="avoid-over-parallelization"></a>Vermeiden Sie eine zu starke Parallelisierung.  
 Mithilfe der `AsParallel` -Operator, der Aufwand die quellauflistung Partitionierung und Synchronisieren von den Arbeitsthreads anfallen. Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt. Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung. Aus diesem Grund müssen Sie darauf achten, keine stark parallelisieren von einer Abfrage sein.  
  
 Das häufigste Szenario, in wie im folgenden Codeausschnitt dargestellt in geschachtelten Abfragen ist Parallelisierung übermäßige auftreten kann.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 In diesem Fall empfiehlt es sich um nur die äußere-Datenquelle (Kunden) zu parallelisieren, es sei denn, eine oder mehrere der folgenden Bedingungen gelten:  
  
-   Die interne Datenquelle (Cust. Bestellungen) ist bekannt, dass sehr lange.  
  
-   Sie führen für jede Bestellung eine umfangreiche Berechnung aus. (Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.)  
  
-   Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.  
  
 In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln. Weitere Informationen finden Sie unter [Vorgehensweise: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a>Vermeiden Sie den Aufruf nicht threadsicherer Methoden.  
 Schreiben in nicht Thread-sichere Instanzmethoden aus einer PLINQ kann Abfrage zur Beschädigung von Daten führen, die vielleicht aber u. u. nicht unerkannt bleiben in Ihrem Programm aktiviert. Dies kann auch zu Ausnahmen führen. Im folgenden Beispiel mehrere Threads versuchen werden würden, zum Aufrufen der `Filestream.Write` Methode gleichzeitig, die nicht von der Klasse unterstützt wird.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a>Beschränken Sie Aufrufe auf threadsichere Methoden.  
 Die meisten statischen Methoden in .NET Framework sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden. Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.  
  
> [!NOTE]
>  Sie können dies testen durch Einfügen von einigen Aufrufe <xref:System.Console.WriteLine%2A> in Ihren Abfragen. Obwohl diese Methode in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet wird, verwenden sie nicht in PLINQ-Abfragen.  
  
## <a name="avoid-unnecessary-ordering-operations"></a>Vermeiden Sie unnötige Sortiervorgänge.  
 Wenn PLINQ die Abfrage parallel ausgeführt wird, unterteilt er die Quellsequenz in Partitionen, die in mehreren Threads gleichzeitig bearbeitet werden können. Wird standardmäßig die Reihenfolge, in dem die Partitionen verarbeitet werden, und die Ergebnisse werden übermittelt, ist nicht vorhersagbar (mit Ausnahme von Operatoren wie `OrderBy`). Sie können PLINQ anweisen, die Reihenfolge der alle Quellsequenz beibehalten, aber dies wirkt sich negativ auf die Leistung. Die bewährte Methode wird nach Möglichkeit auf Struktur Abfragen, damit sie nicht auf die Beibehaltung der Reihenfolge abhängig sind. Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a>Lieber ForAll ForEach When möglich ist  
 PLINQ führt eine Abfrage zwar in mehreren Threads, wenn Sie, die Ergebnisse in Nutzen einer `foreach` Schleife (`For Each` in Visual Basic), und klicken Sie dann die Ergebnisse der Abfrage wieder in einen Thread zusammengeführt und seriell vom Enumerator zugegriffen werden müssen. In einigen Fällen ist dies unvermeidlich. Verwenden Sie jedoch nach Möglichkeit die `ForAll` Methode zum Aktivieren von jeder Thread eine eigene, z. B. ausgeben, durch Schreiben in eine threadsichere Auflistung wie z. B. <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.  
  
 Das gleiche Problem betrifft <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> also `source.AsParallel().Where().ForAll(...)` sollte stark bevorzugt werden.  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## <a name="be-aware-of-thread-affinity-issues"></a>Beachten Sie Threadaffinitätsprobleme.  
 Einige Technologien, z. B. COM-Interoperabilität für STA-Komponenten (Singlethread-Apartment), Windows Forms und Windows Presentation Foundation (WPF), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss. Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde. Wenn Sie versuchen, die gemeinsam verwendete Zustände eines Windows Forms-Steuerelements in einer PLINQ-Abfrage zuzugreifen, wird eine Ausnahme ausgelöst, wenn Sie im Debugger ausführen. (Diese Einstellung kann deaktiviert werden.) Jedoch, wenn die Abfrage an den UI-Thread genutzt wird, klicken Sie dann Sie erreichen das Steuerelement aus der `foreach` -Schleife, die die Abfrage listet verursacht, weil dieser Code in nur einem Thread ausgeführt wird.  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a>Gehen Sie nicht davon aus, dass Iterationen von „ForEach“, „For“ und „ForAll“ immer parallel ausgeführt werden.  
 Es ist wichtig zu beachten, dass einzelne Iterationen in einem <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> oder <xref:System.Linq.ParallelEnumerable.ForAll%2A> Schleife kann jedoch nicht parallel ausgeführt werden müssen. Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist.  
  
 Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
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
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
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
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
