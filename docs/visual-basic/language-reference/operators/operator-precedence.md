---
title: Operatorrangfolge in Visual Basic | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- arithmetic operators, precedence
- operator precedence
- logical operators, precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators
- operators [Visual Basic], precedence
- precedence, of operators
- comparison operators, precedence
- math operators
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6532fc0c26db3b736c863be075571570a3d25eef
ms.lasthandoff: 03/13/2017

---
# <a name="operator-precedence-in-visual-basic"></a>Operatorrangfolge in Visual Basic
Treten mehrere Operationen in einem Ausdruck, wird jeder Teil ausgewertet und aufgelöst, die in einer vorbestimmten Reihenfolge *Operatorrangfolge*.  
  
## <a name="precedence-rules"></a>Regeln  
 Wenn Ausdrücke Operatoren aus mehreren Kategorien enthalten, werden sie gemäß den folgenden Regeln ausgewertet:  
  
-   Die arithmetischen Operatoren und Verkettungsoperatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Vergleichsoperatoren, logische und bitweise Operatoren.  
  
-   Alle Vergleichsoperatoren haben denselben Rang, und alle haben Vorrang vor den logischen und bitweisen Operatoren, sind jedoch die arithmetischen Operatoren und Verkettungsoperatoren.  
  
-   Die logischen und bitweisen Operatoren haben die Rangfolge, die im folgenden Abschnitt beschrieben, und alle haben Vorrang vor den Arithmetik, Verkettung und Vergleichsoperatoren.  
  
-   Operatoren mit gleichem Rang links nach rechts ausgewertet werden in der Reihenfolge, in der sie im Ausdruck vorkommen.  
  
## <a name="precedence-order"></a>Rangfolge  
 Operatoren werden in der folgenden Reihenfolge bewertet:  
  
### <a name="await-operator"></a>Await-Operator  
 Await-  
  
### <a name="arithmetic-and-concatenation-operators"></a>Arithmetische Operatoren und Verkettungsoperatoren  
 Potenzierung (`^`)  
  
 Unäre Identität und Negation (`+`, `–`)  
  
 Multiplikation und Gleitkommadivision (`*`, `/`)  
  
 Division ganzer Zahlen (`\`)  
  
 Modulo-Arithmetik (`Mod`)  
  
 Addition und Subtraktion (`+`, `–`)  
  
 Verketten von Zeichenfolgen (`&`)  
  
 Bit-arithmetische Verschiebung (`<<`, `>>`)  
  
### <a name="comparison-operators"></a>Vergleichsoperatoren  
 All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`... `Is`)  
  
### <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren  
 Negation (`Not`)  
  
 Verbindung (`And`, `AndAlso`)  
  
 Inklusive Disjunktion (`Or`, `OrElse`)  
  
 Exklusive Disjunktion (`Xor`)  
  
### <a name="comments"></a>Kommentare  
 Die `=` -Operator ist nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.  
  
 Der Operator für zeichenfolgenverkettung (`&`) kein arithmetischer Operator, sondern in der Rangfolge mit arithmetischen Operatoren gruppieren.  
  
 Die `Is` und `IsNot` Operatoren sind Objektverweisvergleichsoperatoren. Nicht vergleichen sie die Werte von zwei Objekten; Sie überprüft nur, ob zwei Object-Variablen auf die gleiche Objektinstanz verweisen.  
  
## <a name="associativity"></a>Assoziativität  
 Wenn Operatoren mit gleichem Rang zusammen in einem Ausdruck, z. B. Multiplikation und Division, angezeigt werden wertet der Compiler jede Operation, wie sie von links nach rechts gefundenen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Der erste Ausdruck wertet die Division 96 / 8 (wodurch 12) und dann die Division 12 / 4, der drei führt. Da der Compiler die Operationen für ergibt `n1` von links nach rechts, die Bewertung ist identisch, wenn diese Reihenfolge explizit angegeben wird, für die `n2`. Beide `n1` und `n2` ergeben drei. Im Gegensatz dazu `n3` hat ein Ergebnis 48, da die Klammern erzwingen die vom Compiler ausgewertet 8 / 4 erste.  
  
 Aufgrund dieses Verhaltens können Operatoren gelten als *linksassoziativ* in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="overriding-precedence-and-associativity"></a>Überschreiben von Rangfolge und Assoziativität  
 Sie können Klammern verwenden, um einige Teile eines Ausdrucks vor anderen ausgewertet werden zu erzwingen. Dadurch kann die Rangfolge und Assoziativität von links überschrieben. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Vorgänge, die in Klammern vor den außerhalb stehen durchgeführt immer. Es verwaltet jedoch innerhalb der Klammern normale Rangfolge und Assoziativität, es sei denn, Sie Klammern innerhalb der Klammern verwenden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
 [LIKE-Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf-Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Operatoren sortiert nach Funktionalität](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
