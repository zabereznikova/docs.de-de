---
title: 'Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344545"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="39bae-102">Vorgehensweise: Erstellen eines Lambdaausdrucks (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39bae-102">How to: Create a Lambda Expression (Visual Basic)</span></span>
<span data-ttu-id="39bae-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine, die nicht über einen Namen verfügt.</span><span class="sxs-lookup"><span data-stu-id="39bae-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="39bae-104">Ein Lambda-Ausdruck kann verwendet werden, wo ein Delegattyp gültig ist.</span><span class="sxs-lookup"><span data-stu-id="39bae-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="39bae-105">Zum Erstellen einer einzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="39bae-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="39bae-106">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39bae-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="39bae-107">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="39bae-107">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="39bae-108">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="39bae-108">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. <span data-ttu-id="39bae-109">Geben Sie nach der Parameterliste einen einzelnen Ausdruck als Hauptteil der Funktion.</span><span class="sxs-lookup"><span data-stu-id="39bae-109">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="39bae-110">Der Wert, dem der Ausdruck ergibt, ist der von der Funktion zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="39bae-110">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="39bae-111">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-111">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="39bae-112">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-112">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="39bae-113">Alternativ wird das gleiche Ergebnis im folgenden Beispiel erreicht:</span><span class="sxs-lookup"><span data-stu-id="39bae-113">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="39bae-114">Um eine Unterroutine der einzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39bae-114">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="39bae-115">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39bae-115">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="39bae-116">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="39bae-116">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="39bae-117">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="39bae-117">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. <span data-ttu-id="39bae-118">Geben Sie nach der Parameterliste einer einzelnen Anweisung als Text der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="39bae-118">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="39bae-119">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-119">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="39bae-120">Zum Erstellen einer mehrzeiligen Lambda-Ausdruck-Funktion</span><span class="sxs-lookup"><span data-stu-id="39bae-120">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="39bae-121">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Function`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="39bae-121">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     `Dim add1 =`   `Function`  
  
2. <span data-ttu-id="39bae-122">In Klammern direkt nach `Function`, geben Sie die Parameter der Funktion.</span><span class="sxs-lookup"><span data-stu-id="39bae-122">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="39bae-123">Beachten Sie, dass Sie nicht nach Namen angeben `Function`.</span><span class="sxs-lookup"><span data-stu-id="39bae-123">Notice that you do not specify a name after `Function`.</span></span>  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. <span data-ttu-id="39bae-124">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="39bae-124">Press ENTER.</span></span> <span data-ttu-id="39bae-125">Die `End Function` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="39bae-125">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="39bae-126">Fügen Sie im Text der Funktion den folgenden Code zum Erstellen eines Ausdrucks und der Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-126">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="39bae-127">Verwenden Sie keine `As` -Klausel, um den Rückgabetyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-127">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="39bae-128">Sie rufen den Lambda-Ausdruck auf, indem Sie ein ganzzahliges Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-128">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="39bae-129">Um eine Unterroutine der mehrzeiligen Lambda-Ausdruck zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="39bae-129">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="39bae-130">In einer Situation, in ein Delegattyp verwendet werden kann, geben Sie das Schlüsselwort `Sub`, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="39bae-130">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     `Dim add1 =`   `Sub`  
  
2. <span data-ttu-id="39bae-131">In Klammern direkt nach `Sub`, geben Sie die Parameter der Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="39bae-131">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="39bae-132">Beachten Sie, dass Sie nicht nach Namen angeben `Sub`.</span><span class="sxs-lookup"><span data-stu-id="39bae-132">Notice that you do not specify a name after `Sub`.</span></span>  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. <span data-ttu-id="39bae-133">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="39bae-133">Press ENTER.</span></span> <span data-ttu-id="39bae-134">Die `End Sub` -Anweisung wird automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="39bae-134">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="39bae-135">Fügen Sie den folgenden Code ausgeführt wird, wenn die Unterroutine aufgerufen wird, innerhalb des Texts der Funktion.</span><span class="sxs-lookup"><span data-stu-id="39bae-135">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="39bae-136">Sie rufen den Lambda-Ausdruck auf, indem Sie ein Zeichenfolgenargument übergeben.</span><span class="sxs-lookup"><span data-stu-id="39bae-136">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="39bae-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39bae-137">Example</span></span>  
 <span data-ttu-id="39bae-138">Eine häufige Verwendung von Lambda-Ausdrücken ist eine Funktion definiert, die als Argument für einen Parameter übergeben werden kann, dessen Typ `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="39bae-138">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="39bae-139">Im folgenden Beispiel die <xref:System.Diagnostics.Process.GetProcesses%2A> Methode gibt ein Array von auf dem lokalen Computer ausgeführten Prozesse.</span><span class="sxs-lookup"><span data-stu-id="39bae-139">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="39bae-140">Die <xref:System.Linq.Enumerable.Where%2A> Methode aus der <xref:System.Linq.Enumerable> Klasse erfordert eine `Boolean` als Argument zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="39bae-140">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="39bae-141">Der Lambda-Ausdruck im Beispiel wird für diesen Zweck verwendet.</span><span class="sxs-lookup"><span data-stu-id="39bae-141">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="39bae-142">Es gibt `True` für jeden Prozess, der nur ein Thread besitzt und diese werden in ausgewählt `filteredList`.</span><span class="sxs-lookup"><span data-stu-id="39bae-142">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="39bae-143">Im vorherige Beispiel entspricht dem folgenden Code, der geschrieben wird, im [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Syntax:</span><span class="sxs-lookup"><span data-stu-id="39bae-143">The previous example is equivalent to the following code, which is written in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="39bae-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39bae-144">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="39bae-145">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39bae-145">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="39bae-146">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="39bae-146">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="39bae-147">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="39bae-147">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="39bae-148">Delegaten</span><span class="sxs-lookup"><span data-stu-id="39bae-148">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="39bae-149">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39bae-149">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="39bae-150">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="39bae-150">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="39bae-151">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39bae-151">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
