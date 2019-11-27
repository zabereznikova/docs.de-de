---
title: 'Gewusst wie: Berechnen von numerischen Werten'
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
ms.openlocfilehash: d213f6b5a4abf8c52d8872ae36e89796183ff27c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348964"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>Gewusst wie: Berechnen von numerischen Werten (Visual Basic)
Numerische Werte können mithilfe numerischer Ausdrücke berechnet werden. Ein *numerischer Ausdruck* ist ein Ausdruck, der Literale, Konstanten und Variablen, die numerische Werte darstellen, sowie Operatoren enthält, die auf diese Werte reagieren.  
  
## <a name="calculating-numeric-values"></a>Berechnen von numerischen Werten  
  
#### <a name="to-calculate-a-numeric-value"></a>So berechnen Sie einen numerischen Wert  
  
- Kombinieren Sie eine oder mehrere numerische Literale, Konstanten und Variablen in einem numerischen Ausdruck. Das folgende Beispiel zeigt einige gültige numerische Ausdrücke.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     In den ersten drei Zeilen wird ein Literalwert, eine Konstante und eine Variable angezeigt. Jede ist ein gültiger numerischer Ausdruck. In der letzten Zeile wird eine Kombination aus einer Variablen mit zwei literalen angezeigt.  
  
     Beachten Sie, dass ein numerischer Ausdruck nicht über eine komplette Visual Basic-Anweisung verfügt. Sie müssen den Ausdruck als Teil einer Complete-Anweisung verwenden.  
  
#### <a name="to-store-a-numeric-value"></a>So speichern Sie einen numerischen Wert  
  
- Sie können eine Zuweisungsanweisung verwenden, um den von einem numerischen Ausdruck dargestellten Wert einer Variablen zuzuweisen, wie im folgenden Beispiel veranschaulicht.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     Im vorherigen Beispiel wird der Wert des Ausdrucks auf der rechten Seite des Gleichheits Operators (`=`) der Variablen `j` auf der linken Seite des Operators zugewiesen, sodass `j` zu 276 ausgewertet wird.  
  
     Weitere Informationen finden Sie unter [Anweisungen](../../../../visual-basic/language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Mehrere Operatoren  
 Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge, in der Sie ausgewertet werden, durch die Regeln der Operator Rangfolge bestimmt. Um die Regeln der Operator Rangfolge zu überschreiben, schließen Sie Ausdrücke in Klammern ein, wie im obigen Beispiel gezeigt. die eingeschlossenen Ausdrücke werden zuerst ausgewertet.  
  
#### <a name="to-override-normal-operator-precedence"></a>So überschreiben Sie normale Operator Rangfolge  
  
- Verwenden Sie Klammern, um die Vorgänge, die zuerst ausgeführt werden sollen, einzuschließen. Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit denselben Operanden und Operatoren.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     Im vorherigen Beispiel führt die Berechnung für `j` zuerst den Additions Operator (`+`) aus, da die Klammern um `(67 + i)` die normale Rangfolge überschreiben, und der `j` zugewiesene Wert 276 (4 mal 69). Die Berechnung für `k` führt die Operatoren in ihrer normalen Rangfolge (`*` vor `+`) aus, und der `k` zugewiesene Wert ist 270 (268 plus 2).  
  
     Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Siehe auch

- [Operatoren und Ausdrücke](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Wertvergleiche](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Anweisungen](../../../../visual-basic/language-reference/statements/index.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Arithmetische Operatoren](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Effiziente Kombination von Operatoren](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
