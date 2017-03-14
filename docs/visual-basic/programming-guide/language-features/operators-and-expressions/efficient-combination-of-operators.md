---
title: "Efficient Combination of Operators (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "expressions [Visual Basic], parentheses"
  - "operators [Visual Basic], associativity"
  - "expressions [Visual Basic], operators"
  - "operators [Visual Basic], precedence"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "operators [Visual Basic], complex expressions"
  - "expressions [Visual Basic], complex"
  - "parentheses, complex expressions"
  - "numeric expressions"
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Efficient Combination of Operators (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Komplexe Ausdrücke können viele verschiedene Operatoren enthalten.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 Für die Erstellung komplexer Ausdrücke wie im vorhergehenden Beispiel müssen Sie mit den Regeln der Operatorrangfolge sehr gut vertraut sein.  Weitere Informationen finden Sie unter [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## Klammernausdrücke  
 Oftmals sollen Operationen in einer Reihenfolge ausgeführt werden, die von der Operatorrangfolge abweicht.  Betrachten Sie das folgende Beispiel.  
  
 `x = z * y + 4`  
  
 Im vorhergehenden Beispiel wird `z` mit `y` multipliziert und anschließend das Ergebnis zu `4` addiert.  Wenn Sie jedoch `y` und `4` addieren möchten, bevor Sie das Ergebnis mit `z` multiplizieren, können Sie die normale Operatorrangfolge mithilfe von Klammern überschreiben.  Wenn Sie einen Ausdruck in Klammern einschließen, erzwingen Sie, dass dieser Ausdruck ungeachtet der Operatorrangfolge zuerst ausgewertet wird.  Um im vorherigen Beispiel zu erzwingen, dass die Addition zuerst ausgeführt wird, können sie es wie im folgenden Beispiel ändern.  
  
 `x = z * (y + 4)`  
  
 Im vorangehenden Beispiel werden `y` und `4` addiert, und anschließend wird die Summe mit `z` multipliziert.  
  
### Geschachtelte Klammerausdrücke  
 Sie können Ausdrücke auf mehreren Ebenen von Klammern schachteln, um die Operatorrangfolge noch weiter zu überschreiben.  Die Ausdrücke mit der tiefsten Schachtelung in Klammern werden zuerst ausgewertet, anschließend die Ausdrücke mit der nächsttieferen Schachtelung usw. bis zu den Ausdrücken mit der geringsten Schachtelungstiefe, und schließlich die Ausdrücke außerhalb der Klammern.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 Im vorangehenden Beispiel wird `z + 2` zuerst ausgewertet, und anschließend werden die anderen Ausdrücke in Klammern ausgewertet.  Potenzierung, die normalerweise Vorrang vor Addition oder Multiplikation hat, wird in diesem Beispiel zuletzt ausgewertet, da die anderen Ausdrücke in Klammern stehen.  
  
## Siehe auch  
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Logical\/Bitwise Operators](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [How to: Calculate Numeric Values](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)