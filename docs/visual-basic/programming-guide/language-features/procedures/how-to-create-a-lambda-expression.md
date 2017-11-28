---
title: 'Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16365b64e5430be61c113ac7601154df260e4ca5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="6d4a8-102">Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d4a8-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="6d4a8-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine vorstellen, die nicht über einen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="6d4a8-104">Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="6d4a8-105">Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="6d4a8-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="6d4a8-106">In allen Situationen, in denen ein Delegattyp verwendet werden kann kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="6d4a8-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="6d4a8-108">Die in Klammern direkt nach dem `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6d4a8-109">Beachten Sie, dass Sie keinen Namen nach dem angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6d4a8-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="6d4a8-111">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="6d4a8-112">Der Wert, dem der ausgewertete Ausdruck wird von der Funktion zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="6d4a8-113">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     <span data-ttu-id="6d4a8-114">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  <span data-ttu-id="6d4a8-115">Alternativ wird das gleiche Ergebnis im folgenden Beispiel erzielt:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="6d4a8-116">So erstellen eine einzeilige Lambda-Ausdruck Unterroutine</span><span class="sxs-lookup"><span data-stu-id="6d4a8-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="6d4a8-117">In allen Situationen, in denen ein Delegattyp verwendet werden kann kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6d4a8-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="6d4a8-119">Die in Klammern direkt nach dem `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6d4a8-120">Beachten Sie, dass Sie keinen Namen nach dem angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6d4a8-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="6d4a8-122">Geben Sie nach der Parameterliste einer einzelnen Anweisung als Text der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     <span data-ttu-id="6d4a8-123">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="6d4a8-124">Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="6d4a8-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="6d4a8-125">In allen Situationen, in denen ein Delegattyp verwendet werden kann kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="6d4a8-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="6d4a8-127">Die in Klammern direkt nach dem `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="6d4a8-128">Beachten Sie, dass Sie keinen Namen nach dem angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="6d4a8-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="6d4a8-130">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-130">Press ENTER.</span></span> <span data-ttu-id="6d4a8-131">Die `End Function` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="6d4a8-132">Fügen Sie im Text der Funktion den folgenden Code, um einen Ausdruck erstellen, und der Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="6d4a8-133">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     <span data-ttu-id="6d4a8-134">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="6d4a8-135">So erstellen eine mehrzeiliger Lambda-Ausdruck-Unterroutine</span><span class="sxs-lookup"><span data-stu-id="6d4a8-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="6d4a8-136">In allen Situationen, in denen ein Delegattyp verwendet werden kann kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="6d4a8-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="6d4a8-138">Die in Klammern direkt nach dem `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="6d4a8-139">Beachten Sie, dass Sie keinen Namen nach dem angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="6d4a8-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="6d4a8-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="6d4a8-141">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-141">Press ENTER.</span></span> <span data-ttu-id="6d4a8-142">Die `End Sub` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="6d4a8-143">Fügen Sie den folgenden Code ausführen, wenn die Unterroutine aufgerufen wird, innerhalb des Texts der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     <span data-ttu-id="6d4a8-144">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a><span data-ttu-id="6d4a8-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d4a8-145">Example</span></span>  
 <span data-ttu-id="6d4a8-146">Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definieren, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="6d4a8-147">Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A> Methode gibt ein Array von auf dem lokalen Computer ausgeführten Prozesse.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="6d4a8-148">Die <xref:System.Linq.Enumerable.Where%2A> Methode aus der <xref:System.Linq.Enumerable> Klasse erfordert eine `Boolean` als Argument zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="6d4a8-149">Im Beispiel wird der Lambda-Ausdruck wird zu diesem Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="6d4a8-150">Es gibt `True` für jeden Prozess besitzt, die nur einen Thread, und diese werden in ausgewählt `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="6d4a8-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 <span data-ttu-id="6d4a8-151">Im vorherige Beispiel entspricht dem folgenden Code, der geschriebene [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Syntax:</span><span class="sxs-lookup"><span data-stu-id="6d4a8-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6d4a8-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d4a8-152">See Also</span></span>  
 <xref:System.Linq.Enumerable>  
 [<span data-ttu-id="6d4a8-153">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6d4a8-153">Lambda Expressions</span></span>](./lambda-expressions.md)  
 [<span data-ttu-id="6d4a8-154">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6d4a8-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="6d4a8-155">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6d4a8-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="6d4a8-156">Delegaten</span><span class="sxs-lookup"><span data-stu-id="6d4a8-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="6d4a8-157">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d4a8-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="6d4a8-158">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6d4a8-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="6d4a8-159">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d4a8-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
