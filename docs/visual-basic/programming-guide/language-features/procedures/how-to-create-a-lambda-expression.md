---
title: 'Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: f437166bc5206b4145d6508aa2131ec94d6eca95
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244893"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt. Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion  
  
1.  In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel:  
  
     `Dim add1 =`   `Function`  
  
2.  In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion. Beachten Sie, dass Sie nicht nach Namen angeben `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Hauptteil der Funktion. Der Wert, dem der Ausdruck ergibt, ist der von der Funktion zurückgegebene Wert. Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Alternativ wird das gleiche Ergebnis im folgenden Beispiel erreicht:  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Um eine Unterroutine der einzeiligen Lambda-Ausdruck zu erstellen.  
  
1.  In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Sub`  
  
2.  In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine. Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Geben Sie nach der Parameterliste einer einzelnen Anweisung als Text der Unterroutine.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion  
  
1.  In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Function`  
  
2.  In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion. Beachten Sie, dass Sie nicht nach Namen angeben `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Drücken Sie die EINGABETASTE. Die `End Function` -Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie im Text der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben. Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Um eine Unterroutine der mehrzeiligen Lambda-Ausdruck zu erstellen.  
  
1.  In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:  
  
     `Dim add1 =`   `Sub`  
  
2.  In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine. Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Drücken Sie die EINGABETASTE. Die `End Sub` -Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie den folgenden Code ausgeführt wird, wenn die Unterroutine aufgerufen wird, innerhalb des Texts der Funktion.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Beispiel  
 Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`. Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A> Methode gibt ein Array von auf dem lokalen Computer ausgeführten Prozesse. Die <xref:System.Linq.Enumerable.Where%2A> Methode aus der <xref:System.Linq.Enumerable> Klasse erfordert eine `Boolean` als Argument zu delegieren. Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet. Es gibt `True` für jeden Prozess, der nur ein Thread besitzt und diese werden in ausgewählt `filteredList`.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, im [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Syntax:  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.Enumerable>  
 [Lambda-Ausdrücke](./lambda-expressions.md)  
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
