---
title: "Lambdaausdrücke (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69ac88d295420277e99058d0f80a5ae1c2ce2e39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="11744-102">Lambdaausdrücke (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11744-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="11744-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die verwendet werden kann, wo ein Delegat zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="11744-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="11744-104">Lambda-Ausdrücke können Funktionen oder Unterroutinen werden und einzeilige bzw. mehrzeilige werden können.</span><span class="sxs-lookup"><span data-stu-id="11744-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="11744-105">Sie können Werte aus dem aktuellen Bereich an einen Lambda-Ausdruck übergeben.</span><span class="sxs-lookup"><span data-stu-id="11744-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11744-106">Die `RemoveHandler` -Anweisung ist eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="11744-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="11744-107">Sie können keine Delegaten als Parameter für einen Lambda-Ausdruck im übergeben `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="11744-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="11744-108">Erstellen Sie Lambda-Ausdrücke mithilfe der `Function` oder `Sub` -Schlüsselwort, wie Sie eine standard-Funktion oder Unterroutine erstellen.</span><span class="sxs-lookup"><span data-stu-id="11744-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="11744-109">Lambda-Ausdrücke sind jedoch in einer Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="11744-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="11744-110">Im folgende Beispiel wird ein Lambda-Ausdruck, der inkrementiert Argument und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="11744-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="11744-111">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="11744-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]  
  
 <span data-ttu-id="11744-112">Im folgende Beispiel wird ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="11744-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="11744-113">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="11744-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]  
  
 <span data-ttu-id="11744-114">Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke ein Variablenname zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="11744-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="11744-115">Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="11744-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="11744-116">Sie können auch deklarieren und Aufrufen ein Lambda-Ausdrucks zur gleichen Zeit wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="11744-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]  
  
 <span data-ttu-id="11744-117">Ein Lambda-Ausdruck als Wert eines Funktionsaufrufs zurückgegeben werden kann (wie im Beispiel gezeigt die [Kontext](#context) weiter unten in diesem Thema), oder als Argument an einen Parameter übergeben, die akzeptiert einen Delegattyp, wie im folgenden dargestellt Beispiel:.</span><span class="sxs-lookup"><span data-stu-id="11744-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="11744-118">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="11744-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="11744-119">Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion oder Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="11744-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="11744-120">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="11744-120">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="11744-121">Ein Lambda-Ausdruck weist keine Namen auf.</span><span class="sxs-lookup"><span data-stu-id="11744-121">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="11744-122">Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="11744-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="11744-123">Einzeilige Lambda-Funktionen verwenden Sie keine `As` -Klausel, um den Rückgabetyp festzulegen.</span><span class="sxs-lookup"><span data-stu-id="11744-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="11744-124">Stattdessen wird der Typ aus dem Wert hergeleitet, der der Text des Lambda-Ausdrucks ergibt.</span><span class="sxs-lookup"><span data-stu-id="11744-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="11744-125">Wenn der Text des Lambda-Ausdrucks ist z. B. `cust.City = "London"`, der Rückgabetyp ist `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="11744-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="11744-126">In mehrzeiligen Lambdafunktionen können Sie entweder einen Rückgabetyp angeben, mit einer `As` -Klausel, oder lassen Sie die `As` Klausel so, dass der Rückgabetyp abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="11744-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="11744-127">Wenn die `As` -Klausel weggelassen wird, für eine mehrzeilige Lambda-Funktion, der Rückgabetyp abgeleitet wird, ist der bestimmende Typ von allen die `Return` Anweisungen in mehrzeiligen Lambda-Funktion.</span><span class="sxs-lookup"><span data-stu-id="11744-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="11744-128">Die *bestimmende Typ* ist ein eindeutiger Typ, der alle anderen Typen erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="11744-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="11744-129">Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, dem alle anderen Typen im Array eingegrenzt werden können.</span><span class="sxs-lookup"><span data-stu-id="11744-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="11744-130">Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="11744-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="11744-131">In diesem Fall, wenn `Option Strict` festgelegt ist, um `On`, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="11744-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="11744-132">Angenommen, die Ausdrücke bereitgestellt der `Return` -Anweisung enthalten die Werte des Typs `Integer`, `Long`, und `Double`, der sich ergebenden Array ist vom Typ `Double`.</span><span class="sxs-lookup"><span data-stu-id="11744-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="11744-133">Beide `Integer` und `Long` erweitert werden, um `Double` und nur `Double`.</span><span class="sxs-lookup"><span data-stu-id="11744-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="11744-134">Daher ist `Double` der bestimmende Typ.</span><span class="sxs-lookup"><span data-stu-id="11744-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="11744-135">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="11744-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="11744-136">Der Text einer einzeiligen-Funktion muss ein Ausdruck sein, der einen Wert zurückgibt, keine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="11744-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="11744-137">Es ist keine `Return` -Anweisung für einzeilige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="11744-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="11744-138">Von der einzeilige-Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="11744-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="11744-139">Der Text der einzeilige Unterroutine muss es sich um einzeilige Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="11744-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="11744-140">Einzeilige Funktionen und Unterroutinen enthalten kein `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="11744-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="11744-141">Sie können den Datentyp eines Parameters Lambda-Ausdruck angeben, mit dem `As` Schlüsselwort oder den Datentyp des Parameters abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="11744-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="11744-142">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="11744-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="11744-143">`Optional`und `Paramarray` Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11744-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="11744-144">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11744-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="11744-145">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="11744-145">Async Lambdas</span></span>  
 <span data-ttu-id="11744-146">Sie können problemlos erstellen, Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten die [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md) Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="11744-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="11744-147">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="11744-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```vb  
Public Class Form1  
  
    Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
        ' ExampleMethodAsync returns a Task.  
        Await ExampleMethodAsync()  
        TextBox1.Text = vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="11744-148">Sie können denselben Ereignishandler hinzufügen, indem Sie mit einem asynchronem Lambda-Ausdruck in eine [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="11744-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="11744-149">Um diesen Handler hinzuzufügen, fügen Sie einen `Async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.</span><span class="sxs-lookup"><span data-stu-id="11744-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```vb  
Public Class Form1  
  
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load  
        AddHandler Button1.Click,   
            Async Sub(sender1, e1)  
                ' ExampleMethodAsync returns a Task.  
                Await ExampleMethodAsync()  
                TextBox1.Text = vbCrLf & "Control returned to Button1_ Click."  
            End Sub  
    End Sub  
  
    Async Function ExampleMethodAsync() As Task  
        ' The following line simulates a task-returning asynchronous process.  
        Await Task.Delay(1000)  
    End Function  
  
End Class  
```  
  
 <span data-ttu-id="11744-150">Weitere Informationen zum Erstellen und Verwenden von Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="11744-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <a name="context"></a><span data-ttu-id="11744-151">Kontext</span><span class="sxs-lookup"><span data-stu-id="11744-151">Context</span></span>  
 <span data-ttu-id="11744-152">Ein Lambda-Ausdruck verwendet seinen Kontext mit dem Bereich, in dem sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="11744-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="11744-153">Er verfügt über die gleichen Zugriffsrechte wie der Code in der enthaltenden Bereich geschrieben.</span><span class="sxs-lookup"><span data-stu-id="11744-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="11744-154">Dies schließt den Zugriff auf Member-Variablen, Funktionen und Unterroutinen `Me`, Parameter und lokale Variablen in der enthaltenden Bereich befindet.</span><span class="sxs-lookup"><span data-stu-id="11744-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="11744-155">Zugriff auf lokale Variablen und Parameter in der enthaltenden Bereich kann die Lebensdauer des Bereichs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="11744-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="11744-156">Solange ein Delegat verweist auf einen Lambda-Ausdruck nicht in die Garbagecollection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="11744-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="11744-157">Im folgenden Beispiel Variable `target` lediglich auf `makeTheGame`, die Methode, in der der Lambda-Ausdruck `playTheGame` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="11744-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="11744-158">Beachten Sie, die den zurückgegebenen Lambda-Ausdruck zugewiesen, `takeAGuess` in `Main`, hat weiterhin Zugriff auf die lokale Variable `target`.</span><span class="sxs-lookup"><span data-stu-id="11744-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]  
  
 <span data-ttu-id="11744-159">Das folgende Beispiel zeigt die Vielzahl von Zugriffsrechten der geschachtelte Lambda-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="11744-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="11744-160">Wenn der zurückgegebene Lambda-Ausdruck ausgeführt wird, aus `Main` als `aDel`, greift er auf diese Elemente:</span><span class="sxs-lookup"><span data-stu-id="11744-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="11744-161">Ein Feld der Klasse in der sie definiert ist:`aField`</span><span class="sxs-lookup"><span data-stu-id="11744-161">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="11744-162">Eine Eigenschaft der Klasse in der sie definiert ist:`aProp`</span><span class="sxs-lookup"><span data-stu-id="11744-162">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="11744-163">Ein Parameter der Methode `functionWithNestedLambda`, in dem es definiert ist:`level1`</span><span class="sxs-lookup"><span data-stu-id="11744-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="11744-164">Eine lokale Variable vom `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="11744-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="11744-165">Ein Parameter des Lambda-Ausdrucks, in dem sie geschachtelt ist:`level2`</span><span class="sxs-lookup"><span data-stu-id="11744-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="11744-166">Konvertieren in einen Delegattyp</span><span class="sxs-lookup"><span data-stu-id="11744-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="11744-167">Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="11744-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="11744-168">Informationen zu den allgemeinen Anforderungen für die Kompatibilität finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="11744-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="11744-169">Das folgende Codebeispiel zeigt z. B. einen Lambda-Ausdruck, der implizit konvertiert `Func(Of Integer, Boolean)` oder einer übereinstimmenden Signatur des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="11744-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]  
  
 <span data-ttu-id="11744-170">Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit konvertiert `Sub(Of Double, String, Double)` oder einer übereinstimmenden Signatur des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="11744-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]  
  
 <span data-ttu-id="11744-171">Wenn Sie Delegaten Lambda-Ausdrücke zuweisen oder Prozeduren als Argumente übergeben, können Sie geben Sie den Parameternamen jedoch weglassen, deren Datentypen, lassen die Typen aus dem Delegaten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11744-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="11744-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="11744-172">Examples</span></span>  
  
-   <span data-ttu-id="11744-173">Das folgende Beispiel definiert einen Lambda-Ausdruck, der zurückgibt `True` , wenn das Argument NULL-Werte zulässt, einen Wert zugewiesen wurde und `False` Wenn der Wert `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="11744-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]  
  
-   <span data-ttu-id="11744-174">Das folgende Beispiel definiert einen Lambda-Ausdruck, der den Index des letzten Elements in einem Array zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="11744-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="11744-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11744-175">See Also</span></span>  
 [<span data-ttu-id="11744-176">Verfahren</span><span class="sxs-lookup"><span data-stu-id="11744-176">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="11744-177">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11744-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="11744-178">Delegaten</span><span class="sxs-lookup"><span data-stu-id="11744-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="11744-179">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11744-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="11744-180">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11744-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="11744-181">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="11744-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="11744-182">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11744-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="11744-183">Gewusst wie: Erstellen eines Lambda-Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="11744-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)  
 [<span data-ttu-id="11744-184">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="11744-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
