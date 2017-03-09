---
title: "Operator Precedence in Visual Basic | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operators, precedence"
  - "operator precedence"
  - "logical operators, precedence"
  - "operators [Visual Basic], associativity"
  - "operators [Visual Basic], resolution"
  - "associativity of operators"
  - "operators [Visual Basic], precedence"
  - "precedence, of operators"
  - "comparison operators, precedence"
  - "math operators"
  - "order of precedence"
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Operator Precedence in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Treten mehrere Operationen in einem Ausdruck auf, wird jedes Teil in einer vorbestimmten Reihenfolge ausgewertet und aufgelöst. Dies wird als *Operatorrangfolge* bezeichnet.  
  
## Rangfolgenregeln  
 Wenn ein Ausdruck Operatoren aus mehreren Kategorien enthält, werden sie gemäß den folgenden Regeln ausgewertet:  
  
-   Die arithmetischen Operatoren und Verkettungsoperatoren haben die im folgenden Abschnitt beschriebene Rangfolge. Sie haben gegenüber Vergleichsoperatoren, logischen sowie bitweisen Operatoren Vorrang.  
  
-   Alle Vergleichsoperatoren haben den gleichen Rang, und alle haben Vorrang gegenüber den logischen und bitweisen Operatoren, sind jedoch den arithmetischen Operatoren und Verkettungsoperatoren nachgeordnet.  
  
-   Die logischen und bitweisen Operatoren haben die im folgenden Abschnitt beschriebene Rangfolge und einen niedrigeren Rang als die arithmetischen Operatoren sowie die Verkettungs\- und Vergleichsoperatoren.  
  
-   Operatoren mit gleichem Rang werden von links nach rechts in der Reihenfolge ausgewertet, in der sie im Ausdruck vorkommen.  
  
## Rangfolgenreihenfolge  
 Operatoren werden in der folgenden Rangfolge ausgewertet:  
  
### Rechnen Sie Operator  
 Await  
  
### Arithmetische Operatoren und Verkettungsoperatoren  
 Potenzierung \(`^`\)  
  
 Unäre Identität und Negation \(`+`, `–`\)  
  
 Multiplikation und Gleitkommadivision \(`*`, `/`\)  
  
 Ganzzahldivision \(`\`\)  
  
 Modulooperator \(Mod\)  
  
 Addition und Subtraktion \(`+`, `–`\)  
  
 Zeichenfolgenverkettung \(`&`\)  
  
 Arithmetische Bitverschiebung \(`<<`, `>>`\)  
  
### Vergleichsoperatoren  
 Alle Vergleichsoperatoren \(`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`\)  
  
### Logische und bitweise Operatoren  
 Negation \(`Not`\)  
  
 Konjunktion \(`And`, `AndAlso`\)  
  
 Inklusive Disjunktion \(`Or`, `OrElse`\)  
  
 Exklusive Disjunktion \(`Xor`\)  
  
### Kommentare  
 Der Operator `=` ist nur der Gleichheitsvergleichsoperator, nicht der Zuweisungsoperator.  
  
 Der Operator für die Zeichenfolgenverkettung \(`&`\) ist kein arithmetischer Operator, wird aber in Bezug auf die Rangfolge der Gruppe der arithmetischen Operatoren zugeordnet.  
  
 Der Operator `Is` und der Operator `IsNot` sind Objektverweisvergleichsoperatoren.  Sie vergleichen nicht die Werte zweier Objekte, sondern prüfen lediglich, ob zwei Objektvariablen auf dieselbe Objektinstanz verweisen.  
  
## Assoziativität  
 Treffen Operatoren mit dem gleichen Rang in einem Ausdruck zusammen, z. B. Multiplikation und Division, wertet der Compiler jede Operation bei ihrer Ausführung von links nach rechts aus.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 Im ersten Ausdruck wird zuerst die Division 96 \/ 8 berechnet \(ergibt 12\) und anschließend 12 \/ 4 \(ergibt 3\).  Da der Compiler die Operationen für `n1` von links nach rechts auswertet, ist die Auswertung identisch, wenn diese Reihenfolge für `n2` explizit angegeben wird.  Sowohl `n1` als auch `n2` ergeben drei.  Im Gegensatz ergibt `n3` 48, da 8 \/ 4 aufgrund der Klammern zuerst vom Compiler ausgewertet wird.  
  
 Aufgrund dieses Verhaltens werden Operatoren in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] als *linksassoziativ* bezeichnet.  
  
## Überschreiben von Rangfolge und Assoziativität  
 Mithilfe von runden Klammern können Sie erzwingen, dass einige Teile eines Ausdrucks vor anderen ausgewertet werden.  Dadurch können sowohl die Rangfolge als auch die Linksassoziativität überschrieben werden.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] wird immer Vorgänge aus, die in Klammern vor die außerhalb enthalten sind. jedoch innerhalb der Klammern, wartet er normale Rangfolge und Assoziativität, es sei denn, Sie Klammern in Klammern verwenden.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
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
  
## Siehe auch  
 [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)   
 [TypeOf Operator](../../../visual-basic/language-reference/operators/typeof-operator.md)   
 [Await Operator](../../../visual-basic/language-reference/operators/await-operator.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)