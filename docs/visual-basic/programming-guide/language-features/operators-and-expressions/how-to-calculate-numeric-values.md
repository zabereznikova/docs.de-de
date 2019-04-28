---
title: 'Vorgehensweise: Berechnen von numerischen Werten (Visual Basic)'
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
ms.openlocfilehash: 33184d9be275f5e777ffd79c6dd4e3182d865de7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864680"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Vorgehensweise: Berechnen von numerischen Werten (Visual Basic)
Sie können numerische Werte durch die Verwendung von numerischen Ausdrücken berechnen. Ein *numerischer Ausdruck* ist ein Ausdruck mit Literalen, Konstanten und Variablen, die Darstellung von numerischer Werten und Operatoren, die für diese Werte dienen.  
  
## <a name="calculating-numeric-values"></a>Berechnen von numerischen Werten  
  
#### <a name="to-calculate-a-numeric-value"></a>Um einen numerischen Wert zu berechnen.  
  
- Kombinieren Sie mindestens eine numerischen Literalen, Konstanten und Variablen in einen numerischen Ausdruck. Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     Die ersten drei Zeilen zeigen ein Literal, eine Konstante und einer Variablen. Jeder bildet einen gültigen numerischen Ausdruck selbst. Die letzte Zeile zeigt eine Kombination aus einer Variablen mit zwei Literale.  
  
     Beachten Sie, dass ein numerischer Ausdruck eine vollständige Visual Basic-Anweisung selbst bilden keine ist. Sie müssen den Ausdruck als Teil des eine vollständige Anweisung verwenden.  
  
#### <a name="to-store-a-numeric-value"></a>Um einen numerischen Wert zu speichern.  
  
- Sie können eine zuweisungsanweisung verwenden, den durch einen numerischen Ausdruck auf eine Variable dargestellten Wert zuweisen, wie im folgende Beispiel wird veranschaulicht.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     Im vorherigen Beispiel den Wert des Ausdrucks auf der rechten Seite des Gleichheitsoperators (`=`) der Variablen zugewiesen ist `j` auf der linken Seite des Operators, sodass `j` 276 ergibt.  
  
     Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Mehrere Operatoren  
 Wenn der numerische Ausdruck mehrere Operatoren enthält, wird die Reihenfolge, in der sie ausgewertet werden, durch die Regeln der Operatorrangfolge bestimmt. Um die Regeln der Operatorrangfolge zu überschreiben, müssen Sie die Ausdrücke in Klammern ein, wie im obigen Beispiel; die Ausdrücke ein Klammern werden zuerst ausgewertet.  
  
#### <a name="to-override-normal-operator-precedence"></a>Überschreiben der normalen Operatorrangfolge  
  
- Verwenden Sie Klammern, um die Vorgänge einzuschließen, die zuerst ausgeführt werden sollen. Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit dem gleichen Operanden und Operatoren.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     Im vorherigen Beispiel, der Berechnung für `j` der Additionsoperator (`+`) ersten da Klammern `(67 + i)` überschreiben normale Rangfolge und den zugewiesenen Wert `j` 276 (4-Mal so 69) ist. Die Berechnung für `k` führt die Operatoren in der normalen Rangfolge (`*` vor `+`), und der zugewiesene Wert `k` ist 270 (268 plus 2).  
  
     Weitere Informationen finden Sie unter [Operatorrangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch

- [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
