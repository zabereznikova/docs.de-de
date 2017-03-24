---
title: "Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3b7318eb9853d633d152b93fafcf9570ccd03835
ms.lasthandoff: 03/13/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a>Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)
Abfrage- und Achsenoperationen werden oft so implementiert, dass sie die verzögerte Ausführung (Deferred Execution) verwenden. In diesem Thema werden die Voraussetzungen und die Vorteile der verzögerten Ausführung erläutert und einige Überlegungen zur Implementierung angestellt.  
  
## <a name="deferred-execution"></a>Verzögerte Ausführung  
 Verzögerte Ausführung bedeutet, die die Auswertung eines Ausdrucks, bis verzögert wird die *realisiert* Wert tatsächlich benötigt wird. Dort, wo große Datensammlungen bearbeitet werden müssen, vor allem in Programmen, die eine Reihe von verketteten Abfragen oder Manipulationen enthalten, kann die verzögerte Ausführung die Arbeitsgeschwindigkeit der Anwendung signifikant erhöhen. Im besten Fall muss bei der verzögerten Ausführung lediglich ein Durchlauf durch die Quellauflistung erfolgen.  
  
 Die LINQ-Technologien machen umfangreichen Gebrauch von der verzögerten Ausführung sowohl den Membern der <xref:System.Linq?displayProperty=fullName>Klassen und in die Erweiterungsmethoden in den verschiedenen LINQ-Namespaces, z. B. <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.</xref:System.Xml.Linq.Extensions?displayProperty=fullName> </xref:System.Linq?displayProperty=fullName>  
  
## <a name="eager-vs-lazy-evaluation"></a>Vergleich von sofortiger Auswertung und verzögerter Auswertung  
 Beim Schreiben einer Methode, die die verzögerte Ausführung implementiert, können Sie sich auch überlegen, ob die Methode mit verzögerter Auswertung (Lazy Evaluation) oder sofortiger Auswertung (Eager Evaluation) implementiert werden soll.  
  
-   In *verzögerte Auswertung*, ein einzelnes Element der Auflistung wird bei jedem Aufruf des Iterators verarbeitet. Dies ist die übliche Art und Weise, in der Iteratoren implementiert werden.  
  
-   In *sofortigen Auswertung*, führt der erste Aufruf des Iterators die gesamte Auflistung verarbeitet. Eventuell ist auch eine temporäre Kopie der Quellauflistung erforderlich. Zum Beispiel die <xref:System.Linq.Enumerable.OrderBy%2A>Methode muss die gesamte Auflistung erst sortieren, bevor es das erste Element zurückgibt.</xref:System.Linq.Enumerable.OrderBy%2A>  
  
 Die verzögerte Auswertung hat in der Regel eine höhere Arbeitsgeschwindigkeit zur Folge, weil die Verarbeitung des Mehraufwands gleichmäßig auf die Auswertung der Auflistung verteilt und die Verwendung temporärer Daten minimiert wird. Bei einigen Operationen führt aber natürlich kein Weg an der Materialisierung der Zwischenergebnisse vorbei.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die verzögerte Ausführung ist Gegenstand des nächsten Themas dieses Lernprogramms:  
  
-   [Beispiel für eine verzögerte Ausführung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm: Verzögerte Ausführung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)   
 [Konzepte und Terminologie (funktionale Transformation) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)   
 [Aggregationsoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
