---
title: 'Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: 8754049e493ab23b1e7b01d0f315b00bdebf0378
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841419"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="4f1aa-102">Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f1aa-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="4f1aa-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="4f1aa-104">Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="4f1aa-105">Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f1aa-105">To create a single-line lambda expression function</span></span>  
  
1.  <span data-ttu-id="4f1aa-106">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4f1aa-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="4f1aa-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-107">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="4f1aa-108">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="4f1aa-109">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="4f1aa-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3.  <span data-ttu-id="4f1aa-111">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Hauptteil der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="4f1aa-112">Der Wert, dem der Ausdruck ergibt, ist der von der Funktion zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="4f1aa-113">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="4f1aa-114">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4.  <span data-ttu-id="4f1aa-115">Alternativ wird das gleiche Ergebnis im folgenden Beispiel erreicht:</span><span class="sxs-lookup"><span data-stu-id="4f1aa-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="4f1aa-116">Um eine Unterroutine der einzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-116">To create a single-line lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="4f1aa-117">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="4f1aa-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-118">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="4f1aa-119">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="4f1aa-120">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="4f1aa-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="4f1aa-122">Geben Sie nach der Parameterliste einer einzelnen Anweisung als Text der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="4f1aa-123">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="4f1aa-124">Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="4f1aa-124">To create a multiline lambda expression function</span></span>  
  
1.  <span data-ttu-id="4f1aa-125">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="4f1aa-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-126">`Dim add1 =`   `Function`</span></span>  
  
2.  <span data-ttu-id="4f1aa-127">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="4f1aa-128">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="4f1aa-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3.  <span data-ttu-id="4f1aa-130">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-130">Press ENTER.</span></span> <span data-ttu-id="4f1aa-131">Die `End Function` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-131">The `End Function` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="4f1aa-132">Fügen Sie im Text der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="4f1aa-133">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="4f1aa-134">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="4f1aa-135">Um eine Unterroutine der mehrzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-135">To create a multiline lambda expression subroutine</span></span>  
  
1.  <span data-ttu-id="4f1aa-136">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4f1aa-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="4f1aa-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-137">`Dim add1 =`   `Sub`</span></span>  
  
2.  <span data-ttu-id="4f1aa-138">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="4f1aa-139">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="4f1aa-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="4f1aa-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3.  <span data-ttu-id="4f1aa-141">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-141">Press ENTER.</span></span> <span data-ttu-id="4f1aa-142">Die `End Sub` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-142">The `End Sub` statement is automatically added.</span></span>  
  
4.  <span data-ttu-id="4f1aa-143">Fügen Sie den folgenden Code ausgeführt wird, wenn die Unterroutine aufgerufen wird, innerhalb des Texts der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="4f1aa-144">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="4f1aa-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4f1aa-145">Example</span></span>  
 <span data-ttu-id="4f1aa-146">Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="4f1aa-147">Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A> Methode gibt ein Array von auf dem lokalen Computer ausgeführten Prozesse.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="4f1aa-148">Die <xref:System.Linq.Enumerable.Where%2A> Methode aus der <xref:System.Linq.Enumerable> Klasse erfordert eine `Boolean` als Argument zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="4f1aa-149">Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="4f1aa-150">Es gibt `True` für jeden Prozess, der nur ein Thread besitzt und diese werden in ausgewählt `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="4f1aa-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="4f1aa-151">Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, im [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Syntax:</span><span class="sxs-lookup"><span data-stu-id="4f1aa-151">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="4f1aa-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f1aa-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="4f1aa-153">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="4f1aa-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="4f1aa-154">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4f1aa-154">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4f1aa-155">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4f1aa-155">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="4f1aa-156">Delegaten</span><span class="sxs-lookup"><span data-stu-id="4f1aa-156">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="4f1aa-157">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f1aa-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="4f1aa-158">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4f1aa-158">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="4f1aa-159">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f1aa-159">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
