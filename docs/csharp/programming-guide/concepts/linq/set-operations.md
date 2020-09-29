---
title: Mengenvorgänge (C#)
description: Hier erfahren Sie mehr über Mengenvorgänge und die Methoden von Standardabfrageoperatoren, die Mengenvorgänge in LINQ in C# ausführen.
ms.date: 07/20/2015
ms.assetid: 7c589367-ef8f-4161-9050-642c47e6bf63
ms.openlocfilehash: 8679f804adaaeada390206e3e1dd2a0711a2cbf6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195609"
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

 Das folgende Beispiel veranschaulicht das Verhalten der Methode <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> in einer Zeichensequenz. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus der Eingabesequenz.  
  
 ![Grafische Darstellung des Verhaltens von Distinct&#40;&#41;](./media/set-operations/distinct-method-behavior.png)  

 [!code-csharp-interactive[Distinct](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#1)]
  
### <a name="except"></a>Except  

 Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType> veranschaulicht. Die zurückgegebene Sequenz enthält nur die Elemente aus der ersten Eingabesequenz, die sich nicht in der zweiten Eingabesequenz befinden.  
  
 ![Grafische Darstellung der Aktion Except&#40;&#41;.](./media/set-operations/except-behavior-graphic.png "Zeigt das Verhalten von Except an.")  
  
[!code-csharp-interactive[Except](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#2)]

### <a name="intersect"></a>Überschneiden  

 Im folgenden Beispiel wird das Verhalten von <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType> veranschaulicht. Die zurückgegebene Sequenz enthält die Elemente, die in beiden Eingabesequenzen verwendet werden.  
  
 ![Grafische Darstellung der Schnittmenge von zwei Sequenzen](./media/set-operations/intersection-two-sequences.png)  

[!code-csharp-interactive[Intersect](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#3)]

### <a name="union"></a>Union  

 Das folgende Beispiel veranschaulicht einen Vereinigungsvorgang zweier Zeichensequenzen. Die zurückgegebene Sequenz enthält die eindeutigen Elemente aus beiden Eingabesequenzen.  
  
 ![Grafische Darstellung der Verbindung von zwei Sequenzen](./media/set-operations/union-operation-two-sequences.png)  

[!code-csharp-interactive[Union](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQSetOperation/CS/SetOperation.cs#4)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md)
- [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md)
- [Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)](./how-to-find-the-set-difference-between-two-lists-linq.md)
