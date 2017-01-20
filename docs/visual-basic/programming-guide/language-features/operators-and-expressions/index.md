---
title: "Operators and Expressions in Visual Basic | Microsoft Docs"
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
  - "operators [Visual Basic], operands"
  - "operators [Visual Basic]"
  - "operands, definition"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "operands"
  - "expressions [Visual Basic]"
ms.assetid: b86f3131-94ee-448f-96cd-79611e028b26
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operators and Expressions in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ein *Operator* ist ein Codeelement, das eine Operation für ein oder mehrere Codeelemente ausführt, die Werte enthalten.  Wertelemente sind z. B. Variablen, Konstanten, Literale, Eigenschaften, Rückgaben von der `Function`\-Prozedur und der `Operator`\-Prozedur sowie Ausdrücke.  
  
 Ein *Ausdruck* ist eine Reihe von Wertelementen, die mit Operatoren kombiniert werden, und dies ergibt einen neuen Wert.  Die Operatoren behandeln die Wertelemente, indem sie Berechnungen, Vergleiche und andere Operationen ausführen.  
  
## Typen von Operatoren  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt die folgenden Typen von Operatoren bereit:  
  
-   [Arithmetische Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md) führen gängige Berechnungen mit numerischen Werten aus, einschließlich des Verschiebens ihrer Bitmuster.  
  
-   [Vergleichsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) vergleichen zwei Ausdrücke und geben einen `Boolean`\-Wert zurück, der das Ergebnis des Vergleichs darstellt.  
  
-   [Verkettungsoperatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md) verknüpfen mehrere Zeichenfolgen zu einer einzigen Zeichenfolge.  
  
-   [Logische und bitweise Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md) kombinieren `Boolean`\-Werte oder numerische Werte und geben im Ergebnis denselben Datentyp zurück, den die Werte aufweisen.  
  
 Die mit einem Operator kombinierten Wertelemente werden als *Operanden* dieses Operators bezeichnet.  Mit Wertelementen kombinierte Operatoren bilden Ausdrücke, mit Ausnahme des Zuweisungsoperators, der eine *Anweisung* bildet.  Weitere Informationen finden Sie unter [Statements](../../../../visual-basic/programming-guide/language-features/statements.md).  
  
## Evaluierung von Ausdrücken  
 Das Ergebnis eines Ausdrucks stellt einen Wert dar, der i. d. R. einen gängigen Datentyp, z. B. `Boolean`, `String` oder einen numerischen Typ, aufweist.  
  
 Im Folgenden sind einige Beispiele für Ausdrücke aufgeführt.  
  
 `5 + 4`  
  
 `' The preceding expression evaluates to 9.`  
  
 `15 * System.Math.Sqrt(9) + x`  
  
 `' The preceding expression evaluates to 45 plus the value of x.`  
  
 `"Concat" & "ena" & "tion"`  
  
 `' The preceding expression evaluates to "Concatenation".`  
  
 `763 < 23`  
  
 `' The preceding expression evaluates to False.`  
  
 Aktionen können von mehrere Operatoren in einem einzigen Ausdruck oder einer einzigen Anweisung ausgeführt werden, wie im folgenden Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrOperators#56](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/index_1.vb)]  
  
 Im vorherigen Beispiel führt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die Operationen im Ausdruck auf der rechten Seite des Zuweisungsoperators \(`=`\) aus und weist dann der Variablen `x` auf der linken Seite den Ergebniswert zu.  Es gibt praktisch keine Begrenzung für die Anzahl der Operatoren, die in einem Ausdruck kombiniert werden können. Sie müssen jedoch die Regeln der [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md) verstehen, um sicherzustellen, dass Sie die erwarteten Ergebnisse erhalten.  
  
 Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## Siehe auch  
 [Operators](../../../../visual-basic/language-reference/operators/index.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Statements](../../../../visual-basic/language-reference/statements/index.md)