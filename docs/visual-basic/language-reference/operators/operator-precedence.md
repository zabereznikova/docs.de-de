---
title: Operatorrangfolge
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
ms.openlocfilehash: 318fcc3f35276ba0b2061ba9677c5fde29429f6f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348279"
---
# <a name="operator-precedence-in-visual-basic"></a>Operatorrangfolge in Visual Basic
Wenn mehrere Vorgänge in einem Ausdruck auftreten, wird jeder Teil in einer vordefinierten Reihenfolge ausgewertet und aufgelöst, die als *Operator Rangfolge*bezeichnet wird.

## <a name="precedence-rules"></a>Rang Folge Regeln
 Wenn Ausdrücke Operatoren aus mehr als einer Kategorie enthalten, werden Sie gemäß den folgenden Regeln ausgewertet:

- Der arithmetische und der Verkettungs Operator haben die Rangfolge, die im folgenden Abschnitt beschrieben wird, und alle haben Vorrang vor den Vergleichs-, logischen und bitweisen Operatoren.

- Alle Vergleichs Operatoren weisen die gleiche Rangfolge auf und haben Vorrang vor den logischen und bitweisen Operatoren, aber eine niedrigere Rangfolge als die arithmetischen Operatoren und die Verkettungs Operatoren.

- Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben wird, und alle haben Vorrang vor den Operatoren arithmetischer, Verkettungs-und Vergleichs Operatoren.

- Operatoren mit gleicher Rangfolge werden in der Reihenfolge, in der Sie im Ausdruck angezeigt werden, von links nach rechts ausgewertet.

## <a name="precedence-order"></a>Rangfolge
 Operatoren werden in der folgenden Rangfolge ausgewertet:

### <a name="await-operator"></a>Await-Operator
 Await-

### <a name="arithmetic-and-concatenation-operators"></a>Arithmetische Operatoren und Verkettungs Operatoren
 Exponentiierung (`^`)

 Unäre Identität und Negation (`+``–`)

 Multiplikation und Gleit Komma Division (`*``/`)

 Ganzzahlige Division (`\`)

 Modulare Arithmetik (`Mod`)

 Addition und Subtraktion (`+``–`)

 Verkettung von Zeichen folgen (`&`)

 Arithmetische Bitverschiebung (`<<``>>`)

### <a name="comparison-operators"></a>Vergleichsoperatoren
 Alle Vergleichs Operatoren (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)

### <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren
 Negation (`Not`)

 Verbindung (`And``AndAlso`)

 Inklusive Disjunktion (`Or``OrElse`)

 Exklusive Disjunktion (`Xor`)

### <a name="comments"></a>Comments
 Der `=`-Operator ist nur der Gleichheits Vergleichs Operator, nicht der Zuweisungs Operator.

 Der Operator für die Zeichen folgen Verkettung (`&`) ist kein arithmetischer Operator, aber in der Rangfolge ist er mit den arithmetischen Operatoren gruppiert.

 Die `Is`-und `IsNot` Operatoren sind Objekt Verweis-Vergleichs Operatoren. Die Werte von zwei Objekten werden nicht verglichen. Sie überprüfen lediglich, ob zwei Objektvariablen auf dieselbe Objektinstanz verweisen.

## <a name="associativity"></a>Assoziativität
 Wenn Operatoren mit gleicher Rangfolge in einem Ausdruck angezeigt werden, z. b. Multiplikation und Division, wertet der Compiler jeden Vorgang aus, der von links nach rechts erkannt wird. Das folgende Beispiel veranschaulicht dies.

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 Der erste Ausdruck wertet die Division 96/8 aus (die sich in 12 ergibt) und dann die Division 12/4, die drei ergibt. Da der Compiler die Vorgänge für die `n1` von links nach rechts auswertet, ist die Auswertung identisch, wenn diese Reihenfolge explizit für `n2`angegeben wird. Sowohl `n1` als auch `n2` haben das Ergebnis drei. Im Gegensatz dazu hat `n3` das Ergebnis 48, da die Klammern den Compiler zwingen, zuerst 8/4 auszuwerten.

 Aufgrund dieses Verhaltens werden Operatoren als *links assoziativ* in Visual Basic bezeichnet.

## <a name="overriding-precedence-and-associativity"></a>Überschreiben von Rangfolge und Assoziativität
 Sie können Klammern verwenden, um zu erzwingen, dass einige Teile eines Ausdrucks vor anderen ausgewertet werden. Dies kann die Reihenfolge der Rangfolge und die linke Assoziativität überschreiben. Visual Basic führt immer Vorgänge aus, die in Klammern eingeschlossen werden, bevor Sie außerhalb von stehen. Innerhalb von Klammern behält sie jedoch die normale Rangfolge und Assoziativität bei, es sei denn, Sie verwenden Klammern innerhalb der Klammern. Das folgende Beispiel veranschaulicht dies.

```vb
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
