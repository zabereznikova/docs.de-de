---
title: Funktionsausdruck (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e1d9d1223b340b2172c12bd8c2f364e314e764b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="bb975-102">Funktionsausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb975-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="bb975-103">Deklariert die Parameter und den Code, der einen Lambda-Ausdruck von Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="bb975-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb975-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb975-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="bb975-105">Teile</span><span class="sxs-lookup"><span data-stu-id="bb975-105">Parts</span></span>  
  
|<span data-ttu-id="bb975-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="bb975-106">Term</span></span>|<span data-ttu-id="bb975-107">Definition</span><span class="sxs-lookup"><span data-stu-id="bb975-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="bb975-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bb975-108">Optional.</span></span> <span data-ttu-id="bb975-109">Eine Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="bb975-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="bb975-110">Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="bb975-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="bb975-111">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="bb975-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bb975-112">Required.</span></span> <span data-ttu-id="bb975-113">Ein einzelner Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="bb975-113">A single expression.</span></span> <span data-ttu-id="bb975-114">Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb975-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="bb975-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bb975-115">Required.</span></span> <span data-ttu-id="bb975-116">Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bb975-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="bb975-117">(Siehe [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb975-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb975-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb975-118">Remarks</span></span>  
 <span data-ttu-id="bb975-119">Ein *Lambda-Ausdruck* ist eine Funktion ohne Namen, die einen Wert berechnet und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bb975-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="bb975-120">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument für `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="bb975-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="bb975-121">Weitere Informationen über Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="bb975-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="bb975-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="bb975-123">Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb975-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="bb975-124">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="bb975-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="bb975-125">Ein Lambda-Ausdruck weist keine Namen auf.</span><span class="sxs-lookup"><span data-stu-id="bb975-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="bb975-126">Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="bb975-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="bb975-127">Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="bb975-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="bb975-128">Stattdessen wird der Typ nicht abgeleitet aus dem Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder den Rückgabewert eines mehrzeiligen Lambda-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="bb975-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="bb975-129">Wenn der Text eines Lambdaausdrucks einzeilige ist z. B. `Where cust.City = "London"`, der Rückgabetyp ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="bb975-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="bb975-130">Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="bb975-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="bb975-131">Der Text kann einen Aufruf an eine Funktionsprozedur, aber nicht auf einen Aufruf an eine Subprozedur sein.</span><span class="sxs-lookup"><span data-stu-id="bb975-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="bb975-132">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb975-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="bb975-133">Optional und Paramarray-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb975-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="bb975-134">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="bb975-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb975-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb975-135">Example</span></span>  
 <span data-ttu-id="bb975-136">Den folgenden Beispielen werden zwei Methoden zum einfachen Lambda-Ausdrücke zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bb975-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="bb975-137">Im ersten Beispiel wird eine `Dim` , einen Namen für die Funktion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bb975-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="bb975-138">Um die Funktion aufzurufen, senden Sie einen Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="bb975-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="bb975-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb975-139">Example</span></span>  
 <span data-ttu-id="bb975-140">Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="bb975-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="bb975-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb975-141">Example</span></span>  
 <span data-ttu-id="bb975-142">Es folgt ein Beispiel eines Lambda-Ausdrucks, das Argument inkrementiert und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="bb975-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="bb975-143">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb975-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="bb975-144">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="bb975-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb975-145">Example</span></span>  
 <span data-ttu-id="bb975-146">Lambda-Ausdrücke zugrunde liegen, viele der Standardabfrageoperatoren in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], explizit in methodenbasierten Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bb975-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="bb975-147">Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage, gefolgt von der Übersetzung der Abfrage in das Format der Methode.</span><span class="sxs-lookup"><span data-stu-id="bb975-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="bb975-148">Weitere Informationen zu Abfragemethoden, finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="bb975-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="bb975-149">Weitere Informationen zu den Standardabfrageoperatoren, finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="bb975-149">For more information about standard query operators, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb975-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb975-150">See Also</span></span>  
 [<span data-ttu-id="bb975-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bb975-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="bb975-152">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="bb975-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="bb975-153">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="bb975-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="bb975-154">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="bb975-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="bb975-155">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="bb975-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="bb975-156">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="bb975-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="bb975-157">If-Operator</span><span class="sxs-lookup"><span data-stu-id="bb975-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="bb975-158">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="bb975-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
