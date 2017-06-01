---
title: "Understanding Speedup in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, performance tuning"
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Understanding Speedup in PLINQ
Der primäre Zweck von PLINQ besteht darin, die Ausführung von LINQ to Objects\-Abfragen zu beschleunigen, indem die Abfragedelegaten parallel auf Multikerncomputern ausgeführt werden.  Die beste Leistung erzielt PLINQ, wenn die Verarbeitung jedes Elements in einer Quellauflistung unabhängig ist und in den einzelnen Delegaten kein Freigabezustand enthalten ist.  Solche Vorgänge werden in LINQ to Objects und PLINQ häufig ausgeführt, und sie werden oftmals als "*optimal parallel*" bezeichnet, da sie gut für die Planung in mehreren Threads geeignet sind.  Allerdings bestehen nicht alle Abfragen vollständig aus optimal parallelen Vorgängen. In den meisten Fällen enthält eine Abfrage einige Operatoren, die entweder nicht parallelisiert werden können oder die die parallele Ausführung verlangsamen.  Auch bei Abfragen, die vollständig optimal parallel sind, muss PLINQ nach wie vor die Datenquelle partitionieren und die Arbeit in den Threads planen. Zudem müssen normalerweise die Ergebnisse bei Abschluss der Abfrage zusammengeführt werden.  Alle diese Vorgänge erhöhen den Rechenaufwand für die Parallelisierung. Diese Schritte zum Hinzufügen der Parallelisierung werden als *Mehraufwand* bezeichnet.  Um in einer PLINQ\-Abfrage die optimale Leistung zu erzielen, müssen die optimal parallelen Teile maximiert und die Teile minimiert werden, die Mehraufwand erfordern.  Dieser Artikel enthält Informationen zum Schreiben von PLINQ\-Abfragen, die möglichst effizient sind und dabei dennoch korrekte Ergebnisse liefern.  
  
## Faktoren, die sich auf die PLINQ\-Abfrageleistung auswirken  
 In den folgenden Abschnitten sind einige der wichtigsten Faktoren aufgeführt, die sich auf die parallele Abfrageleistung auswirken.  Dabei handelt es sich um allgemeine Aussagen, die nicht in jedem Fall eine zuverlässige Prognose der Abfrageleistung ermöglichen.  Wie immer muss die tatsächliche Leistung bestimmter Abfragen auf Computern mit einem Spektrum repräsentativer Konfigurationen und Ladevorgänge gemessen werden.  
  
1.  Rechnungsaufwand für die Gesamtarbeit.  
  
     Zur Erhöhung der Geschwindigkeit muss eine PLINQ\-Abfrage über ein ausreichendes Maß an optimal paralleler Arbeit verfügen, um den Mehraufwand auszugleichen.  Die Arbeit kann folgendermaßen ausgedrückt werden: Rechnungsaufwand für jeden Delegaten multipliziert mit der Anzahl der Elemente in der Quellauflistung.  Unter der Voraussetzung, dass ein Vorgang parallelisiert werden kann, steigt mit höherem Rechenaufwand die Wahrscheinlichkeit, Geschwindigkeitssteigerungen zu erzielen.  Wenn die Ausführung einer Funktion z. B. eine Millisekunde in Anspruch nimmt, dauert eine sequenzielle Abfrage von 1.000 Elementen eine Sekunde, wohingegen eine parallele Abfrage auf einem Computer mit vier Kernen unter Umständen nur 250 Millisekunden dauert.  Dies ergibt eine Geschwindigkeitssteigerung von 750 Millisekunden.  Wenn die Funktion für die Ausführung jedes Elements eine Sekunde benötigen würde, betrüge die Geschwindigkeitssteigerung 750 Sekunden.  Wenn der Delegat sehr aufwändig ist, können von PLINQ mit nur einigen Elementen in der Quellauflistung deutliche Geschwindigkeitssteigerungen erzielt werden.  Umgekehrt sind kleine Quellauflistungen mit einfachen Delegaten im Allgemeinen nicht gut für PLINQ geeignet.  
  
     Im folgenden Beispiel ist queryA wahrscheinlich gut für PLINQ und wird, dass die Select\-Funktion. queryB ist wahrscheinlich weniger gut geeignet, da die Arbeitsmenge in der Select\-Anweisung gibt, und durch den Mehraufwand aufgrund der Parallelisierung der Geschwindigkeitszuwachs größtenteils oder vollständig aus.  
  
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
  
2.  Die Anzahl der logischen Kerne im System \(Grad des Parallelismus\).  
  
     Dieser Punkt ist eine offensichtliche Begleiterscheinung des vorherigen Abschnitts. Abfragen, die optimal parallel sind, werden auf Computern mit mehr Kernen schneller ausgeführt, da die Arbeit unter einer größeren Anzahl gleichzeitiger Threads aufgeteilt werden kann.  Die gesamte erzielbare Geschwindigkeitssteigerung hängt davon ab, welcher Anteil der Gesamtarbeit der Abfrage parallelisiert werden kann.  Gehen Sie jedoch nicht davon aus, dass alle Abfragen auf einem Computer mit acht Kernen doppelt so schnell wie auf einem Computer mit vier Kernen ausgeführt werden.  Wenn Abfragen auf optimale Leistung hin optimiert werden, müssen die tatsächlichen Ergebnisse auf Computern mit einer unterschiedlichen Anzahl von Kernen gemessen werden.  Dieser Punkt bezieht sich auf Punkt 1: Größere Datasets sind erforderlich, um größere Computerressourcen nutzen zu können.  
  
