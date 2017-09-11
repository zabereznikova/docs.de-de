---
title: "Lambda-Ausdrücke (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.LambdaFunction
dev_langs:
- VB
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
caps.latest.revision: 52
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
ms.openlocfilehash: e4624e5f20beeebf85656c893043030566200557
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="71245-102">Lambdaausdrücke (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71245-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="71245-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die verwendet werden kann, wo ein Delegat zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="71245-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="71245-104">Lambda-Ausdrücke können können Funktionen oder Unterroutinen sein und ein- oder mehrzeiligen.</span><span class="sxs-lookup"><span data-stu-id="71245-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="71245-105">Sie können Werte aus dem aktuellen Gültigkeitsbereich an einen Lambda-Ausdruck übergeben.</span><span class="sxs-lookup"><span data-stu-id="71245-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71245-106">Die `RemoveHandler` -Anweisung ist eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="71245-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="71245-107">Sie können keine Delegaten als Parameter für einen Lambda-Ausdruck in übergeben `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="71245-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="71245-108">Erstellen Sie Lambda-Ausdrücke mithilfe der `Function` oder `Sub` -Schlüsselwort, wie Sie eine standard-Funktion oder Unterroutine erstellen.</span><span class="sxs-lookup"><span data-stu-id="71245-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="71245-109">Lambda-Ausdrücke sind jedoch in einer Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="71245-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="71245-110">Im folgende Beispiel wird ein Lambda-Ausdruck ein, der Argument inkrementiert und gibt den Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="71245-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="71245-111">Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="71245-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 <span data-ttu-id="71245-112">[!code-vb[VbVbalrLambdas&14;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-112">[!code-vb[VbVbalrLambdas#14](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_1.vb)]</span></span>  
  
 <span data-ttu-id="71245-113">Im folgende Beispiel wird ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="71245-113">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="71245-114">Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="71245-114">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 <span data-ttu-id="71245-115">[!code-vb[VbVbalrLambdas&#15;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-115">[!code-vb[VbVbalrLambdas#15](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_2.vb)]</span></span>  
  
 <span data-ttu-id="71245-116">Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke ein Variablenname zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="71245-116">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="71245-117">Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="71245-117">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="71245-118">Sie können auch deklarieren und Aufrufen ein Lambda-Ausdrucks auf einmal, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71245-118">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 <span data-ttu-id="71245-119">[!code-vb[VbVbalrLambdas&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-119">[!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_3.vb)]</span></span>  
  
 <span data-ttu-id="71245-120">Ein Lambda-Ausdruck als Wert eines Funktionsaufrufs zurückgegeben werden kann (wie in dem Beispiel in der [Kontext](#context) weiter unten in diesem Thema), oder als Argument an einen Parameter übergeben, der einen Delegattyp akzeptiert wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71245-120">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 <span data-ttu-id="71245-121">[!code-vb[VbVbalrLambdas&#8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-121">[!code-vb[VbVbalrLambdas#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_4.vb)]</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="71245-122">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="71245-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="71245-123">Die Syntax eines Lambda-Ausdrucks ähnelt der einer standard-Funktion oder Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="71245-123">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="71245-124">Die Unterschiede sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="71245-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="71245-125">Ein Lambda-Ausdruck keinen Namen.</span><span class="sxs-lookup"><span data-stu-id="71245-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="71245-126">Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="71245-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="71245-127">Verwenden Sie einzeiligen Lambda-Funktionen kein `As` -Klausel, um den Rückgabetyp festzulegen.</span><span class="sxs-lookup"><span data-stu-id="71245-127">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="71245-128">Stattdessen wird der Typ von dem Wert abgeleitet, der der Text des Lambda-Ausdrucks ergibt.</span><span class="sxs-lookup"><span data-stu-id="71245-128">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="71245-129">Wenn der Text des Lambda-Ausdrucks ist z. B. `cust.City = "London"`, dessen Rückgabetyp `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="71245-129">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="71245-130">In mehrzeiligen Lambda-Funktionen können Sie entweder einen Rückgabetyp angeben, mit einer `As` -Klausel, oder lassen Sie die `As` Klausel so, dass der Rückgabetyp abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="71245-130">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="71245-131">Wenn die `As` -Klausel weggelassen wird, für den eine mehrzeilige Lambda-Funktion, der Rückgabetyp ist der bestimmende Typ von allen abgeleitet ist die `Return` Anweisungen in mehrzeiligen Lambda-Funktion.</span><span class="sxs-lookup"><span data-stu-id="71245-131">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="71245-132">Die *bestimmende Typ* ist ein eindeutiger Typ, der alle anderen Typen erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="71245-132">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="71245-133">Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, dem alle anderen Typen im Array eingegrenzt werden können.</span><span class="sxs-lookup"><span data-stu-id="71245-133">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="71245-134">Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="71245-134">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="71245-135">In diesem Fall, wenn `Option Strict` Wert `On`, tritt ein Compilerfehler auf.</span><span class="sxs-lookup"><span data-stu-id="71245-135">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="71245-136">Z. B. wenn die Ausdrücke an die `Return` -Anweisung enthalten die Werte des Typs `Integer`, `Long`, und `Double`, das resultierende Array ist vom Typ `Double`.</span><span class="sxs-lookup"><span data-stu-id="71245-136">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="71245-137">Beide `Integer` und `Long` werden zu `Double` und nur `Double`.</span><span class="sxs-lookup"><span data-stu-id="71245-137">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="71245-138">Daher ist `Double` der bestimmende Typ.</span><span class="sxs-lookup"><span data-stu-id="71245-138">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="71245-139">Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="71245-139">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
-   <span data-ttu-id="71245-140">Der Text einer einzeiligen Funktion muss ein Ausdruck sein, der einen Wert, der keine Anweisung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="71245-140">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="71245-141">Es gibt keine `Return` -Anweisung für einzeilige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="71245-141">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="71245-142">Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="71245-142">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
-   <span data-ttu-id="71245-143">Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="71245-143">The body of a single-line subroutine must be single-line statement.</span></span>  
  
-   <span data-ttu-id="71245-144">Einzeilige Funktionen und Unterroutinen enthalten kein `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="71245-144">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
-   <span data-ttu-id="71245-145">Sie können den Datentyp eines Lambda-Ausdruck-Parameters angeben, mit dem `As` Schlüsselwort oder der Datentyp des Parameters abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="71245-145">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="71245-146">Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="71245-146">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="71245-147">`Optional`und `Paramarray` Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="71245-147">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="71245-148">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="71245-148">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="71245-149">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="71245-149">Async Lambdas</span></span>  
 <span data-ttu-id="71245-150">Sie können problemlos erstellen, Lambda-Ausdrücke und Anweisungen, die asynchrone Verarbeitung enthalten die [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md) Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="71245-150">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="71245-151">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="71245-151">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="71245-152">Sie können denselben Ereignishandler hinzufügen, indem Sie ein asynchrones Lambda in verwenden ein [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span><span class="sxs-lookup"><span data-stu-id="71245-152">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="71245-153">Um diesen Handler hinzuzufügen, fügen Sie einen `Async`-Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.</span><span class="sxs-lookup"><span data-stu-id="71245-153">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="71245-154">Weitere Informationen zum Erstellen und Verwenden von Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="71245-154">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
##  <span data-ttu-id="71245-155"><a name="context"></a>Kontext</span><span class="sxs-lookup"><span data-stu-id="71245-155"><a name="context"></a> Context</span></span>  
 <span data-ttu-id="71245-156">Ein Lambda-Ausdruck teilt der Kontext mit dem Bereich, in dem sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="71245-156">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="71245-157">Er verfügt über die gleichen Zugriffsrechte wie der Code im enthaltenden Bereich geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71245-157">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="71245-158">Dies schließt Zugriff auf Membervariablen, Funktionen und Subroutinen, `Me`, Parameter und lokale Variablen im enthaltenden Bereich.</span><span class="sxs-lookup"><span data-stu-id="71245-158">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="71245-159">Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann die Lebensdauer dieses Bereichs überdauern.</span><span class="sxs-lookup"><span data-stu-id="71245-159">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="71245-160">Solange ein Delegat, der auf einen Lambda-Ausdruck verweist nicht auf die Garbagecollection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="71245-160">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="71245-161">Im folgenden Beispiel Variablen `target` lediglich auf `makeTheGame`, die Methode, in der der Lambda-Ausdruck `playTheGame` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="71245-161">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="71245-162">Beachten Sie, die den zurückgegebenen Lambda-Ausdruck zugewiesen, `takeAGuess` in `Main`, immer noch Zugriff auf die lokale Variable `target`.</span><span class="sxs-lookup"><span data-stu-id="71245-162">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 <span data-ttu-id="71245-163">[!code-vb[VbVbalrLambdas&#12;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-163">[!code-vb[VbVbalrLambdas#12](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_5.vb)]</span></span>  
  
 <span data-ttu-id="71245-164">Das folgende Beispiel zeigt eine Vielzahl von Zugriffsrechte des geschachtelten Lambda-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="71245-164">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="71245-165">Wenn der zurückgegebene Lambda-Ausdruck ausgeführt wird, von `Main` als `aDel`, greift er auf diese Elemente:</span><span class="sxs-lookup"><span data-stu-id="71245-165">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
-   <span data-ttu-id="71245-166">Ein Feld der Klasse, in der er definiert wird:`aField`</span><span class="sxs-lookup"><span data-stu-id="71245-166">A field of the class in which it is defined: `aField`</span></span>  
  
-   <span data-ttu-id="71245-167">Eine Eigenschaft der Klasse, in der er definiert wird:`aProp`</span><span class="sxs-lookup"><span data-stu-id="71245-167">A property of the class in which it is defined: `aProp`</span></span>  
  
-   <span data-ttu-id="71245-168">Ein Parameter der Methode `functionWithNestedLambda`, in der er definiert wird:`level1`</span><span class="sxs-lookup"><span data-stu-id="71245-168">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
-   <span data-ttu-id="71245-169">Eine lokale Variable des `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="71245-169">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
-   <span data-ttu-id="71245-170">Ein Parameter des Lambda-Ausdrucks in der er geschachtelt wird:`level2`</span><span class="sxs-lookup"><span data-stu-id="71245-170">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 <span data-ttu-id="71245-171">[!code-vb[VbVbalrLambdas&#9;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-171">[!code-vb[VbVbalrLambdas#9](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_6.vb)]</span></span>  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="71245-172">Konvertieren in einen Delegattyp</span><span class="sxs-lookup"><span data-stu-id="71245-172">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="71245-173">Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="71245-173">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="71245-174">Informationen über die allgemeinen Kriterien zur Kompatibilität finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="71245-174">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="71245-175">Das folgende Codebeispiel zeigt z. B. einen Lambda-Ausdruck, der implizit in konvertiert `Func(Of Integer, Boolean)` oder eine entsprechende Delegatsignatur.</span><span class="sxs-lookup"><span data-stu-id="71245-175">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="71245-176">[!code-vb[VbVbalrLambdas Nr.&16;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-176">[!code-vb[VbVbalrLambdas#16](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_7.vb)]</span></span>  
  
 <span data-ttu-id="71245-177">Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in konvertiert `Sub(Of Double, String, Double)` oder eine entsprechende Delegatsignatur.</span><span class="sxs-lookup"><span data-stu-id="71245-177">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 <span data-ttu-id="71245-178">[!code-vb[VbVbalrLambdas&23;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-178">[!code-vb[VbVbalrLambdas#23](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_8.vb)]</span></span>  
  
 <span data-ttu-id="71245-179">Wenn Sie Lambda-Ausdrücke Delegaten zugewiesen oder als Argumente an Prozeduren übergeben, können Sie die Parameternamen jedoch weglassen, deren Datentypen, die Typen aus dem Delegaten ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="71245-179">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="71245-180">Beispiele</span><span class="sxs-lookup"><span data-stu-id="71245-180">Examples</span></span>  
  
-   <span data-ttu-id="71245-181">Im folgenden Beispiel wird einen Lambda-Ausdruck, der zurückgibt `True` verfügt das auf NULL festlegbare Argument einen Wert zugewiesen und `False` ist der Wert `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="71245-181">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     <span data-ttu-id="71245-182">[!code-vb[VbVbalrLambdas&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-182">[!code-vb[VbVbalrLambdas#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_9.vb)]</span></span>  
  
-   <span data-ttu-id="71245-183">Das folgende Beispiel definiert einen Lambda-Ausdruck, der den Index des letzten Elements in einem Array zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="71245-183">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     <span data-ttu-id="71245-184">[!code-vb[VbVbalrLambdas&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="71245-184">[!code-vb[VbVbalrLambdas#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/lambda-expressions_10.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71245-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71245-185">See Also</span></span>  
 <span data-ttu-id="71245-186">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="71245-186">[Procedures](./index.md) </span></span>  
<span data-ttu-id="71245-187"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="71245-187"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="71245-188"> [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="71245-188"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="71245-189"> [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71245-189"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="71245-190"> [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71245-190"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="71245-191"> [Auf NULL festlegbare Werttypen](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span><span class="sxs-lookup"><span data-stu-id="71245-191"> [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) </span></span>  
<span data-ttu-id="71245-192"> [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="71245-192"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="71245-193"> [Gewusst wie: Erstellen eines Lambda-Ausdrucks](./how-to-create-a-lambda-expression.md) </span><span class="sxs-lookup"><span data-stu-id="71245-193"> [How to: Create a Lambda Expression](./how-to-create-a-lambda-expression.md) </span></span>  
<span data-ttu-id="71245-194"> [Gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="71245-194"> [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

