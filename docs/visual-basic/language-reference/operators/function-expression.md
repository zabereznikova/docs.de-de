---
title: Funktionsausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 4bef609289cdbb192116469bac4fca66ee10fd09
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662522"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="ad536-102">Funktionsausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad536-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="ad536-103">Deklariert die Parameter und den Code, der einen Lambda-Ausdruck von Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="ad536-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad536-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad536-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="ad536-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ad536-105">Parts</span></span>  
  
|<span data-ttu-id="ad536-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="ad536-106">Term</span></span>|<span data-ttu-id="ad536-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ad536-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="ad536-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ad536-108">Optional.</span></span> <span data-ttu-id="ad536-109">Eine Liste von Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="ad536-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="ad536-110">Die Klammern müssen vorhanden sein, selbst wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="ad536-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="ad536-111">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="ad536-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="ad536-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad536-112">Required.</span></span> <span data-ttu-id="ad536-113">Ein einzelner Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="ad536-113">A single expression.</span></span> <span data-ttu-id="ad536-114">Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="ad536-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="ad536-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad536-115">Required.</span></span> <span data-ttu-id="ad536-116">Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ad536-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="ad536-117">(Finden Sie unter [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="ad536-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad536-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad536-118">Remarks</span></span>  
 <span data-ttu-id="ad536-119">Ein *Lambda-Ausdruck* ist eine Funktion ohne einen Namen, die berechnet, und gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="ad536-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="ad536-120">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument an `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="ad536-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="ad536-121">Weitere Informationen zu Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="ad536-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="ad536-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="ad536-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="ad536-123">Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion.</span><span class="sxs-lookup"><span data-stu-id="ad536-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="ad536-124">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ad536-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="ad536-125">Ein Lambda-Ausdruck ist nicht auf einen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="ad536-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="ad536-126">Lambda-Ausdrücke sind keine Modifizierer, z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="ad536-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="ad536-127">Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="ad536-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="ad536-128">Stattdessen wird der Typ der Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder der Rückgabewert eines mehrzeiligen Lambda-Ausdrucks abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ad536-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="ad536-129">Wenn der Text eines einzeiligen Lambda-Ausdrucks ist z. B. `Where cust.City = "London"`, dessen Rückgabetyp `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="ad536-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="ad536-130">Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um einen Ausdruck, der keine Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="ad536-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="ad536-131">Der Text kann aus einem Aufruf einer Funktionsprozedur, aber nicht aus einem Aufruf an eine Subprozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="ad536-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="ad536-132">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen per Rückschluss abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ad536-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="ad536-133">Optional "und" Paramarray-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ad536-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="ad536-134">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ad536-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad536-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad536-135">Example</span></span>  
 <span data-ttu-id="ad536-136">Die folgenden Beispiele zeigen zwei Möglichkeiten zum Erstellen von einfachen Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="ad536-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="ad536-137">Im ersten Beispiel wird eine `Dim` einen Namen für die Funktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ad536-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="ad536-138">Um die Funktion aufzurufen, senden Sie einen Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="ad536-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="ad536-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad536-139">Example</span></span>  
 <span data-ttu-id="ad536-140">Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="ad536-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="ad536-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad536-141">Example</span></span>  
 <span data-ttu-id="ad536-142">Es folgt ein Beispiel für einen Lambda-Ausdruck, der inkrementiert des Arguments und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="ad536-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="ad536-143">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="ad536-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="ad536-144">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ad536-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="ad536-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad536-145">Example</span></span>  
 <span data-ttu-id="ad536-146">Lambda-Ausdrücke zugrunde liegen viele Abfrageoperatoren in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], explizit in methodenbasierten Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ad536-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="ad536-147">Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage, gefolgt von der Verschiebung der Abfrage in das Format der Methode.</span><span class="sxs-lookup"><span data-stu-id="ad536-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="ad536-148">Weitere Informationen zu Abfragemethoden finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="ad536-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="ad536-149">Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ad536-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad536-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad536-150">See also</span></span>

- [<span data-ttu-id="ad536-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ad536-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="ad536-152">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ad536-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="ad536-153">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ad536-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="ad536-154">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="ad536-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="ad536-155">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="ad536-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="ad536-156">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ad536-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="ad536-157">If-Operator</span><span class="sxs-lookup"><span data-stu-id="ad536-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="ad536-158">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="ad536-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
