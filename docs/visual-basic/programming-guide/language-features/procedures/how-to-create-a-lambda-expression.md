---
title: 'Gewusst wie: Erstellen eines Lambda-Ausdrucks (Visual Basic) | Microsoft-Dokumentation'
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
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 5e105e87b1e63218f2c3c2204350257c139b5837
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)
Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt. Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Function`, wie im folgenden Beispiel:  
  
     `Dim add1 =`   `Function`  
  
2.  In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion. Beachten Sie, dass Sie nicht nach Namen angeben `Function`.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion. Der Wert, dem der Ausdruck ausgewertet wird, ist der von der Funktion zurückgegebene Wert. Verwenden Sie eine `As` -Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  Alternativ erfolgt das gleiche Ergebnis im folgenden Beispiel:  
  
     [!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>Erstellen Sie eine Unterroutine der einzeiligen Lambda-Ausdruck  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Sub`  
  
2.  In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine. Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  Geben Sie nach der Parameterliste eine einzelne Anweisung als Text der Unterroutine ein.  
  
     [!code-vb[VbVbalrLambdas&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.  
  
     `Dim add1 =`   `Function`  
  
2.  In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion. Beachten Sie, dass Sie nicht nach Namen angeben `Function`.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Drücken Sie die EINGABETASTE. Die `End Function` -Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie im Hauptteil der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben. Verwenden Sie eine `As` -Klausel, um den Rückgabetyp anzugeben.  
  
     [!code-vb[VbVbalrLambdas Nr.&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.  
  
     [!code-vb[VbVbalrLambdas&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>Erstellen Sie eine mehrzeilige Lambda-Ausdruck-Unterroutine  
  
1.  Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:  
  
     `Dim add1 =`   `Sub`  
  
2.  In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine. Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Drücken Sie die EINGABETASTE. Die `End Sub` -Anweisung wird automatisch hinzugefügt.  
  
4.  Fügen Sie im Hauptteil der Funktion den folgenden Code ausführen, wenn die Unterroutine aufgerufen wird.  
  
     [!code-vb[VbVbalrLambdas&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.  
  
     [!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>Beispiel  
 Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`. Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A>-Methode gibt ein Array der auf dem lokalen Computer ausgeführten Prozesse.</xref:System.Diagnostics.Process.GetProcesses%2A> Die <xref:System.Linq.Enumerable.Where%2A>Methode aus der <xref:System.Linq.Enumerable>Klasse erfordert eine `Boolean` als Argument zu delegieren.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A> Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet. Es gibt `True` für jeden Prozess, bei dem nur ein Thread, und diese werden in ausgewählt `filteredList`.  
  
 [!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Syntax:  
  
 [!code-vb[VbVbalrLambdas&#11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Lambda-Ausdrücke](./lambda-expressions.md)   
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
