---
title: "Value Comparisons (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], comparing values"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "comparison operators, comparing expressions"
  - "numeric expressions"
  - "operators [Visual Basic], comparison"
  - "expressions [Visual Basic], comparing"
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Value Comparisons (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Vergleichsoperatoren können zum Erstellen von Ausdrücken verwendet werden, die die Werte von numerischen Variablen vergleichen.  Diese Ausdrücke geben einen `Boolean`\-Wert zurück, der darauf basiert, ob der Vergleich "True" oder "False" ist.  Ein solcher Ausdruck kann wie in den folgenden Beispielen angegeben werden.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 Der erste Ausdruck ist `True`, weil 45 größer als 26 ist.  Der zweite Ausdruck ist `False`, weil 26 nicht größer als 45 ist.  
  
 Sie können auch numerische Ausdrücke auf diese Weise vergleichen.  Bei den zu vergleichenden Ausdrücken kann es sich, wie im folgenden Beispiel, auch um komplexe Ausdrücke handeln.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 Der oben dargestellte komplexe Ausdruck enthält Literale, Variablen und Funktionsaufrufe.  Die Ausdrücke auf beiden Seiten des Vergleichsoperators werden ausgewertet, und die Ergebniswerte werden dann mit dem Vergleichsoperator `>=` verglichen.  Wenn der Wert des Ausdrucks auf der linken Seite größer als oder gleich dem Wert des Ausdrucks auf der rechten Seite ist, ist der gesamte Ausdruck `True`. Andernfalls ist er `False`.  
  
 Ausdrücke, die Werte vergleichen, werden häufig in `If...Then`\-Konstruktionen verwendet, wie im folgenden Beispiel.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 Das Zeichen `=` ist sowohl ein Vergleichsoperator als auch ein Zuweisungsoperator.  Wenn Sie dieses Zeichen als Vergleichsoperator verwenden, wird ausgewertet, ob der Wert auf der linken Seite gleich dem Wert auf der rechten Seite ist, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 Sie können einen Vergleichsausdruck auch überall dort verwenden, wo ein `Boolean`\-Wert erforderlich ist, z. B. in den Anweisungen `If`, `While`, `Loop` oder `ElseIf` oder beim Zuweisen oder Übergeben eines Werts an eine `Boolean`\-Variable.  Im folgenden Beispiel wird der von dem Vergleichsausdruck zurückgegebene Wert einer `Boolean`\-Variablen zugewiesen.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## Siehe auch  
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [How to: Calculate Numeric Values](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)