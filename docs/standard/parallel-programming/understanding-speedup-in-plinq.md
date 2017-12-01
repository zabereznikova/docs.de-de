---
title: Grundlagen zur Beschleunigung in PLINQ
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
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a>Grundlagen zur Beschleunigung in PLINQ
Der primäre Zweck von PLINQ ist, um die Ausführung von LINQ to Objects-Abfragen beschleunigen, indem Sie die Delegaten für die Abfrage parallel auf Computern mit mehreren Kernen ausgeführt. PLINQ führt am besten auf, wenn die Verarbeitung der einzelnen Elemente in einer quellauflistung unabhängig, ohne gemeinsam genutzten Zustand zwischen den einzelnen Delegaten beteiligt ist. Solche Vorgänge sind häufig in LINQ to Objects und PLINQ und werden oft als "*Parallelschleife*", da sie gut für die Planung in mehreren Threads. Nicht alle Abfragen werden jedoch vollständig aus optimal parallelen Vorgängen bestehen; in den meisten Fällen umfasst eine Abfrage einige Operatoren, die entweder nicht parallelisiert werden, oder, die parallele Ausführung verlangsamt. Und auch bei Abfragen, die vollständig optimal parallel sind, PLINQ muss noch die Datenquelle partitionieren planen die Arbeit für die Threads und in der Regel die Ergebnisse zusammenführen, wenn die Abfrage abgeschlossen ist. Alle diese Vorgänge hinzufügen zu den Rechenaufwand für die Parallelisierung; Diese Kosten zum Hinzufügen von Parallelisierung heißen *Aufwand*. Zum Erzielen einer optimalen Leistung in einer PLINQ-Abfrage besteht das Ziel darin, die Teile, die optimal parallelen maximieren und minimieren die Teile, die Aufwand erfordern. Dieser Artikel enthält Informationen, mit denen Sie PLINQ-Abfragen schreiben, die noch keine richtigen Ergebnisse so effizient wie möglich sind.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>Faktoren, die Leistung von PLINQ-Abfragen auswirken.  
 In den folgenden Abschnitten werden einige der wichtigsten Faktoren, die diese Leistungseinbußen für die parallele Abfrage aufgeführt. Hierbei handelt es sich um allgemeine Anweisungen, die selbst nicht ausreichend, um die abfrageleistung in allen Fällen vorhergesagt werden. Wie immer, ist es wichtig, zum Messen der tatsächlichen Leistung auf Computern bestimmte Abfragen mit einer Reihe von repräsentative Konfigurationen und lädt.  
  
1.  Rechenaufwand für die gesamte Arbeit.  
  
     Um die Beschleunigung zu erreichen, benötigen eine PLINQ-Abfrage genügend optimal parallelen Arbeit, um den Mehraufwand auszugleichen. Die Arbeit kann als den Rechenaufwand für jeden Delegaten multipliziert mit der Anzahl der Elemente in der quellauflistung ausgedrückt werden. Vorausgesetzt, dass ein Vorgang kann, desto stärker rechnerisch parallelisiert werden teure es, größer ist die Gelegenheit für Beschleunigung. Wenn eine Funktion zum Ausführen einer Millisekunde ausgeführt wird, kann z. B. eine sequenzielle Abfrage mehr als 1000 Elemente einer Sekunde zum Ausführen dieses Vorgangs dauert, wohingegen eine parallele Abfrage auf einem Computer mit vier Kernen nur 250 Millisekunden dauern. Dies ergibt eine Beschleunigung von 750 Millisekunden. Bei Bedarf die Funktion einer Sekunde, die für jedes Element ausgeführt würde die Beschleunigung 750 Sekunden betragen. Wenn der Delegat sehr aufwendig ist, kann PLINQ erhebliche Beschleunigung mit nur wenige Elemente in der quellauflistung bieten. Im Gegensatz dazu sind kleine quellauflistung mit trivialen Delegaten im Allgemeinen nicht geeignet für PLINQ.  
  
     Im folgenden Beispiel ist QueryA wahrscheinlich ein guter Kandidat für PLINQ, vorausgesetzt, dass die Select-Funktion eine Menge Arbeit umfasst. QueryB ist wahrscheinlich nicht geeignet, da es nicht genügend Arbeitsvorgänge in der Select-Anweisung ist und der Aufwand der Parallelisierung wird die meisten oder alle der Beschleunigung der offset.  
  
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
  
2.  Die Anzahl der logischen Kerne im System (Grad an Parallelität).  
  
     Dieser Punkt ist eine offensichtliche begleitende im vorherigen Abschnitt, Abfragen, die optimal parallelen ausführen schneller auf Computern mit mehr Kerne, da die Arbeit auf mehrere gleichzeitige Threads aufgeteilt werden kann. Die Gesamtmenge an Beschleunigung hängt davon ab, welcher Prozentsatz der gesamten Arbeit der Abfrage parallelisiert wird. Sollte Sie jedoch nicht davon ausgegangen, dass alle Abfragen, zweimal so ausgeführt werden schnell auf einem Computer mit acht Kernen als eine vier-Core-Computer. Beim Abfragen für eine optimale Leistung zu optimieren, ist es wichtig, zum Messen der tatsächlichen Ergebnisse auf Computern mit einer unterschiedlichen Anzahl von Kernen. Dieser Punkt bezieht sich auf #1 zeigen: größeren Datasets sind erforderlich, um größere Computerressourcen nutzen.  
  
