---
title: Operatorrangfolge in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58830031"
---
# <a name="operator-precedence-in-visual-basic"></a>Operatorrangfolge in Visual Basic
Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und in einer vorbestimmten Reihenfolge aufgelöst *Operatorrangfolge*.  
  
## <a name="precedence-rules"></a>Regeln für die Berechnungsrangfolge  
 Ausdrücke, Operatoren, die von mehr als einer Kategorie enthalten, werden sie gemäß den folgenden Regeln ausgewertet:  
  
-   Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben der Rangfolge höher eingestuft als die Vergleichsoperatoren, logische und bitweise Operatoren.  
  
-   Alle Vergleichsoperatoren haben denselben Rang, und alles, was der Rangfolge höher eingestuft als die logischen und bitweisen Operatoren, jedoch geringere Rangfolge als der arithmetischen Operatoren und Verkettungsoperatoren.  
  
-   Die logischen und bitweisen Operatoren die Reihenfolge der Rangfolge, die im folgenden Abschnitt beschrieben, und alle niedrigeren Rangfolge als der arithmetische, Verkettung und Vergleichsoperatoren.  
  
-   Operatoren mit gleichem Rang werden links nach rechts ausgewertet in der Reihenfolge, in der sie den Ausdruck angezeigt werden.  
  
## <a name="precedence-order"></a>Rangfolge  
 Operatoren werden in der folgenden Rangfolge ausgewertet:  
  
### <a name="await-operator"></a>Await-Operator  
 Await-  
  
### <a name="arithmetic-and-concatenation-operators"></a>Arithmetische Operatoren und Verkettungsoperatoren  
 Potenzierung (`^`)  
  
 Unäre Identität und Negation (`+`, `–`)  
  
 Multiplikation und Gleitkommadivision (`*`, `/`)  
  
 Division ganzer Zahlen (`\`)  
  
 Arithmetischer Modulo (`Mod`)  
  
 Addition und Subtraktion (`+`, `–`)  
  
 Verketten von Zeichenfolgen (`&`)  
  
 Arithmetische-Bit-Verschiebung (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Vergleichsoperatoren  
 Alle Vergleichsoperatoren (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren  
 Negation (`Not`)  
  
 Verbindung (`And`, `AndAlso`)  
  
 Inklusive Disjunktion (`Or`, `OrElse`)  
  
 Exklusive Disjunktion (`Xor`)  
  
### <a name="comments"></a>Kommentare  
 Die `=` Operator wird nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.  
  
 Der Operator für zeichenfolgenverkettung (`&`) kein arithmetischer Operator, sondern in der Rangfolge mit den arithmetischen Operatoren gruppieren.  
  
 Die `Is` und `IsNot` Operatoren sind die Vergleichsoperatoren für Objekt-Verweis. Sie führen nicht die Werte von zwei Objekten Vergleich. Sie überprüfen, nur um zu bestimmen, ob zwei Objektvariablen auf die gleiche Objektinstanz verweisen.  
  
## <a name="associativity"></a>Assoziativität  
 Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. die Multiplikations- und Divisionsaufgaben, angezeigt werden wertet der Compiler jeder Vorgang, wie sie von links nach rechts gefundenen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Der erste Ausdruck wertet die Division 96 / 8 (wodurch 12), und klicken Sie dann die Division 12 / 4, die in drei führt. Da der Compiler die Vorgänge für wertet `n1` von links nach rechts, die Auswertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`. Beide `n1` und `n2` Ergebnis 3 haben. Im Gegensatz dazu `n3` ein Ergebnis 48, hat, da die Klammern erzwingen, den Compiler zum Auswerten von 8 dass / 4 ersten.  
  
 Aufgrund dieses Verhaltens der Operatoren gelten als *linksassoziativ* in Visual Basic.  
  
## <a name="overriding-precedence-and-associativity"></a>Überschreiben der Rangfolge und Assoziativität  
 Sie können mithilfe von Klammern zu erzwingen, dass einige Teile eines Ausdrucks vor anderen ausgewertet werden soll. Dadurch kann sowohl die Reihenfolge der Rangfolge und Assoziativität von links auf die überschrieben werden. Visual Basic führt immer Vorgänge, die in Klammern vor den außerhalb eingeschlossen sind. Es verwaltet jedoch innerhalb der Klammern normale Rangfolge und Assoziativität, es sei denn, Sie mithilfe von Klammern innerhalb der Klammern. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim a, b, c, d, e, f, g As Double  
a = 8.0  
b = 3.0  
c = 4.0  
d = 2.0  
e = 1.0  
f = a - b + c / d * e  
' The preceding line sets f to 7.0. Because of natural operator   
' precedence and associativity, it is exactly equivalent to the   
' following line.  
f = (a - b) + ((c / d) * e)  
' The following line overrides the natural operator precedence   
' and left associativity.  
g = (a - (b + c)) / (d * e)  
' The preceding line sets g to 0.5.  
```  
  
## <a name="see-also"></a>Siehe auch

- [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)
- [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
