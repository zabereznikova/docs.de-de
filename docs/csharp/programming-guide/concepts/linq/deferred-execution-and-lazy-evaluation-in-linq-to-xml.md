---
title: Verzögerte Ausführung und Auswertung in LINQ to XML (C#)
description: Abfrage- und Achsenvorgänge können die verzögerte Ausführung in C# verwenden. Hier erfahren Sie mehr über die Ausführungen und die Vorteile der verzögerten Ausführung und zu Überlegungen zur Implementierung.
ms.date: 07/20/2015
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
ms.openlocfilehash: 8559505572404f895d75e0d9895f9ae2c07b795e
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105460"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a>Verzögerte Ausführung und Auswertung in LINQ to XML (C#)
Abfrage- und Achsenoperationen werden oft so implementiert, dass sie die verzögerte Ausführung (Deferred Execution) verwenden. In diesem Thema werden die Voraussetzungen und die Vorteile der verzögerten Ausführung erläutert und einige Überlegungen zur Implementierung angestellt.  
  
## <a name="deferred-execution"></a>Verzögerte Ausführung  
 Verzögerte Ausführung bedeutet, dass die Auswertung eines Ausdrucks so lange hinausgezögert wird, bis dessen *realisierter* Wert tatsächlich benötigt wird. Dort, wo große Datensammlungen bearbeitet werden müssen, vor allem in Programmen, die eine Reihe von verketteten Abfragen oder Manipulationen enthalten, kann die verzögerte Ausführung die Arbeitsgeschwindigkeit der Anwendung signifikant erhöhen. Im besten Fall muss bei der verzögerten Ausführung lediglich ein Durchlauf durch die Quellauflistung erfolgen.  
  
 Die LINQ-Technologien machen von der verzögerten Ausführung umfangreichen Gebrauch, und dies sowohl bei den Membern der <xref:System.Linq?displayProperty=nameWithType>-Kernklassen als auch bei den Erweiterungsmethoden in den verschiedenen LINQ-Namespaces, z. B. <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.  
  
 Die verzögerte Auswertung wird in der C#-Sprache direkt durch das [yield](../../../language-reference/keywords/yield.md)-Schlüsselwort (in Form der `yield-return`-Anweisung) im Iteratorblock unterstützt. So ein Iterator muss eine Auflistung des Typs <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> (oder eines abgeleiteten Typs) zurückgeben.  
  
## <a name="eager-vs-lazy-evaluation"></a>Vergleich von sofortiger Auswertung und verzögerter Auswertung  
 Beim Schreiben einer Methode, die die verzögerte Ausführung implementiert, können Sie sich auch überlegen, ob die Methode mit verzögerter Auswertung (Lazy Evaluation) oder sofortiger Auswertung (Eager Evaluation) implementiert werden soll.  
  
- Bei der *verzögerten Auswertung* wird bei jedem Aufruf des Iterators jeweils ein Element der Quellauflistung verarbeitet. Dies ist die übliche Art und Weise, in der Iteratoren implementiert werden.  
  
- Bei der *sofortigen Auswertung* wird beim ersten Aufruf des Iterators die gesamte Auflistung verarbeitet. Eventuell ist auch eine temporäre Kopie der Quellauflistung erforderlich. So muss z. B. die <xref:System.Linq.Enumerable.OrderBy%2A>-Methode die gesamte Auflistung erst sortieren, bevor sie das erste Element zurückgibt.  
  
 Die verzögerte Auswertung hat in der Regel eine höhere Arbeitsgeschwindigkeit zur Folge, weil die Verarbeitung des Mehraufwands gleichmäßig auf die Auswertung der Auflistung verteilt und die Verwendung temporärer Daten minimiert wird. Bei einigen Operationen führt aber natürlich kein Weg an der Materialisierung der Zwischenergebnisse vorbei.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Die verzögerte Ausführung ist Gegenstand des nächsten Themas dieses Lernprogramms:  
  
- [Beispiel für eine verzögerte Ausführung (C#)](./deferred-execution-example.md)  
  
## <a name="see-also"></a>Siehe auch

- [Tutorial: Verketten von Abfragen (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
- [Konzepte und Terminologie (funktionale Transformation) (C#)](./concepts-and-terminology-functional-transformation.md)
- [Aggregation Operations (C#) (Aggregationsvorgänge (C#))](./aggregation-operations.md)
- [yield](../../../language-reference/keywords/yield.md)
