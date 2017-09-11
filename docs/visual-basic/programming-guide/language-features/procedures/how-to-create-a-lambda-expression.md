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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: edd475490dce81ff9cca32b5f9a5090d99f4d80d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="b9432-102">Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9432-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="b9432-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b9432-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="b9432-104">Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b9432-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="b9432-105">Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="b9432-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="b9432-106">Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Function`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b9432-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="b9432-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="b9432-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="b9432-108">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="b9432-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="b9432-109">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="b9432-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="b9432-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="b9432-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="b9432-111">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="b9432-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="b9432-112">Der Wert, dem der Ausdruck ausgewertet wird, ist der von der Funktion zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="b9432-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="b9432-113">Verwenden Sie eine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="b9432-114">[!code-vb[VbVbalrLambdas&#1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-114">[!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]</span></span>  
  
     <span data-ttu-id="b9432-115">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-115">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="b9432-116">[!code-vb[VbVbalrLambdas&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-116">[!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]</span></span>  
  
4.  <span data-ttu-id="b9432-117">Alternativ erfolgt das gleiche Ergebnis im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b9432-117">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     <span data-ttu-id="b9432-118">[!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-118">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="b9432-119">Erstellen Sie eine Unterroutine der einzeiligen Lambda-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="b9432-119">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="b9432-120">Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9432-120">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b9432-121">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="b9432-121">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="b9432-122">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="b9432-122">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="b9432-123">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="b9432-123">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="b9432-124">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="b9432-124">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="b9432-125">Geben Sie nach der Parameterliste eine einzelne Anweisung als Text der Unterroutine ein.</span><span class="sxs-lookup"><span data-stu-id="b9432-125">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     <span data-ttu-id="b9432-126">[!code-vb[VbVbalrLambdas&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-126">[!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]</span></span>  
  
     <span data-ttu-id="b9432-127">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-127">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="b9432-128">[!code-vb[VbVbalrLambdas&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-128">[!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="b9432-129">Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="b9432-129">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="b9432-130">Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b9432-130">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b9432-131">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="b9432-131">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="b9432-132">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="b9432-132">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="b9432-133">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="b9432-133">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="b9432-134">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="b9432-134">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="b9432-135">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b9432-135">Press ENTER.</span></span> <span data-ttu-id="b9432-136">Die `End Function` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9432-136">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="b9432-137">Fügen Sie im Hauptteil der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-137">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="b9432-138">Verwenden Sie eine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-138">You do not use an `As` clause to specify the return type.</span></span>  
  
     <span data-ttu-id="b9432-139">[!code-vb[VbVbalrLambdas Nr.&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-139">[!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]</span></span>  
  
     <span data-ttu-id="b9432-140">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-140">You call the lambda expression by passing in an integer argument.</span></span>  
  
     <span data-ttu-id="b9432-141">[!code-vb[VbVbalrLambdas&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-141">[!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]</span></span>  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="b9432-142">Erstellen Sie eine mehrzeilige Lambda-Ausdruck-Unterroutine</span><span class="sxs-lookup"><span data-stu-id="b9432-142">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="b9432-143">Geben Sie in einer Situation, in der ein Delegattyp verwendet werden kann, das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="b9432-143">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="b9432-144">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="b9432-144">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="b9432-145">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="b9432-145">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="b9432-146">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="b9432-146">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="b9432-147">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="b9432-147">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="b9432-148">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b9432-148">Press ENTER.</span></span> <span data-ttu-id="b9432-149">Die `End Sub` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9432-149">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="b9432-150">Fügen Sie im Hauptteil der Funktion den folgenden Code ausführen, wenn die Unterroutine aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b9432-150">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     <span data-ttu-id="b9432-151">[!code-vb[VbVbalrLambdas&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-151">[!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]</span></span>  
  
     <span data-ttu-id="b9432-152">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="b9432-152">You call the lambda expression by passing in a string argument.</span></span>  
  
     <span data-ttu-id="b9432-153">[!code-vb[VbVbalrLambdas&#22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-153">[!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9432-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9432-154">Example</span></span>  
 <span data-ttu-id="b9432-155">Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="b9432-155">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="b9432-156">Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A>-Methode gibt ein Array der auf dem lokalen Computer ausgeführten Prozesse.</xref:System.Diagnostics.Process.GetProcesses%2A></span><span class="sxs-lookup"><span data-stu-id="b9432-156">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="b9432-157">Die <xref:System.Linq.Enumerable.Where%2A>Methode aus der <xref:System.Linq.Enumerable>Klasse erfordert eine `Boolean` als Argument zu delegieren.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="b9432-157">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="b9432-158">Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9432-158">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="b9432-159">Es gibt `True` für jeden Prozess, bei dem nur ein Thread, und diese werden in ausgewählt `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="b9432-159">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 <span data-ttu-id="b9432-160">[!code-vb[VbVbalrLambdas&#10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-160">[!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]</span></span>  
  
 <span data-ttu-id="b9432-161">Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] Syntax:</span><span class="sxs-lookup"><span data-stu-id="b9432-161">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] syntax:</span></span>  
  
 <span data-ttu-id="b9432-162">[!code-vb[VbVbalrLambdas&#11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="b9432-162">[!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9432-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9432-163">See Also</span></span>  
 <span data-ttu-id="b9432-164"><xref:System.Linq.Enumerable></xref:System.Linq.Enumerable></span><span class="sxs-lookup"><span data-stu-id="b9432-164"><xref:System.Linq.Enumerable></span></span>   
<span data-ttu-id="b9432-165"> [Lambda-Ausdrücke](./lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-165"> [Lambda Expressions](./lambda-expressions.md) </span></span>  
<span data-ttu-id="b9432-166"> [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-166"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="b9432-167"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-167"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="b9432-168"> [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-168"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="b9432-169"> [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-169"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="b9432-170"> [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b9432-170"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="b9432-171"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="b9432-171"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
