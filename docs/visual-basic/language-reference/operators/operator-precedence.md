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
ms.openlocfilehash: 211a710f4dba2310ea1ae74decdb1926ce612a62
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="operator-precedence-in-visual-basic"></a>Operatorrangfolge in Visual Basic
Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und in einem vorbestimmten Reihenfolge aufgelöst *Operatorrangfolge*.  
  
## <a name="precedence-rules"></a>Rangfolgeregeln  
 Wenn Ausdrücke Operatoren aus mehr als einer Kategorie enthalten, werden sie anhand der folgenden Regeln ausgewertet:  
  
-   Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Vergleichsoperatoren, logische und bitweise Operatoren.  
  
-   Alle Vergleichsoperatoren haben denselben Rang und alle höheren Priorität als die logischen und bitweisen Operatoren, aber geringere Rangfolge als der arithmetischen Operatoren und Verkettungsoperatoren verfügen.  
  
-   Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle geringere Rangfolge als der Arithmetik, Verkettung und Vergleichsoperatoren haben.  
  
-   Operatoren mit gleichem Rang werden links nach rechts ausgewertet in der Reihenfolge, in dem sie im Ausdruck angezeigt werden.  
  
## <a name="precedence-order"></a>Rangfolge  
 Operatoren werden in der folgenden Rangfolge ausgewertet:  
  
### <a name="await-operator"></a>Await-Operator  
 Await-  
  
### <a name="arithmetic-and-concatenation-operators"></a>Arithmetische Operatoren und Verkettungsoperatoren  
 Potenzierung (`^`)  
  
 Unäre Identität und Negation (`+`, `–`)  
  
 Multiplikation und Gleitkommadivision (`*`, `/`)  
  
 Ganzzahldivision (`\`)  
  
 Modulo (`Mod`)  
  
 Addition und Subtraktion (`+`, `–`)  
  
 Verketten von Zeichenfolgen (`&`)  
  
 Arithmetische bitverschiebung (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Vergleichsoperatoren  
 Alle Vergleichsoperatoren (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren  
 Negation (`Not`)  
  
 Verbindung (`And`, `AndAlso`)  
  
 Inklusive Disjunktion (`Or`, `OrElse`)  
  
 Ausschließende Disjunktion (`Xor`)  
  
### <a name="comments"></a>Kommentare  
 Die `=` Operator wird nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.  
  
 Der Operator für zeichenfolgenverkettung (`&`) ist ein arithmetischer Operator, aber in der Rangfolge mit den arithmetischen Operatoren gruppieren.  
  
 Die `Is` und `IsNot` Operatoren sind, Referenz-Objektverweisvergleichsoperatoren. Nicht vergleichen sie die Werte von zwei Objekten; Sie überprüft nur, um festzustellen, ob zwei Objektvariablen auf die gleiche Objektinstanz verweisen.  
  
## <a name="associativity"></a>Assoziativität  
 Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. Multiplikations- und Divisionsaufgaben, angezeigt werden wertet der Compiler jeden Vorgang, wie sie von links nach rechts gefundenen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Der erste Ausdruck wertet die Division 96 / 8 (Vortäuschen 12), und klicken Sie dann die Division 12 / 4, was in drei führt. Da der Compiler die Operationen für ergibt `n1` von links nach rechts, die Auswertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`. Beide `n1` und `n2` Ergebnis von drei haben. Im Gegensatz dazu `n3` verfügt über ein Ergebnis von 48, da die Klammern den Compiler auszuwertende 8 zwingen / 4 erste.  
  
 Aufgrund dieses Verhaltens Operatoren gelten als *linksassoziativ* in Visual Basic.  
  
## <a name="overriding-precedence-and-associativity"></a>Überschreiben von Rangfolge und Assoziativität  
 Sie können Klammern verwenden, erzwingen Sie einige Teile eines Ausdrucks vor anderen ausgewertet werden soll. Dadurch kann die Reihenfolge der Rangfolge und Assoziativität von links auf die überschreiben. Visual Basic führt immer Vorgänge, die in Klammern vor den außerhalb eingeschlossen sind. Verwaltet jedoch innerhalb der Klammern gewöhnliche Rangfolge und Assoziativität, es sei denn, Sie mithilfe von Klammern innerhalb der Klammern. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
 [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)  
 [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
