---
title: Grundlagen zur Beschleunigung in PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
ms.openlocfilehash: 07b5027d560a4caccc6c0a516c3f70c11df6be83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139906"
---
# <a name="understanding-speedup-in-plinq"></a>Grundlagen zur Beschleunigung in PLINQ
Der primäre Zweck von PLINQ ist die Beschleunigung der Ausführung von LINQ to Objects-Abfragen durch paralleles Ausführen der Abfragedelegaten auf Computern mit mehreren Kernen. PLINQ zeigt die beste Leistung, wenn die Verarbeitung der einzelnen Elemente in einer Quellsammlung unabhängig erfolgt, ohne gemeinsamen Zustand der einzelnen Delegaten. Solche Vorgänge sind häufig in LINQ to Objects und PLINQ und werden oft als „*optimal parallel*“ bezeichnet, da sie gut auf mehrere Threads verteilt werden können. Nicht alle Abfragen bestehen jedoch vollständig aus optimal parallel verarbeitbaren Vorgängen; in den meisten Fällen umfasst eine Abfrage einige Operatoren, die entweder nicht parallelisiert werden können oder die parallele Ausführung verlangsamen. Und auch bei optimal parallel verarbeitbaren Abfragen muss PLINQ noch die Datenquelle partitionieren, die Arbeit auf die Threads aufteilen und in der Regel die Ergebnisse zusammenführen, wenn die Abfrage abgeschlossen ist. Alle diese Vorgänge tragen zum Rechenaufwand für die Parallelisierung bei; dieser Aufwand zum Hinzufügen der Parallelisierung wird als *Mehraufwand* bezeichnet. Um optimale Leistung in einer PLINQ-Abfrage zu erzielen, besteht das Ziel darin, optimal parallel verarbeitbare Teile zu maximieren und Teile, die Mehraufwand erfordern, zu minimieren. Dieser Artikel enthält Informationen, mit deren Hilfe Sie PLINQ-Abfragen schreiben können, die so effizient wie möglich sind und nichtsdestoweniger richtige Ergebnisse liefern.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>Faktoren, die sich auf die PLINQ-Abfrageleistung auswirken  
 In den folgenden Abschnitten werden einige der wichtigsten Faktoren aufgeführt, die sich auf die Leistung der parallelen Abfrage auswirken. Hierbei handelt es sich um allgemeine Aussagen, die für sich allein nicht ausreichen, um die Abfrageleistung in allen Fällen vorherzusagen. Wie immer ist es wichtig, die tatsächliche Leistung bei bestimmten Abfragen auf Computern mit einer Reihe von repräsentativen Konfigurationen und Lasten zu messen.  
  
