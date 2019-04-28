---
title: 'Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665935"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="1ad4a-102">Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ad4a-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="1ad4a-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="1ad4a-104">Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="1ad4a-105">Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="1ad4a-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="1ad4a-106">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1ad4a-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="1ad4a-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="1ad4a-108">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1ad4a-109">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="1ad4a-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="1ad4a-111">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Hauptteil der Funktion.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="1ad4a-112">Der Wert, dem der Ausdruck ergibt, ist der von der Funktion zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="1ad4a-113">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="1ad4a-114">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="1ad4a-115">Alternativ wird das gleiche Ergebnis im folgenden Beispiel erreicht:</span><span class="sxs-lookup"><span data-stu-id="1ad4a-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="1ad4a-116">Um eine Unterroutine der einzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1ad4a-117">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="1ad4a-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="1ad4a-119">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1ad4a-120">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="1ad4a-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="1ad4a-122">Geben Sie nach der Parameterliste einer einzelnen Anweisung als Text der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="1ad4a-123">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="1ad4a-124">Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="1ad4a-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="1ad4a-125">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="1ad4a-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="1ad4a-127">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="1ad4a-128">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="1ad4a-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="1ad4a-130">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-130">Press ENTER.</span></span> <span data-ttu-id="1ad4a-131">Die `End Function` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1ad4a-132">Fügen Sie im Text der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="1ad4a-133">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="1ad4a-134">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="1ad4a-135">Um eine Unterroutine der mehrzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="1ad4a-136">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1ad4a-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="1ad4a-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="1ad4a-138">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="1ad4a-139">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="1ad4a-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="1ad4a-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="1ad4a-141">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-141">Press ENTER.</span></span> <span data-ttu-id="1ad4a-142">Die `End Sub` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="1ad4a-143">Fügen Sie den folgenden Code ausgeführt wird, wenn die Unterroutine aufgerufen wird, innerhalb des Texts der Funktion.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="1ad4a-144">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="1ad4a-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ad4a-145">Example</span></span>  
 <span data-ttu-id="1ad4a-146">Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="1ad4a-147">Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A> Methode gibt ein Array von auf dem lokalen Computer ausgeführten Prozesse.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="1ad4a-148">Die <xref:System.Linq.Enumerable.Where%2A> Methode aus der <xref:System.Linq.Enumerable> Klasse erfordert eine `Boolean` als Argument zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="1ad4a-149">Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="1ad4a-150">Es gibt `True` für jeden Prozess, der nur ein Thread besitzt und diese werden in ausgewählt `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="1ad4a-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="1ad4a-151">Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, im [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Syntax:</span><span class="sxs-lookup"><span data-stu-id="1ad4a-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="1ad4a-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ad4a-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="1ad4a-153">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1ad4a-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="1ad4a-154">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ad4a-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="1ad4a-155">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ad4a-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1ad4a-156">Delegaten</span><span class="sxs-lookup"><span data-stu-id="1ad4a-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="1ad4a-157">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ad4a-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="1ad4a-158">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1ad4a-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="1ad4a-159">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1ad4a-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
