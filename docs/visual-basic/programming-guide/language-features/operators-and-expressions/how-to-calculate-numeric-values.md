---
title: "How to: Calculate Numeric Values (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
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
  - "operator precedence"
  - "operators [Visual Basic]"
  - "expressions [Visual Basic], numeric"
  - "calculations, numeric expressions"
  - "precedence, of operators"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "numeric expressions"
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Calculate Numeric Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können numerische Werte mithilfe von numerischen Ausdrücken berechnen.  Ein *numerischer Ausdruck* ist ein Ausdruck, der Literale, Konstanten und Variablen enthält, die numerische Werte darstellen, sowie Operatoren, die diese Werte behandeln.  
  
## Berechnen von numerischen Werten  
  
#### So berechnen Sie einen numerischen Wert  
  
-   Bilden Sie aus ein oder mehreren numerischen Literalen, Konstanten und Variablen einen numerischen Ausdruck.  Im folgenden Beispiel werden einige gültige numerische Ausdrücke dargestellt.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Die ersten drei Zeilen enthalten ein Literal, eine Konstante bzw. eine Variable.  Jedes dieser Elemente an sich ist ein gültiger numerischer Ausdruck.  Die letzte Zeile enthält eine Variable mit zwei Literalen.  
  
     Beachten Sie, dass ein numerischer Ausdruck an sich keine vollständige [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Anweisung bildet.  Sie müssen den Ausdruck als Teil einer vollständigen Anweisung verwenden.  
  
#### So speichern Sie einen numerischen Wert  
  
-   Sie können eine Zuweisungsanweisung verwenden, um den von einem numerischen Ausdruck dargestellten Wert einer Variablen zuzuweisen, wie im folgenden Beispiel dargestellt.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-va_1.vb)]  
  
     Im vorherigen Beispiel wird der Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators \(`=`\) der Variablen `j` auf der linken Seite des Operators zugewiesen, sodass `j` 276 ergibt.  
  
     Weitere Informationen finden Sie unter [Statements](../../../../visual-basic/language-reference/statements/index.md).  
  
## Mehrere Operatoren  
 Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge der Berechnung durch die Regeln der Operatorrangfolge festgelegt.  Wenn Sie die Regeln der Operatorrangfolge überschreiben möchten, müssen Sie wie im obigen Beispiel Ausdrücke in Klammern einschließen. Die Ausdrücke ein Klammern werden zuerst ausgewertet.  
  
#### So überschreiben Sie die normale Operatorrangfolge  
  
-   Schließen Sie die Operationen in Klammern ein, die zuerst ausgeführt werden sollen.  Im folgenden Beispiel werden zwei verschiedene, mit den gleichen Operanden und Operatoren erzielte Ergebnisse veranschaulicht.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-va_2.vb)]  
  
     Im vorhergehenden Beispiel wird in der Berechnung für `j` der Additionsoperator \(`+`\) zuerst ausgeführt, weil die Klammern um `(67 + i)` die normale Rangfolge überschreiben, und der `j` zugewiesene Wert ist 276 \(4 mal 69\).  Bei der Berechnung von `k` werden die Operatoren in der normalen Rangfolge \(`*` vor `+`\) ausgeführt, und der `k` zugewiesene Wert ist 270 \(268 plus 2\).  
  
     Weitere Informationen finden Sie unter [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Siehe auch  
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)