1. Rechenaufwand für die gesamte Arbeit.  
  
     Um die Beschleunigung zu erreichen, muss eine PLINQ-Abfrage zum Ausgleich des Mehraufwands in ausreichendem Maße optimal parallel verarbeitbar sein. Die Arbeit kann als Rechenaufwand für jeden Delegaten multipliziert mit der Anzahl der Elemente in der Quellsammlung ausgedrückt werden. Unter der Voraussetzung, dass ein Vorgang parallelisiert werden kann, ist die Gelegenheit zur Beschleunigung umso größer, je höher der Rechenaufwand für ihn ist. Wenn z.B. die Ausführung einer Funktion eine Millisekunde dauert, dauert die Anwendung dieser Funktion bei einer sequenziellen Abfrage von 1.000 Elementen eine Sekunde, bei einer parallelen Abfrage auf einem Computer mit vier Kernen vielleicht nur 250 Millisekunden. Dies ergibt eine Beschleunigung von 750 Millisekunden. Wenn die Ausführung der Funktion für jedes Element eine Sekunde beanspruchen würde, betrüge die Beschleunigung 750 Sekunden. Wenn der Delegat sehr aufwändig ist, könnte PLINQ mit nur wenigen Elementen in der Quellsammlung eine erhebliche Beschleunigung bieten. Im Gegensatz dazu eignen sich kleine Quellsammlungen mit trivialen Delegaten im Allgemeinen nicht gut für PLINQ.  
  
     Im folgenden Beispiel ist queryA wahrscheinlich ein guter Kandidat für PLINQ, vorausgesetzt, dass die Select-Funktion mit einer Menge Arbeit verbunden ist. Wahrscheinlich ist queryB kein guter Kandidat, weil die Select-Funktion nicht mit genügend Arbeit verbunden ist, und der Mehraufwand der Parallelisierung den Vorteil der Beschleunigung mindestens überwiegend, wenn nicht vollständig aufhebt.  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
    ```  
  
2. Die Anzahl der logischen Kerne im System (Grad an Parallelität).  
  
     Dieser Punkt ist eine offensichtliche logische Konsequenz des vorherigen Abschnitts; optimal parallel verarbeitbare Abfragen werden auf Computern mit mehr Kernen schneller ausgeführt, da die Arbeit auf mehrere parallele Threads aufgeteilt werden kann. Die Gesamtbeschleunigung hängt davon ab, welcher Prozentsatz der gesamten Abfragearbeit parallelisierbar ist. Gehen Sie jedoch nicht davon aus, dass alle Abfragen auf einem Computer mit acht Kernen doppelt so schnell ausgeführt werden wie auf einem Computer mit vier Kernen. Bei der Leistungsoptimierung von Abfragen kommt es darauf an, die tatsächlichen Ergebnisse auf Computern mit unterschiedlicher Anzahl von Kernen zu messen. Dieser Punkt steht im Zusammenhang mit Punkt 1: Zur Nutzung größerer Computeressourcen sind größere Datasets erforderlich.  
  
3. Anzahl und Art der Vorgänge.  
  
     PLINQ stellt den AsOrdered-Operator für Situationen bereit, in denen die Reihenfolge der Elemente in der Quellsequenz beibehalten werden muss. Mit der Sortierung ist ein gewisser Aufwand verbunden, aber dieser Nachteil ist in der Regel sehr gering. GroupBy- und Join-Vorgänge verursachen ebenso einen Mehraufwand. PLINQ bringt die beste Leistung, wenn Elemente in der Quellsammlung in beliebiger Reihenfolge verarbeitet und – sobald sie dazu bereit sind – an den nächsten Operator übergeben werden können. Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4. Die Form der Abfrageausführung.  
  
     Wenn Sie die Ergebnisse einer Abfrage durch Aufrufen von ToArray oder ToList speichern, müssen die Ergebnisse von allen parallelen Threads in der einzelnen Datenstruktur zusammengeführt werden. Dies ist mit unvermeidbarem Rechenaufwand verbunden. Ebenso müssen die Ergebnisse von den Arbeitsthreads auf den Enumeratorthread serialisiert werden, wenn Sie die Iteration über die Ergebnisse mithilfe einer foreach-Schleife („For Each“ in Visual Basic) durchführen. Aber wenn Sie eine Aktion einfach basierend auf dem Ergebnis jedes Threads ausführen möchten, können Sie diese Aufgabe mit der ForAll-Methode auf mehreren Threads durchführen.  
  
5. Der Typ der Mergeoptionen.  
  
     PLINQ kann entweder so konfiguriert werden, dass die Ausgabe gepuffert und nach dem Erzeugen des gesamten Resultsets in Blöcken oder im Ganzen bereitgestellt wird, oder dass einzelne Ergebnisse nach dem Erzeugen im Datenstrom bereitgestellt werden. Im ersten Fall wird die Gesamtausführungszeit verkürzt und im zweiten Fall die Latenzzeit zwischen den bereitgestellten Elementen.  Mergeoptionen haben zwar nicht immer erhebliche Auswirkungen auf die gesamte Abfrageleistung, können sich jedoch auf die wahrgenommene Leistung auswirken, da sie steuern, wie lange ein Benutzer warten muss, um Ergebnisse zu sehen. Weitere Informationen finden Sie unter [Merge Options in PLINQ (Zusammenführungsoptionen in PLINQ)](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6. Die Art der Partitionierung.  
  
     In einigen Fällen kann eine PLINQ-Abfrage einer indizierbaren Quellsammlung zu einer unausgeglichenen Arbeitslast führen. In diesem Fall können Sie die Abfrageleistung vielleicht erhöhen, indem Sie einen benutzerdefinierten Partitionierer erstellen. Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="when-plinq-chooses-sequential-mode"></a>Wenn PLINQ den sequenziellen Modus auswählt  
 PLINQ versucht immer, eine Abfrage mindestens so schnell auszuführen, als würde die Abfrage sequenziell ausgeführt. PLINQ beachtet zwar weder den Rechenaufwand der Benutzerdelegaten noch die Größe der Eingabequelle, sucht jedoch nach bestimmten „Abfrageformen“. Insbesondere wird nach Abfrageoperatoren oder Kombinationen aus Operatoren gesucht, die in der Regel die Ausführung einer Abfrage im parallelen Modus verlangsamen. Wenn solche Formen gefunden werden, fällt PLINQ standardmäßig auf den sequenziellen Modus zurück.  
  
 Vielleicht stellen Sie jedoch nach dem Messen der Leistung für eine bestimmte Abfrage fest, dass sie im parallelen Modus tatsächlich schneller ausgeführt wird. In solchen Fällen können Sie das <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType>-Flag mithilfe der <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>-Methode verwenden, um PLINQ anzuweisen, die Abfrage zu parallelisieren. Weitere Informationen finden Sie unter [How to: Specify the Execution Mode in PLINQ (Vorgehensweise: Angeben des Ausführungsmodus in PLINQ)](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 Die folgende Liste beschreibt die Abfrageformen, die PLINQ standardmäßig im sequenziellen Modus ausführt:  
  
- Abfragen, die eine Select-, indizierte Where-, indizierte SelectMany- oder ElementAt-Klausel nach einem Sortierungs- oder Filterungsoperator enthalten, der ursprüngliche Indizes entfernt oder angeordnet hat.  
  
- Abfragen, die einen Take-, TakeWhile-, Skip- und SkipWhile-Operator enthalten, und bei denen sich Indizes in der Quellsequenz nicht in der ursprünglichen Reihenfolge befinden.  
  
- Abfragen, die Zip oder SequenceEquals enthalten, es sei denn, eine der Datenquellen enthält einen ursprünglich geordneten Index, und die andere Datenquelle ist indizierbar – d.h. Array oder IList(T).  
  
- Abfragen, die Concat enthalten, sofern nicht auf indizierbare Datenquellen angewendet.  
  
- Abfragen, die Reverse enthalten, sofern nicht auf eine indizierbare Datenquelle angewendet.  
  
## <a name="see-also"></a>Weitere Informationen

- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
