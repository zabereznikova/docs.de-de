---
title: "Potential Pitfalls with PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, pitfalls"
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Potential Pitfalls with PLINQ
In vielen Fällen ermöglicht PLINQ bedeutende Leistungssteigerungen gegenüber sequenziellen LINQ to Objects\-Abfragen.  Die Parallelisierung der Abfrageausführung erhöht jedoch die Komplexität des Vorgangs, was Probleme nach sich ziehen kann, die in sequenziellem Code weniger häufig oder garnicht vorkommen.  In diesem Thema sind bestimmte Fehlerquellen aufgeführt, die beim Schreiben von PLINQ\-Abfragen vermieden werden sollten.  
  
## Gehen Sie nicht davon aus, dass eine parallele Ausführung immer schneller ist.  
 Die Parallelisierung kann zur Folge haben, dass eine PLINQ\-Abfrage langsamer als die äquivalente LINQ to Objects\-Abfrage ausgeführt wird.  Eine Faustregel besagt, dass die Geschwindigkeit von Abfragen mit wenigen Quellelementen und schnellen Benutzerdelegaten wahrscheinlich kaum zunimmt.  Da jedoch viele Faktoren die Leistung beeinflussen, sollten Sie die tatsächlichen Ergebnisse messen, bevor Sie sich für oder gegen die Verwendung von PLINQ entscheiden.  Weitere Informationen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Vermeiden Sie es, in gemeinsam genutzte Speicherpositionen zu schreiben.  
 Bei sequenziellem Code wird regelmäßig aus statischen Variablen oder Klassenfeldern gelesen bzw. in diese geschrieben.  Wenn jedoch mehrere Threads gleichzeitig auf diese Variablen zugreifen, besteht eine hohe Wahrscheinlichkeit für Racebedingungen.  Sie können den Zugriff auf die Variable mithilfe von Sperren zwar synchronisieren, die Synchronisierung geht jedoch zu Lasten der Leistung.  Es empfiehlt sich daher, den Zugriff auf den Freigabezustand in einer PLINQ\-Abfrage zu vermeiden oder so weit wie möglich einzuschränken.  
  
## Vermeiden Sie eine zu starke Parallelisierung.  
 Mit dem `AsParallel`\-Operator übernehmen Sie die Mehrkosten für das Partitionieren der Quellauflistung und das Synchronisieren der Arbeitsthreads.  Die Vorteile der Parallelisierung werden zudem durch die Anzahl der Prozessoren auf dem Computer beschränkt.  Die Ausführung von mehreren rechnergebundenen Threads auf nur einem Prozessor ermöglicht keine Geschwindigkeitssteigerung.  Seien Sie daher vorsichtig, dass Sie eine Abfrage nicht zu stark parallelisieren.  
  
 Eine zu starke Parallelisierung tritt vor allem in geschachtelten Abfragen auf, wie im folgenden Ausschnitt angezeigt.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 In diesem Fall sollte am besten nur die äußere Datenquelle \(Kunden\) parallelisiert werden, außer eine oder mehrere der folgenden Bedingungen sind erfüllt:  
  
-   Die innere Datenquelle \(cust.Orders\) ist sehr lang.  
  
-   Sie führen für jede Bestellung eine umfangreiche Berechnung aus. \(Der im Beispiel gezeigte Vorgang ist nicht sehr rechenintensiv.\)  
  
-   Das Zielsystem verfügt über genug Prozessoren für die Verarbeitung der Anzahl von Threads, die durch die Parallelisierung der Abfrage von `cust.Orders` erzeugt werden.  
  
 In allen diesen Fällen empfiehlt es sich, die optimale Abfrageform mithilfe von Tests und Messungen zu ermitteln.  Weitere Informationen finden Sie unter [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).  
  
## Vermeiden Sie den Aufruf nicht threadsicherer Methoden.  
 Das Schreiben in nicht threadsichere Instanzmethoden von einer PLINQ\-Abfrage aus kann zu Datenbeschädigung führen, die im Programm möglicherweise unerkannt bleiben.  Dies kann Ausnahmen zur Folge haben.  Im folgenden Beispiel würden mehrere Threads gleichzeitig versuchen, die `Filestream.Write`\-Methode aufzurufen, was von der Klasse nicht unterstützt wird.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## Beschränken Sie Aufrufe auf threadsichere Methoden.  
 Die meisten statischen Methoden in .NET Framework sind threadsicher und können von mehreren Threads gleichzeitig aufgerufen werden.  Die damit verbundene Synchronisierung kann jedoch auch in diesen Fällen zu einer erheblichen Verlangsamung der Abfrage führen.  
  
