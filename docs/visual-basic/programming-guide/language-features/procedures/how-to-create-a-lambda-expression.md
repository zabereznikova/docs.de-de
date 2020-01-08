---
title: 'Gewusst wie: Erstellen eines Lambda-Ausdrucks'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 1c65841e4c124252cfa41bcd4d0c305a426687ee
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75632349"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die keinen Namen hat. Ein Lambda-Ausdruck kann überall dort verwendet werden, wo ein Delegattyp gültig ist.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>So erstellen Sie eine einzeilige Lambda-Ausdrucks Funktion  
  
1. Wenn ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`ein, wie im folgenden Beispiel gezeigt:  
  
     `Dim add1 =`   `Function`  
  
2. Geben Sie in Klammern direkt nach `Function`die Parameter der Funktion ein. Beachten Sie, dass Sie nach `Function`keinen Namen angeben.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion ein. Der Wert, zu dem der Ausdruck ausgewertet wird, ist der Wert, der von der Funktion zurückgegeben wird. Sie verwenden keine `As`-Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. Das gleiche Ergebnis wird auch im folgenden Beispiel erreicht:  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>So erstellen Sie eine einzeilige Lambda-Ausdrucks Unterroutine  
  
1. Wenn ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`ein, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Sub`  
  
2. Geben Sie in Klammern direkt nach `Sub`die Parameter der Unterroutine ein. Beachten Sie, dass Sie nach `Sub`keinen Namen angeben.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. Geben Sie nach der Parameterliste eine einzelne Anweisung als Text der Unterroutine ein.  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichen folgen Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>So erstellen Sie eine mehrzeilige Lambda-Ausdrucks Funktion  
  
1. Wenn ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`ein, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Function`  
  
2. Geben Sie in Klammern direkt nach `Function`die Parameter der Funktion ein. Beachten Sie, dass Sie nach `Function`keinen Namen angeben.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. Drücken Sie die EINGABETASTE. Die `End Function`-Anweisung wird automatisch hinzugefügt.  
  
4. Fügen Sie im Textkörper der Funktion den folgenden Code hinzu, um einen Ausdruck zu erstellen, und geben Sie den Wert zurück. Sie verwenden keine `As`-Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>So erstellen Sie eine mehrzeilige Lambda-Ausdrucks Unterroutine  
  
1. Wenn ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`ein, wie im folgenden Beispiel gezeigt:  
  
     `Dim add1 =`   `Sub`  
  
2. Geben Sie in Klammern direkt nach `Sub`die Parameter der Unterroutine ein. Beachten Sie, dass Sie nach `Sub`keinen Namen angeben.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. Drücken Sie die EINGABETASTE. Die `End Sub`-Anweisung wird automatisch hinzugefügt.  
  
4. Fügen Sie im Textkörper der Funktion den folgenden Code hinzu, der ausgeführt werden soll, wenn die Unterroutine aufgerufen wird.  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichen folgen Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>Beispiel  
 Lambda-Ausdrücke werden häufig verwendet, um eine Funktion zu definieren, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`ist. Im folgenden Beispiel gibt die <xref:System.Diagnostics.Process.GetProcesses%2A>-Methode ein Array der Prozesse zurück, die auf dem lokalen Computer ausgeführt werden. Die <xref:System.Linq.Enumerable.Where%2A>-Methode aus der <xref:System.Linq.Enumerable>-Klasse erfordert einen `Boolean` Delegaten als Argument. Der Lambda-Ausdruck im Beispiel wird zu diesem Zweck verwendet. Sie gibt `True` für jeden Prozess zurück, der nur einen Thread hat, und diese werden in `filteredList`ausgewählt.  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 Das vorherige Beispiel entspricht dem folgenden Code, der in der Language-Integrated Query (LINQ)-Syntax geschrieben ist:  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq.Enumerable>
- [Lambda-Ausdrücke](./lambda-expressions.md)
- [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
