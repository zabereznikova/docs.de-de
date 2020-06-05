---
title: Verzögerte Ausführung und Auswertung in LINQ to XML
ms.date: 07/20/2015
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
ms.openlocfilehash: 98a5010de6ea7ef46d845c6a921c54d4e7692370
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410811"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a>Verzögerte Ausführung und verzögerte Auswertung in LINQ to XML (Visual Basic)
Abfrage- und Achsenoperationen werden oft so implementiert, dass sie die verzögerte Ausführung (Deferred Execution) verwenden. In diesem Thema werden die Voraussetzungen und die Vorteile der verzögerten Ausführung erläutert und einige Überlegungen zur Implementierung angestellt.  
  
## <a name="deferred-execution"></a>Verzögerte Ausführung  
 Verzögerte Ausführung bedeutet, dass die Auswertung eines Ausdrucks so lange hinausgezögert wird, bis dessen *realisierter* Wert tatsächlich benötigt wird. Dort, wo große Datensammlungen bearbeitet werden müssen, vor allem in Programmen, die eine Reihe von verketteten Abfragen oder Manipulationen enthalten, kann die verzögerte Ausführung die Arbeitsgeschwindigkeit der Anwendung signifikant erhöhen. Im besten Fall muss bei der verzögerten Ausführung lediglich ein Durchlauf durch die Quellauflistung erfolgen.  
  
 Die LINQ-Technologien machen von der verzögerten Ausführung umfangreichen Gebrauch, und dies sowohl bei den Membern der <xref:System.Linq?displayProperty=nameWithType>-Kernklassen als auch bei den Erweiterungsmethoden in den verschiedenen LINQ-Namespaces, z. B. <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.  
  
## <a name="eager-vs-lazy-evaluation"></a>Vergleich von sofortiger Auswertung und verzögerter Auswertung  
 Beim Schreiben einer Methode, die die verzögerte Ausführung implementiert, können Sie sich auch überlegen, ob die Methode mit verzögerter Auswertung (Lazy Evaluation) oder sofortiger Auswertung (Eager Evaluation) implementiert werden soll.  
  
- Bei der *verzögerten Auswertung* wird bei jedem Aufruf des Iterators jeweils ein Element der Quellauflistung verarbeitet. Dies ist die übliche Art und Weise, in der Iteratoren implementiert werden.  
  
- Bei der *sofortigen Auswertung* wird beim ersten Aufruf des Iterators die gesamte Auflistung verarbeitet. Eventuell ist auch eine temporäre Kopie der Quellauflistung erforderlich. So muss z. B. die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode die gesamte Auflistung erst sortieren, bevor sie das erste Element zurückgibt.  
  
 Die verzögerte Auswertung hat in der Regel eine höhere Arbeitsgeschwindigkeit zur Folge, weil die Verarbeitung des Mehraufwands gleichmäßig auf die Auswertung der Auflistung verteilt und die Verwendung temporärer Daten minimiert wird. Bei einigen Operationen führt aber natürlich kein Weg an der Materialisierung der Zwischenergebnisse vorbei.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die verzögerte Ausführung ist Gegenstand des nächsten Themas dieses Lernprogramms:  
  
- [Beispiel für eine verzögerte Ausführung (Visual Basic)](deferred-execution-example.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Tutorial: verzögerte Ausführung (Visual Basic)](tutorial-deferred-execution.md)
- [Konzepte und Terminologie (funktionale Transformation) (Visual Basic)](concepts-and-terminology-functional-transformation.md)
- [Aggregations Vorgänge (Visual Basic)](aggregation-operations.md)