> [!NOTE]
>  Sie können dies testen, indem Sie in den Abfragen Aufrufe von <xref:System.Console.WriteLine%2A> einfügen.  Diese Methode wird jedoch nur in den Dokumentationsbeispielen zu Demonstrationszwecken verwendet. Nutzen Sie sie nicht in PLINQ\-Abfragen.  
  
## Vermeiden Sie unnötige Sortiervorgänge.  
 Wenn PLINQ eine Abfrage parallel ausführt, wird die Quellsequenz in Partitionen unterteilt, die gleichzeitig in mehreren Threads verarbeitet werden können.  Standardmäßig ist die Reihenfolge, in der die Partitionen verarbeitet und die Ergebnisse zurückgegeben werden, nicht vorhersagbar \(außer bei Vorgängen wie `OrderBy`\).  Sie können PLINQ anweisen, die Reihenfolge einer beliebigen Quellsequenz beizubehalten, dies beeinträchtigt jedoch die Leistung.  Am besten ist es, Abfragen so zu strukturieren, dass eine Beibehaltung der Reihenfolge nicht notwendig ist.  Weitere Informationen finden Sie unter [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
## Verwenden Sie nach Möglichkeit ForAll anstatt ForEach.  
 PLINQ führt eine Abfrage zwar in mehreren Threads aus, wenn Sie die Ergebnisse in einer `foreach`\-Schleife \(`For Each` in Visual Basic\) nutzen, müssen die Abfrageergebnisse zurück in einen Thread zusammengeführt und seriell vom Enumerator aufgerufen werden.  In einigen Fällen ist dies unvermeidlich. Verwenden Sie jedoch nach Möglichkeit die `ForAll`\-Methode, damit jeder Thread eigene Ergebnisse ausgibt, z. B. durch das Schreiben in eine threadsichere Auflistung wie <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>.  
  
 Das gleiche Problem tritt bei <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>, das heißt `source.AsParallel().Where().ForAll(...)` stark bevorzugt werden sollte zu  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## Beachten Sie Threadaffinitätsprobleme.  
 Einige Technologien, z. B. COM\-Interoperabilität für STA\-Komponenten \(Singlethread\-Apartment\), Windows Forms und Windows Presentation Foundation \(WPF\), erzeugen Threadaffinitätseinschränkungen, aufgrund derer Code in einem bestimmten Thread ausgeführt werden muss.  Beispielsweise kann sowohl in Windows Forms als auch in WPF nur in einem Thread auf ein Steuerelement zugegriffen werden, in dem es erstellt wurde.  Bei dem Versuch, auf den Freigabezustand eines Windows Forms\-Steuerelements in eine PLINQ\-Abfrage zuzugreifen, wird eine Ausnahme ausgelöst, wenn Sie den Debugger ausführen. \(Diese Einstellung kann deaktiviert werden.\) Wenn die Abfrage jedoch im UI\-Thread genutzt wird, können Sie von der `foreach`\-Schleife, die die Abfrageergebnisse auflistet, auf das Steuerelement zugreifen, da dieser Code auf in einem Thread ausgeführt wird.  
  
## Gehen Sie nicht davon aus, dass Iterationen von "ForEach", "For" und "ForAll" immer parallel ausgeführt werden.  
 Berücksichtigen Sie, dass einzelne Iterationen in einer <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>\-Schleife, einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>\-Schleife oder einer <xref:System.Linq.ParallelEnumerable.ForAll%2A>\-Schleife möglicherweise, jedoch nicht zwingend, parallel ausgeführt werden.  Schreiben Sie daher nach Möglichkeit keinen Code, dessen Korrektheit von der parallelen Ausführung von Iterationen oder der Ausführung von Iterationen in einer bestimmten Reihenfolge abhängig ist.  
  
 Beim folgenden Code ist z. B. ein Deadlock wahrscheinlich:  
  
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
  
 In diesem Beispiel wird durch eine Iteration ein Ereignis festgelegt, und alle anderen Iterationen warten auf das Ereignis.  Die wartenden Iterationen können erst nach Abschluss der Ereigniseinstellungsiteration abgeschlossen werden.  Es ist jedoch möglich, dass die wartenden Iterationen alle Threads blockieren, die zur Ausführung der parallelen Schleife verwendet werden, bevor die Ereigniseinstellungsiteration überhaupt ausgeführt werden kann.  Dies führt zu einem Deadlock. Die Ereigniseinstellungsiteration wird niemals ausgeführt, und die wartenden Iterationen werden zu keinem Zeitpunkt aktiviert.  
  
 Insbesondere sollte eine Iteration einer parallelen Schleife nie auf den Fortschritt einer anderen Iteration der Schleife warten.  Wenn von der parallelen Schleife entschieden wird, die Iterationen sequenziell zu planen, jedoch in der entgegengesetzten Reihenfolge, tritt ein Deadlock auf.  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)