3.  Die Anzahl und Art der Vorgänge.  
  
     PLINQ stellt den AsOrdered\-Operator für Situationen bereit, in denen die Reihenfolge der Elemente in der Quellsequenz aufrechterhalten werden muss.  Sortierungen verursachen Aufwand, der jedoch in der Regel gering ist.  GroupBy\- und Join\-Vorgänge verursachen gleichermaßen Mehraufwand.  Die beste Leistung wird mit PLINQ erzielt, wenn Elemente in der Quellauflistung in beliebiger Reihenfolge verarbeitet und an den nächsten Operator übergeben werden dürfen, sobald sie bereit sind.  Weitere Informationen finden Sie unter [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4.  Die Form der Abfrageausführung.  
  
     Wenn Sie die Ergebnisse einer Abfrage speichern, indem Sie ToArray oder ToList aufrufen, müssen die Ergebnisse aus allen parallelen Threads in der einzelnen Datenstruktur zusammengeführt werden.  Zusätzlicher Rechenaufwand ist hier unvermeidlich.  Wenn die Ergebnisse mit einer foreach\-Schleife \("For Each" in Visual Basic\) durchlaufen werden, müssen die Ergebnisse aus den Arbeitsthreads ebenfalls im Enumeratorthread serialisiert werden.  Wenn Sie jedoch nur auf Grundlage des Ergebnisses aus jedem Thread einige Aktionen ausführen möchten, können Sie die Arbeit mithilfe der ForAll\-Methode in mehreren Threads ausführen.  
  
5.  Der Typ der Zusammenführungsoptionen.  
  
     PLINQ kann so konfiguriert werden, dass entweder die Ausgabe gepuffert und in Blöcken erzeugt wird, oder dass alle Vorgänge auf einmal ausgeführt werden, nachdem das gesamte Resultset erzeugt wurde. Eine andere Möglichkeit besteht darin, einzelne Ergebnisse bei deren Erstellung zu streamen.  Ergebnis der ersten Variante ist eine geringere Gesamtausführungszeit, wohingegen die zweite Variante eine verringerte Latenz zwischen übergebenen Elementen zur Folge hat.  Während die Zusammenführungsoptionen nicht immer größere Auswirkungen auf die allgemeine Abfrageleistung haben, können sie die wahrgenommene Leistung beeinflussen, da sie bestimmen, wie lang ein Benutzer auf Ergebnisse warten muss.  Weitere Informationen finden Sie unter [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6.  Die Art der Partitionierung.  
  
     In einigen Fällen führt eine PLINQ\-Abfrage über eine indizierbare Quellauflistung möglicherweise zu einer unausgeglichenen Arbeitslast.  In diesem Fall können Sie die Abfrageleistung ggf. durch Erstellen eines benutzerdefinierten Partitionierers verbessern.  Weitere Informationen finden Sie unter [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Wenn PLINQ den sequenziellen Modus auswählt  
 PLINQ versucht immer, eine Abfrage mindestens so schnell auszuführen, wie es bei einer sequenziellen Ausführung der Abfrage der Fall ist.  Obwohl PLINQ nicht berücksichtigt, wie rechenintensiv die Benutzerdelegaten sind, oder wie groß die Eingabequelle ist, wird nach bestimmten "Abfrageformen" gesucht. Insbesondere wird nach Abfrageoperatoren oder Kombinationen aus Operatoren gesucht, die normalerweise eine langsamere Ausführung einer Abfrage im parallelen Modus zur Folge haben.  Wenn solche Formen gefunden werden, greift PLINQ standardmäßig auf den sequenziellen Modus zurück.  
  
 Nach dem Messen der Leistung einer bestimmten Abfrage stellen Sie jedoch möglicherweise fest, dass die Abfrage im parallelen Modus schneller ausgeführt wird.  In solchen Fällen können Sie PLINQ mit dem <xref:System.Linq.ParallelExecutionMode?displayProperty=fullName>\-Flag über die <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>\-Methode anweisen, die Abfrage zu parallelisieren.  Weitere Informationen finden Sie unter [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 In der folgenden Liste werden die Abfrageformen beschrieben, die PLINQ standardmäßig im sequenziellen Modus ausführt:  
  
-   Abfragen, die eine Select\-, eine indizierte Where\-, eine indizierte SelectMany\- oder eine ElementAt\-Klausel nach einem Sortierungs\- oder Filterungsoperator enthalten, von dem die ursprünglichen Indizes entfernt oder neu angeordnet wurden.  
  
-   Abfragen, die einen Take\-, TakeWhile\-, Skip\- oder SkipWhile\-Operator enthalten und in denen Indizes in der Quellsequenz nicht in der ursprünglichen Reihenfolge vorhanden sind.  
  
-   Abfragen, die ZIP oder SequenceEquals enthalten, es sei denn, eine der Datenquellen einen ursprünglich sortierten Index besitzt und die, andere Datenquelle indizierbar ist \(d. ein Array oder IList \(T\)\).  
  
-   Abfragen, die Concat enthalten, sofern es nicht für indizierbare Datenquellen übernommen wird.  
  
-   Abfragen, die Reverse enthalten, sofern es nicht für eine indizierbare Datenquelle übernommen wird.  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)