3.  Die Anzahl und Art der Vorgänge.  
  
     PLINQ stellt den AsOrdered-Operator für Situationen, in denen die Reihenfolge der Elemente in der Quellsequenz beibehalten werden muss. Es ist ein gewisser Aufwand verbunden mit der Reihenfolge, aber dieser Nachteil wird in der Regel sehr geringem. GROUP BY und Join-Vorgängen verursachen ebenso Verwaltungsaufwand. PLINQ führt am besten, wenn es zulässig ist, um Elemente in der quellauflistung in beliebiger Reihenfolge verarbeitet und an dem nächsten Operator übergeben werden, sobald sie bereit sind. Weitere Informationen finden Sie unter [Order Preservation in PLINQ (Beibehaltung der Reihenfolge in PLINQ)](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4.  Die Form der Ausführung einer Abfrage.  
  
     Wenn Sie die Ergebnisse einer Abfrage durch Aufrufen von ToArray oder ToList gespeichert sind, müssen die Ergebnisse von allen parallelen Threads in den einzelnen Datenstruktur zusammengeführt werden. Führen Sie dazu eine unvermeidbar rechnerischen Kosten. Wenn Sie die Ergebnisse mithilfe einer Foreach (For Each in Visual Basic)-Schleife durchlaufen, müssen die Ergebnisse von den Arbeitsthreads ebenso auf den Enumerator Thread serialisiert werden. Aber wenn Sie eine Aktion basierend auf dem Ergebnis von jedem Thread ausführen möchten, können Sie ForAll-Methode zum Durchführen dieser Aufgaben auf mehreren Threads verwenden.  
  
5.  Der Typ der Zusammenführungsoptionen.  
  
     PLINQ kann so konfiguriert werden, dass entweder die Ausgabe gepuffert und erzeugt es in Blöcken oder alle auf einmal nach dem das gesamte Resultset, oder sich auf einzelne Ergebnisse Datenstrom erzeugt wird, wie sie erstellt wurden. Das vorherige Ergebnis ist eine verringerte Gesamtausführungszeit und die zweite Ergebnisse in eine verringerte Latenz zwischen zurückgegebene Elemente.  Während die Zusammenführungsoptionen nicht immer eine erhebliche Auswirkungen auf die gesamtleistung der Abfrage verfügen, können sie wahrgenommene Leistung Auswirkungen, da sie, wie langen einen Benutzer steuern muss warten, um Ergebnisse anzuzeigen. Weitere Informationen finden Sie unter [Merge Options in PLINQ (Zusammenführungsoptionen in PLINQ)](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6.  Die Art der Partitionierung.  
  
     In einigen Fällen kann eine unausgeglichene Arbeitslast eine PLINQ-Abfrage über eine indizierbaren quellauflistung führen. In diesem Fall können Sie die abfrageleistung zu erhöhen, indem Sie einen benutzerdefinierten Partitionierer erstellen können. Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL (Benutzerdefinierte Partitionierer für PLINQ und TPL)](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## <a name="when-plinq-chooses-sequential-mode"></a>Wenn PLINQ den sequenziellen Modus auswählt  
 PLINQ versucht immer, führen Sie eine Abfrage mindestens so schnell, wie die Abfrage sequenziell ausgeführt würde. Obwohl PLINQ nicht wie rechenintensiv teuer sind die Benutzerdelegaten oder wie groß die Eingabequelle ist, es für bestimmte Abfrage "Shapes." angezeigt wird Insbesondere sucht nach Abfrageoperatoren oder Kombinationen aus Operatoren, die in der Regel eine auszuführende Abfrage langsamer im parallelen Modus verursachen. Wenn solche Formen gefunden wird, fällt PLINQ standardmäßig auf den sequenziellen Modus zurück.  
  
 Nach dem Messen der Leistung für eine bestimmte Abfrage können Sie jedoch feststellen, dass sie tatsächlich schneller im parallelen Modus ausgeführt wird. In solchen Fällen können Sie die <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> flag über die <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> aufzurufende Methode anzuweisen, die PLINQ zum parallelisieren der Abfrage. Weitere Informationen finden Sie unter [How to: Specify the Execution Mode in PLINQ (Vorgehensweise: Angeben des Ausführungsmodus in PLINQ)](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 Die folgende Liste beschreibt die Abfrageformen, die PLINQ standardmäßig in den sequenziellen Modus ausgeführt wird:  
  
-   Abfragen, die eine Select enthalten indiziert, indizierte SelectMany oder ElementAt-Klausel nach einer Sortierung oder Filterung-Operator, der ursprünglichen Indizes angeordnet oder entfernt wurde.  
  
-   Abfragen, die eine Take TakeWhile, überspringen SkipWhile-Operator enthalten und Indizes in der Quellsequenz sind nicht in der ursprünglichen Reihenfolge.  
  
-   Abfragen, die ZIP- oder SequenceEquals enthalten, es sei denn, eine der Datenquellen einen ursprünglich geordneten Index enthält und die andere Datenquelle indizierbar ist (d. h. ein Array oder eine IList(T)).  
  
-   Abfragen, die Concat enthalten, es sei denn, es indizierbaren Datenquellen angewendet wird.  
  
-   Abfragen, die enthalten umzukehren, es sei denn, die mit einer Datenquelle indizierbaren angewendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
