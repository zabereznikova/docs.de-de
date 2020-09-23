---
title: 'Vorgehensweise: Erstellen eines Lambdaausdrucks'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: cc2de38f7375848d104edff6f419656d9caa9cb2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071923"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="f7806-102">Gewusst wie: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7806-102">How to: Create a Lambda Expression (Visual Basic)</span></span>

<span data-ttu-id="f7806-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die keinen Namen hat.</span><span class="sxs-lookup"><span data-stu-id="f7806-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="f7806-104">Ein Lambda-Ausdruck kann überall dort verwendet werden, wo ein Delegattyp gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f7806-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="f7806-105">So erstellen Sie eine einzeilige Lambda-Ausdrucks Funktion</span><span class="sxs-lookup"><span data-stu-id="f7806-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="f7806-106">Geben Sie in jeder Situation, in der ein Delegattyp verwendet werden könnte, das-Schlüsselwort ein `Function` , wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f7806-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="f7806-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="f7806-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="f7806-108">Geben Sie in Klammern direkt nach `Function` die Parameter der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="f7806-109">Beachten Sie, dass Sie nach keinen Namen angeben `Function` .</span><span class="sxs-lookup"><span data-stu-id="f7806-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="f7806-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="f7806-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="f7806-111">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Text der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="f7806-112">Der Wert, zu dem der Ausdruck ausgewertet wird, ist der Wert, der von der Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f7806-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="f7806-113">Sie verwenden keine- `As` Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="f7806-114">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="f7806-115">Das gleiche Ergebnis wird auch im folgenden Beispiel erreicht:</span><span class="sxs-lookup"><span data-stu-id="f7806-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="f7806-116">So erstellen Sie eine einzeilige Lambda-Ausdrucks Unterroutine</span><span class="sxs-lookup"><span data-stu-id="f7806-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="f7806-117">Geben Sie in jeder Situation, in der ein Delegattyp verwendet werden könnte, das-Schlüsselwort ein `Sub` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7806-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f7806-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="f7806-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="f7806-119">Geben Sie in Klammern direkt nach `Sub` die Parameter der Unterroutine ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="f7806-120">Beachten Sie, dass Sie nach keinen Namen angeben `Sub` .</span><span class="sxs-lookup"><span data-stu-id="f7806-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="f7806-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="f7806-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="f7806-122">Geben Sie nach der Parameterliste eine einzelne Anweisung als Text der Unterroutine ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="f7806-123">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichen folgen Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="f7806-124">So erstellen Sie eine mehrzeilige Lambda-Ausdrucks Funktion</span><span class="sxs-lookup"><span data-stu-id="f7806-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="f7806-125">Geben Sie in jeder Situation, in der ein Delegattyp verwendet werden könnte, das-Schlüsselwort ein `Function` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7806-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f7806-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="f7806-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="f7806-127">Geben Sie in Klammern direkt nach `Function` die Parameter der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="f7806-128">Beachten Sie, dass Sie nach keinen Namen angeben `Function` .</span><span class="sxs-lookup"><span data-stu-id="f7806-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="f7806-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="f7806-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="f7806-130">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f7806-130">Press ENTER.</span></span> <span data-ttu-id="f7806-131">Die- `End Function` Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7806-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="f7806-132">Fügen Sie im Textkörper der Funktion den folgenden Code hinzu, um einen Ausdruck zu erstellen, und geben Sie den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="f7806-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="f7806-133">Sie verwenden keine- `As` Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="f7806-134">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="f7806-135">So erstellen Sie eine mehrzeilige Lambda-Ausdrucks Unterroutine</span><span class="sxs-lookup"><span data-stu-id="f7806-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="f7806-136">Geben Sie in jeder Situation, in der ein Delegattyp verwendet werden könnte, das-Schlüsselwort ein `Sub` , wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f7806-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="f7806-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="f7806-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="f7806-138">Geben Sie in Klammern direkt nach `Sub` die Parameter der Unterroutine ein.</span><span class="sxs-lookup"><span data-stu-id="f7806-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="f7806-139">Beachten Sie, dass Sie nach keinen Namen angeben `Sub` .</span><span class="sxs-lookup"><span data-stu-id="f7806-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="f7806-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="f7806-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="f7806-141">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f7806-141">Press ENTER.</span></span> <span data-ttu-id="f7806-142">Die- `End Sub` Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7806-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="f7806-143">Fügen Sie im Textkörper der Funktion den folgenden Code hinzu, der ausgeführt werden soll, wenn die Unterroutine aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f7806-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="f7806-144">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichen folgen Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="f7806-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="f7806-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7806-145">Example</span></span>  

 <span data-ttu-id="f7806-146">Lambda-Ausdrücke werden häufig verwendet, um eine Funktion zu definieren, die als Argument für einen Parameter mit dem Typ übergeben werden kann `Delegate` .</span><span class="sxs-lookup"><span data-stu-id="f7806-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="f7806-147">Im folgenden Beispiel gibt die- <xref:System.Diagnostics.Process.GetProcesses%2A> Methode ein Array der Prozesse zurück, die auf dem lokalen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f7806-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="f7806-148">Die-Methode der- <xref:System.Linq.Enumerable.Where%2A> <xref:System.Linq.Enumerable> Klasse erfordert einen Delegaten `Boolean` als Argument.</span><span class="sxs-lookup"><span data-stu-id="f7806-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="f7806-149">Der Lambda-Ausdruck im Beispiel wird zu diesem Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="f7806-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="f7806-150">Er gibt `True` für jeden Prozess zurück, der nur einen Thread hat, und diese werden in ausgewählt `filteredList` .</span><span class="sxs-lookup"><span data-stu-id="f7806-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="f7806-151">Das vorherige Beispiel entspricht dem folgenden Code, der in der Language-Integrated Query (LINQ)-Syntax geschrieben ist:</span><span class="sxs-lookup"><span data-stu-id="f7806-151">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="f7806-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7806-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="f7806-153">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f7806-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="f7806-154">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f7806-154">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="f7806-155">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f7806-155">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="f7806-156">Delegaten</span><span class="sxs-lookup"><span data-stu-id="f7806-156">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="f7806-157">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7806-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="f7806-158">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f7806-158">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="f7806-159">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f7806-159">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
