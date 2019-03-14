---
title: Mengenvorgänge (C#)
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 169f7608409fcc0205a1f8edc69ee7a0b7785a51
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675510"
---
# <a name="set-operations-c"></a>Mengenvorgänge (C#)
Mengenvorgänge in LINQ sind Abfrageoperationen, die ein Satz von Ergebnissen erzeugen, der auf der Existenz oder Abwesenheit äquivalenter Elemente in derselben oder in einer getrennten Auflistung (oder einem Satz) basiert.  
  
 Die Methoden des Standardabfrageoperators, die Mengenoperationen ausführen, sind im folgenden Abschnitt aufgeführt.  
  
## <a name="methods"></a>Methoden  
  
|Methodenname|Beschreibung|C#-Abfrageausdruckssyntax|Weitere Informationen|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Distinct|Entfernt doppelte Werte aus einer Auflistung|Nicht zutreffend.|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Except|Gibt die festgelegte Differenz zurück, was bedeutet, dass die Elemente in einer Auflistung nicht in einer zweiten Auflistung angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|Überschneiden|Gibt die Schnittmenge zurück, d.h. die Elemente, die in beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Union|Gibt die Vereinigungsmenge zurück, d.h. eindeutige Elemente, die in einer der beiden Auflistungen angezeigt werden|Nicht zutreffend.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Vergleich von Mengenvorgängen  
  
### <a name="distinct"></a>Distinct  
 Die folgende Abbildung veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;.](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Distinct")  
  
### <a name="except"></a>Except  
 Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.  
  
 ![Grafische Darstellung der Aktion von Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except.")  
  
### <a name="intersect"></a>Überschneiden  
 Die folgende Abbildung veranschaulicht das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Union  
 Die folgende Abbildung stellt einen Union-Vorgang zweier Zeichensequenzen dar. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen.](../../../../csharp/programming-guide/concepts/linq/media/union.png "Union")  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
