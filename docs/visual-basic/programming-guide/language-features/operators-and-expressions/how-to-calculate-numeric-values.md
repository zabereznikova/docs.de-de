---
title: 'Gewusst wie: Berechnen von numerischen Werten (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
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
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations, numeric expressions
- precedence, of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
caps.latest.revision: 13
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
ms.openlocfilehash: d844e2af3892d897125e21d3fd7047a8b295d10a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Gewusst wie: Berechnen von numerischen Werten (Visual Basic)
Sie können numerische Werte mithilfe von numerischen Ausdrücken berechnen. Ein *numerischen Ausdruck* ist ein Ausdruck, der literalen, Konstanten und Variablen, die numerische Werte enthält und Operatoren, die für diese Werte fungieren.  
  
## <a name="calculating-numeric-values"></a>Berechnen von numerischen Werten  
  
#### <a name="to-calculate-a-numeric-value"></a>Um einen numerischen Wert zu berechnen.  
  
-   Kombinieren Sie einen oder mehrere numerischen Literalen, Konstanten und Variablen in einem numerischen Ausdruck. Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Die ersten drei Zeilen enthalten ein Literal, eine Konstante und einer Variable. Jede bildet einen gültigen numerischen Ausdruck selbst. Die letzte Zeile zeigt eine Kombination einer Variablen mit zwei Literalen.  
  
     Beachten Sie, dass ein numerisches Ausdrucks keine vollständige bilden [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Anweisung selbst. Sie müssen den Ausdruck als Teil einer vollständigen Anweisung verwenden.  
  
#### <a name="to-store-a-numeric-value"></a>Um einen numerischen Wert zu speichern.  
  
-   Eine Zuweisung können durch einen numerischen Ausdruck einer Variablen dargestellten Wert zuweisen, wie im folgende Beispiel veranschaulicht.  
  
     [!code-vb[VbVbalrOperators&#82;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     Im vorherigen Beispiel den Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators (`=`) der Variablen zugewiesen `j` auf der linken Seite des Operators, damit `j` 276 ergibt.  
  
     Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Mehrere Operatoren  
 Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge, die Auswertung, durch die Regeln der Operatorrangfolge bestimmt. Um die Regeln der Operatorrangfolge überschreiben möchten, müssen Sie Ausdrücke in Klammern, wie im obigen Beispiel; die Ausdrücke ein Klammern werden zuerst ausgewertet.  
  
#### <a name="to-override-normal-operator-precedence"></a>Normale Operatorrangfolge überschreiben  
  
-   Verwenden Sie Klammern, die Vorgänge einschließen, zuerst ausgeführt werden soll. Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit den gleichen Operanden und Operatoren.  
  
     [!code-vb[VbVbalrOperators&83;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     Im vorhergehenden Beispiel die Berechnung für `j` der Additionsoperator (`+`) erste da Klammern `(67 + i)` überschreiben normale Rangfolge und den zugewiesenen Wert `j` ist 276 (4 Mal 69). Die Berechnung für `k` führt die Operatoren in der normalen Rangfolge (`*` vor `+`), und den zugewiesenen Wert `k` ist 270 (268 plus 2).  
  
     Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)   
 [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
