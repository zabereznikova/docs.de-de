---
title: 'Gewusst wie: Berechnen von numerischen Werten (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: cf24d7259ac04f6901497c81558a4d59b340eec7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649785"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Gewusst wie: Berechnen von numerischen Werten (Visual Basic)
Sie können numerische Werte durch die Verwendung von numerischen Ausdrücken berechnen. Ein *numerischen Ausdrucks* ist ein Ausdruck, Literalen, Konstanten und Variablen, die numerische Werte enthält, und Operatoren, die für diese Werte fungieren.  
  
## <a name="calculating-numeric-values"></a>Berechnen von numerischen Werten  
  
#### <a name="to-calculate-a-numeric-value"></a>Um einen numerischen Wert zu berechnen.  
  
-   Kombinieren Sie mindestens numerischen Literalen, Konstanten und Variablen in einen numerischen Ausdruck. Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Die ersten drei Zeilen anzeigen ein Literal, eine Konstante und einer Variablen. Jeweils bildet einen gültigen numerischen Ausdruck selbst. Die letzte Zeile zeigt eine Kombination einer Variablen mit zwei Literalen.  
  
     Beachten Sie, dass ein numerisches Ausdrucks eine vollständige Visual Basic-Anweisung nicht allein Formular ist. Sie müssen den Ausdruck im Rahmen einer vollständigen-Anweisung verwenden.  
  
#### <a name="to-store-a-numeric-value"></a>Um einen numerischen Wert zu speichern.  
  
-   Eine zuweisungsanweisung können Sie den Wert dargestellt durch einen numerischen Ausdruck einer Variablen zuweisen, wie im folgende Beispiel veranschaulicht.  
  
     [!code-vb[VbVbalrOperators#82](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_1.vb)]  
  
     Im vorherigen Beispiel der Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators (`=`) der Variablen zugewiesen `j` auf der linken Seite des Operators, sodass `j` 276 ergibt.  
  
     Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Mehrere Operatoren  
 Wenn der numerische Ausdruck mehrere Operatoren enthält, wird die Reihenfolge, die Auswertung, von den Regeln der Operatorrangfolge bestimmt. Um die Regeln der Operatorrangfolge überschreiben möchten, schließen Sie Ausdrücke in Klammern ein, wie im obigen Beispiel; die Ausdrücke ein Klammern werden zuerst ausgewertet.  
  
#### <a name="to-override-normal-operator-precedence"></a>Normale Operatorrangfolge überschreiben  
  
-   Verwenden Sie Klammern, um die Vorgänge einzuschließen, zuerst ausgeführt werden sollen. Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit dem gleichen Operanden und Operatoren.  
  
     [!code-vb[VbVbalrOperators#83](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-calculate-numeric-values_2.vb)]  
  
     Im vorherigen Beispiel, die Berechnung von `j` führt den Addition-Operator (`+`) erste da Klammern `(67 + i)` Überschreiben von normalen Vorrang und den zugewiesenen Wert `j` 276 (4 Mal 69) ist. Die Berechnung von `k` führt die Operatoren in der normalen Rangfolge (`*` vor `+`), und den zugewiesenen Wert `k` ist 270 (268 plus 2).  
  
     Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
