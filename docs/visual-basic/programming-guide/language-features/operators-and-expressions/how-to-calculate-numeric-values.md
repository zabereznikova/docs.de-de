---
title: 'Vorgehensweise: Berechnen von numerischen Werten'
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
ms.openlocfilehash: 94b02693f308dcfcfa6983f2750a26d9d419f7be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403458"
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
  
     Im vorangehenden Beispiel wird der Wert des Ausdrucks auf der rechten Seite des Gleichheits Operators ( `=` ) der Variablen `j` auf der linken Seite des Operators zugewiesen, daher ergibt den Wert `j` 276.  
  
     Weitere Informationen finden Sie unter [Transact-SQL-Anweisungen](../../../language-reference/statements/index.md).  
  
## <a name="multiple-operators"></a>Mehrere Operatoren  
 Wenn der numerische Ausdruck mehr als einen Operator enthält, wird die Reihenfolge, in der Sie ausgewertet werden, durch die Regeln der Operator Rangfolge bestimmt. Um die Regeln der Operator Rangfolge zu überschreiben, schließen Sie Ausdrücke in Klammern ein, wie im obigen Beispiel gezeigt. die eingeschlossenen Ausdrücke werden zuerst ausgewertet.  
  
#### <a name="to-override-normal-operator-precedence"></a>So überschreiben Sie normale Operator Rangfolge  
  
- Verwenden Sie Klammern, um die Vorgänge, die zuerst ausgeführt werden sollen, einzuschließen. Das folgende Beispiel zeigt zwei unterschiedliche Ergebnisse mit denselben Operanden und Operatoren.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     Im vorherigen Beispiel führt die Berechnung für `j` den Additions Operator ( `+` ) zuerst aus, da die Klammern um die `(67 + i)` normale Rangfolge überschreiben, und der zugewiesene Wert `j` ist 276 (4 mal 69). Die Berechnung für `k` führt die Operatoren in ihrer normalen Rangfolge ( `*` vor `+` ) aus, und der zugewiesene Wert `k` ist 270 (268 plus 2).  
  
     Weitere Informationen finden Sie unter [Operator Rangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Operatoren und Ausdrücke](index.md)
- [Wertvergleiche](value-comparisons.md)
- [Anweisungen](../../../language-reference/statements/index.md)
- [Operatorrangfolge in Visual Basic](../../../language-reference/operators/operator-precedence.md)
- [Arithmetische Operatoren](../../../language-reference/operators/arithmetic-operators.md)
- [Effiziente Kombination von Operatoren](efficient-combination-of-operators.md)
