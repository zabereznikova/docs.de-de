---
title: Funktionsausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: cfdd17f6f4ee6c4ddb3fa73ab3ec9c5ce46a162f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702997"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="97e2a-102">Funktionsausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97e2a-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="97e2a-103">Deklariert die Parameter und den Code, der einen Lambda-Ausdruck von Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="97e2a-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97e2a-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="97e2a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="97e2a-105">Parts</span></span>  
  
|<span data-ttu-id="97e2a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="97e2a-106">Term</span></span>|<span data-ttu-id="97e2a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="97e2a-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="97e2a-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="97e2a-108">Optional.</span></span> <span data-ttu-id="97e2a-109">Eine Liste von Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="97e2a-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="97e2a-110">Die Klammern müssen vorhanden sein, selbst wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="97e2a-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="97e2a-111">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="97e2a-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="97e2a-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97e2a-112">Required.</span></span> <span data-ttu-id="97e2a-113">Ein einzelner Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="97e2a-113">A single expression.</span></span> <span data-ttu-id="97e2a-114">Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="97e2a-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="97e2a-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="97e2a-115">Required.</span></span> <span data-ttu-id="97e2a-116">Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="97e2a-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="97e2a-117">(Finden Sie unter [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="97e2a-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97e2a-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97e2a-118">Remarks</span></span>  
 <span data-ttu-id="97e2a-119">Ein *Lambda-Ausdruck* ist eine Funktion ohne einen Namen, die berechnet, und gibt einen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97e2a-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="97e2a-120">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument an `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="97e2a-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="97e2a-121">Weitere Informationen zu Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="97e2a-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="97e2a-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="97e2a-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="97e2a-123">Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion.</span><span class="sxs-lookup"><span data-stu-id="97e2a-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="97e2a-124">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="97e2a-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="97e2a-125">Ein Lambda-Ausdruck ist nicht auf einen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="97e2a-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="97e2a-126">Lambda-Ausdrücke sind keine Modifizierer, z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="97e2a-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="97e2a-127">Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="97e2a-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="97e2a-128">Stattdessen wird der Typ der Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder der Rückgabewert eines mehrzeiligen Lambda-Ausdrucks abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="97e2a-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="97e2a-129">Wenn der Text eines einzeiligen Lambda-Ausdrucks ist z. B. `Where cust.City = "London"`, dessen Rückgabetyp `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="97e2a-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="97e2a-130">Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um einen Ausdruck, der keine Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="97e2a-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="97e2a-131">Der Text kann aus einem Aufruf einer Funktionsprozedur, aber nicht aus einem Aufruf an eine Subprozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="97e2a-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="97e2a-132">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen per Rückschluss abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="97e2a-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="97e2a-133">Optional "und" Paramarray-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="97e2a-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="97e2a-134">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="97e2a-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97e2a-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97e2a-135">Example</span></span>  
 <span data-ttu-id="97e2a-136">Die folgenden Beispiele zeigen zwei Möglichkeiten zum Erstellen von einfachen Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="97e2a-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="97e2a-137">Im ersten Beispiel wird eine `Dim` einen Namen für die Funktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="97e2a-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="97e2a-138">Um die Funktion aufzurufen, senden Sie einen Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="97e2a-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="97e2a-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97e2a-139">Example</span></span>  
 <span data-ttu-id="97e2a-140">Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="97e2a-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="97e2a-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97e2a-141">Example</span></span>  
 <span data-ttu-id="97e2a-142">Es folgt ein Beispiel für einen Lambda-Ausdruck, der inkrementiert des Arguments und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="97e2a-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="97e2a-143">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="97e2a-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="97e2a-144">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="97e2a-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="97e2a-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97e2a-145">Example</span></span>  
 <span data-ttu-id="97e2a-146">Lambda-Ausdrücke zugrunde liegen viele Abfrageoperatoren in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], explizit in methodenbasierten Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="97e2a-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="97e2a-147">Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage, gefolgt von der Verschiebung der Abfrage in das Format der Methode.</span><span class="sxs-lookup"><span data-stu-id="97e2a-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="97e2a-148">Weitere Informationen zu Abfragemethoden finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="97e2a-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="97e2a-149">Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="97e2a-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97e2a-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97e2a-150">See Also</span></span>  
 [<span data-ttu-id="97e2a-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="97e2a-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="97e2a-152">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="97e2a-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="97e2a-153">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="97e2a-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="97e2a-154">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="97e2a-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="97e2a-155">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="97e2a-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="97e2a-156">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="97e2a-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="97e2a-157">If-Operator</span><span class="sxs-lookup"><span data-stu-id="97e2a-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="97e2a-158">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="97e2a-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
