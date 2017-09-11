---
title: Funktionsausdruck (Visual Basic) | Microsoft-Dokumentation
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
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: c379ed1694f72243ccb8367d5b820803b4fcf190
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="785ca-102">Funktionsausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="785ca-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="785ca-103">Deklariert die Parameter und Code, die einen Lambda-Funktionsausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="785ca-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="785ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="785ca-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="785ca-105">Teile</span><span class="sxs-lookup"><span data-stu-id="785ca-105">Parts</span></span>  
  
|<span data-ttu-id="785ca-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="785ca-106">Term</span></span>|<span data-ttu-id="785ca-107">Definition</span><span class="sxs-lookup"><span data-stu-id="785ca-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="785ca-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="785ca-108">Optional.</span></span> <span data-ttu-id="785ca-109">Eine Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="785ca-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="785ca-110">Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="785ca-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="785ca-111">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="785ca-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="785ca-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="785ca-112">Required.</span></span> <span data-ttu-id="785ca-113">Ein einzelner Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="785ca-113">A single expression.</span></span> <span data-ttu-id="785ca-114">Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="785ca-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="785ca-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="785ca-115">Required.</span></span> <span data-ttu-id="785ca-116">Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="785ca-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="785ca-117">(Siehe [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des Rückgabewerts ist der Rückgabetyp der Funktion.</span><span class="sxs-lookup"><span data-stu-id="785ca-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="785ca-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="785ca-118">Remarks</span></span>  
 <span data-ttu-id="785ca-119">Ein *Lambda-Ausdruck* ist eine Funktion ohne Namen, die einen Wert berechnet und zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="785ca-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="785ca-120">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument für `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="785ca-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="785ca-121">Weitere Informationen zu Delegaten und der Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="785ca-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="785ca-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="785ca-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="785ca-123">Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion.</span><span class="sxs-lookup"><span data-stu-id="785ca-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="785ca-124">Die Unterschiede sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="785ca-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="785ca-125">Ein Lambda-Ausdruck keinen Namen.</span><span class="sxs-lookup"><span data-stu-id="785ca-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="785ca-126">Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="785ca-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="785ca-127">Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="785ca-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="785ca-128">Stattdessen wird der Typ von dem Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder den Rückgabewert eines mehrzeiligen Lambda-Ausdrucks abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="785ca-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="785ca-129">Wenn der Text eines einzeiligen Lambda-Ausdrucks ist z. B. `Where cust.City = "London"`, dessen Rückgabetyp `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="785ca-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="785ca-130">Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="785ca-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="785ca-131">Der Text kann aus einem Aufruf einer Funktionsprozedur, jedoch nicht aus einem Aufruf einer Sub-Prozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="785ca-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="785ca-132">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="785ca-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="785ca-133">Optional und Paramarray-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="785ca-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="785ca-134">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="785ca-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="785ca-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="785ca-135">Example</span></span>  
 <span data-ttu-id="785ca-136">Den folgenden Beispielen werden zwei Methoden zum Erstellen von einfachen Lambda-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="785ca-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="785ca-137">Die erste Anwendung verwendet eine `Dim` einen Namen für die Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="785ca-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="785ca-138">Um die Funktion aufrufen, senden Sie einen Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="785ca-138">To call the function, you send in a value for the parameter.</span></span>  
  
 <span data-ttu-id="785ca-139">[!code-vb[VbVbalrLambdas&#1;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="785ca-139">[!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span></span>  
  
 <span data-ttu-id="785ca-140">[!code-vb[VbVbalrLambdas&#2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="785ca-140">[!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="785ca-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="785ca-141">Example</span></span>  
 <span data-ttu-id="785ca-142">Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.</span><span class="sxs-lookup"><span data-stu-id="785ca-142">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 <span data-ttu-id="785ca-143">[!code-vb[VbVbalrLambdas&3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="785ca-143">[!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="785ca-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="785ca-144">Example</span></span>  
 <span data-ttu-id="785ca-145">Es folgt ein Beispiel eines Lambda-Ausdrucks, das Argument inkrementiert und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="785ca-145">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="785ca-146">Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="785ca-146">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="785ca-147">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="785ca-147">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="785ca-148">[!code-vb[VbVbalrLambdas&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="785ca-148">[!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="785ca-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="785ca-149">Example</span></span>  
 <span data-ttu-id="785ca-150">Lambda-Ausdrücke zugrunde liegen viele Abfrageoperatoren in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], und in methodenbasierten Abfragen explizit verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="785ca-150">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="785ca-151">Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] Abfrage, gefolgt von der Übersetzung der Abfrage in Methode Format.</span><span class="sxs-lookup"><span data-stu-id="785ca-151">The following example shows a typical [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="785ca-152">Weitere Informationen zu Abfragemethoden finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="785ca-152">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="785ca-153">Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="785ca-153">For more information about standard query operators, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="785ca-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="785ca-154">See Also</span></span>  
 <span data-ttu-id="785ca-155">[Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-155">[Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="785ca-156"> [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-156"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="785ca-157"> [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="785ca-158"> [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-158"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="785ca-159"> [Wertvergleiche](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-159"> [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="785ca-160"> [Boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-160"> [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span></span>  
<span data-ttu-id="785ca-161"> [Wenn Operator](../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="785ca-161"> [If Operator](../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="785ca-162"> [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="785ca-162"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

