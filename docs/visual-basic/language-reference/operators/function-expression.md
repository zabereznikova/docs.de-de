---
title: Function-Ausdruck
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 719969be23a6d94f22a1d86cb4ad3f37e4c3b254
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873421"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="7d264-102">Funktionsausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d264-102">Function Expression (Visual Basic)</span></span>

<span data-ttu-id="7d264-103">Deklariert die Parameter und den Code, die einen Funktions-Lambda-Ausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="7d264-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d264-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d264-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="7d264-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7d264-105">Parts</span></span>  
  
|<span data-ttu-id="7d264-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="7d264-106">Term</span></span>|<span data-ttu-id="7d264-107">Definition</span><span class="sxs-lookup"><span data-stu-id="7d264-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="7d264-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7d264-108">Optional.</span></span> <span data-ttu-id="7d264-109">Eine Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="7d264-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="7d264-110">Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="7d264-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="7d264-111">Siehe [Parameter Liste](../statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="7d264-111">See [Parameter List](../statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="7d264-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d264-112">Required.</span></span> <span data-ttu-id="7d264-113">Ein einzelner Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="7d264-113">A single expression.</span></span> <span data-ttu-id="7d264-114">Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="7d264-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="7d264-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7d264-115">Required.</span></span> <span data-ttu-id="7d264-116">Eine Liste von-Anweisungen, die mithilfe der-Anweisung einen Wert zurückgibt `Return` .</span><span class="sxs-lookup"><span data-stu-id="7d264-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="7d264-117">(Siehe [Return-Anweisung](../statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="7d264-117">(See [Return Statement](../statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d264-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7d264-118">Remarks</span></span>  

 <span data-ttu-id="7d264-119">Ein *Lambda-Ausdruck* ist eine Funktion ohne einen Namen, der einen Wert berechnet und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7d264-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="7d264-120">Sie können einen Lambda-Ausdruck überall dort verwenden, wo Sie einen Delegattyp verwenden können, außer als Argument für `RemoveHandler` .</span><span class="sxs-lookup"><span data-stu-id="7d264-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="7d264-121">Weitere Informationen zu Delegaten und zur Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [delegatanweisung](../statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="7d264-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="7d264-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="7d264-122">Lambda Expression Syntax</span></span>  

 <span data-ttu-id="7d264-123">Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion.</span><span class="sxs-lookup"><span data-stu-id="7d264-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="7d264-124">Es gibt die folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="7d264-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="7d264-125">Ein Lambda-Ausdruck weist keinen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="7d264-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="7d264-126">Lambda Ausdrücke können keine Modifizierer aufweisen, wie z `Overloads` `Overrides` . b. oder.</span><span class="sxs-lookup"><span data-stu-id="7d264-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="7d264-127">Lambda-Ausdrücke verwenden keine- `As` Klausel, um den Rückgabetyp der Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="7d264-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="7d264-128">Stattdessen wird der-Typ von dem Wert abgeleitet, den der Text eines einzeiligen Lambda Ausdrucks ergibt, oder der Rückgabewert eines mehrzeiligen Lambda Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="7d264-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="7d264-129">Wenn der Text eines einzeiligen Lambda-Ausdrucks beispielsweise ist `Where cust.City = "London"` , ist der Rückgabetyp `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="7d264-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="7d264-130">Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine-Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="7d264-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="7d264-131">Der Text kann aus einem aufzurufenden Funktions Vorgang bestehen, jedoch nicht mit einem-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="7d264-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="7d264-132">Entweder müssen alle Parameter über bestimmte Datentypen verfügen, oder alle müssen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7d264-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="7d264-133">Optionale Parameter und ParamArray-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7d264-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="7d264-134">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7d264-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d264-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d264-135">Example</span></span>  

 <span data-ttu-id="7d264-136">In den folgenden Beispielen werden zwei Möglichkeiten zum Erstellen einfacher Lambda-Ausdrücke veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d264-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="7d264-137">Der erste verwendet einen `Dim` , um einen Namen für die Funktion bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d264-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="7d264-138">Zum Aufrufen der-Funktion senden Sie einen Wert für den-Parameter.</span><span class="sxs-lookup"><span data-stu-id="7d264-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="7d264-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d264-139">Example</span></span>  

 <span data-ttu-id="7d264-140">Alternativ dazu können Sie die Funktion gleichzeitig deklarieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="7d264-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="7d264-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d264-141">Example</span></span>  

 <span data-ttu-id="7d264-142">Im folgenden finden Sie ein Beispiel für einen Lambda-Ausdruck, der sein Argument erhöht und den Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7d264-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="7d264-143">Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="7d264-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="7d264-144">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7d264-144">For more examples, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="7d264-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d264-145">Example</span></span>  

 <span data-ttu-id="7d264-146">Lambda-Ausdrücke unterliegen vielen der Abfrage Operatoren in LINQ (Language-Integrated Query) und können in Methoden basierten Abfragen explizit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7d264-146">Lambda expressions underlie many of the query operators in Language-Integrated Query (LINQ), and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="7d264-147">Das folgende Beispiel zeigt eine typische LINQ-Abfrage, gefolgt von der Übersetzung der Abfrage in das Methoden Format.</span><span class="sxs-lookup"><span data-stu-id="7d264-147">The following example shows a typical LINQ query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="7d264-148">Weitere Informationen zu Abfrage Methoden finden Sie unter [Abfragen](../queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d264-148">For more information about query methods, see [Queries](../queries/index.md).</span></span> <span data-ttu-id="7d264-149">Weitere Informationen zu Standard Abfrage Operatoren finden Sie unter [Übersicht über Standard Abfrage Operatoren](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d264-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d264-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d264-150">See also</span></span>

- [<span data-ttu-id="7d264-151">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7d264-151">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="7d264-152">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7d264-152">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="7d264-153">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7d264-153">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="7d264-154">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7d264-154">Statements</span></span>](../../programming-guide/language-features/statements.md)
- [<span data-ttu-id="7d264-155">Wertvergleiche</span><span class="sxs-lookup"><span data-stu-id="7d264-155">Value Comparisons</span></span>](../../programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="7d264-156">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7d264-156">Boolean Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="7d264-157">If-Operator</span><span class="sxs-lookup"><span data-stu-id="7d264-157">If Operator</span></span>](if-operator.md)
- [<span data-ttu-id="7d264-158">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7d264-158">Relaxed Delegate Conversion</span></span>](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
