---
title: Lambdaausdrücke (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.LambdaFunction
helpviewer_keywords:
- functions [Visual Basic], lambda expressions
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
- inline functions [Visual Basic]
ms.assetid: 137064b0-3928-4bfa-ba71-c3f9cbd951e2
ms.openlocfilehash: e688beac18e782367bf39ddec8339df2b2735225
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928905"
---
# <a name="lambda-expressions-visual-basic"></a><span data-ttu-id="e8ee5-102">Lambdaausdrücke (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8ee5-102">Lambda Expressions (Visual Basic)</span></span>
<span data-ttu-id="e8ee5-103">Ein *Lambda-Ausdruck* ist eine Funktion oder Unterroutine ohne Namen, die überall dort verwendet werden kann, wo ein Delegat gültig ist.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-103">A *lambda expression* is a function or subroutine without a name that can be used wherever a delegate is valid.</span></span> <span data-ttu-id="e8ee5-104">Lambda Ausdrücke können Funktionen oder Unterroutinen sein und können einzeilige oder mehrzeilige Zeilen sein.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-104">Lambda expressions can be functions or subroutines and can be single-line or multi-line.</span></span> <span data-ttu-id="e8ee5-105">Sie können Werte aus dem aktuellen Gültigkeitsbereich an einen Lambda-Ausdruck übergeben.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-105">You can pass values from the current scope to a lambda expression.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8ee5-106">Die `RemoveHandler` -Anweisung ist eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-106">The `RemoveHandler` statement is an exception.</span></span> <span data-ttu-id="e8ee5-107">Sie können einen Lambda-Ausdruck in nicht für den Delegatparameter von `RemoveHandler`übergeben.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-107">You cannot pass a lambda expression in for the delegate parameter of `RemoveHandler`.</span></span>  
  
 <span data-ttu-id="e8ee5-108">Sie können Lambda Ausdrücke erstellen, indem `Function` Sie `Sub` das-Schlüsselwort oder das-Schlüsselwort verwenden, wie Sie eine Standardfunktion oder Unterroutine erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-108">You create lambda expressions by using the `Function` or `Sub` keyword, just as you create a standard function or subroutine.</span></span> <span data-ttu-id="e8ee5-109">Allerdings sind Lambda-Ausdrücke in einer-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-109">However, lambda expressions are included in a statement.</span></span>  
  
 <span data-ttu-id="e8ee5-110">Das folgende Beispiel zeigt einen Lambda-Ausdruck, der sein-Argument erhöht und den-Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-110">The following example is a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="e8ee5-111">Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-111">The example shows both the single-line and multi-line lambda expression syntax for a function.</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
 <span data-ttu-id="e8ee5-112">Das folgende Beispiel ist ein Lambda-Ausdruck, der einen Wert in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-112">The following example is a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="e8ee5-113">Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-113">The example shows both the single-line and multi-line lambda expression syntax for a subroutine.</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
 <span data-ttu-id="e8ee5-114">Beachten Sie, dass in den vorherigen Beispielen die Lambda-Ausdrücke einem Variablennamen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-114">Notice that in the previous examples the lambda expressions are assigned to a variable name.</span></span> <span data-ttu-id="e8ee5-115">Wenn Sie auf die Variable verweisen, rufen Sie den Lambda-Ausdruck auf.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-115">Whenever you refer to the variable, you invoke the lambda expression.</span></span> <span data-ttu-id="e8ee5-116">Sie können einen Lambda-Ausdruck auch gleichzeitig deklarieren und aufrufen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-116">You can also declare and invoke a lambda expression at the same time, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
 <span data-ttu-id="e8ee5-117">Ein Lambda-Ausdruck kann als Wert eines Funktions Aufrufes zurückgegeben werden (wie im Beispiel im [Kontext](#context) Abschnitt weiter unten in diesem Thema gezeigt) oder als Argument an einen Parameter übergeben, der einen Delegattyp annimmt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-117">A lambda expression can be returned as the value of a function call (as is shown in the example in the [Context](#context) section later in this topic), or passed in as an argument to a parameter that takes a delegate type, as shown in the following example.</span></span>  
  
 [!code-vb[VbVbalrLambdas#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class2.vb#8)]  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="e8ee5-118">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="e8ee5-118">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="e8ee5-119">Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion oder-Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-119">The syntax of a lambda expression resembles that of a standard function or subroutine.</span></span> <span data-ttu-id="e8ee5-120">Die Unterschiede lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e8ee5-120">The differences are as follows:</span></span>  
  
- <span data-ttu-id="e8ee5-121">Ein Lambda-Ausdruck weist keinen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-121">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="e8ee5-122">Lambda Ausdrücke können keine Modifizierer aufweisen, `Overloads` wie `Overrides`z. b. oder.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-122">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="e8ee5-123">Einzeilige Lambda-Funktionen verwenden `As` keine-Klausel, um den Rückgabetyp festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-123">Single-line lambda functions do not use an `As` clause to designate the return type.</span></span> <span data-ttu-id="e8ee5-124">Stattdessen wird der-Typ von dem Wert abgeleitet, zu dem der Text des Lambda-Ausdrucks ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-124">Instead, the type is inferred from the value that the body of the lambda expression evaluates to.</span></span> <span data-ttu-id="e8ee5-125">Wenn der Text des Lambda-Ausdrucks beispielsweise ist `cust.City = "London"`, ist `Boolean`der Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-125">For example, if the body of the lambda expression is `cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="e8ee5-126">In mehrzeiligen Lambda-Funktionen können Sie entweder mithilfe einer `As` -Klausel einen Rückgabetyp angeben oder die `As` -Klausel weglassen, damit der Rückgabetyp abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-126">In multi-line lambda functions, you can either specify a return type by using an `As` clause, or omit the `As` clause so that the return type is inferred.</span></span> <span data-ttu-id="e8ee5-127">Wenn die `As` -Klausel für eine mehrzeilige Lambda-Funktion weggelassen wird, wird der Rückgabetyp als dominanter Typ aus `Return` allen Anweisungen in der mehrzeiligen Lambda-Funktion abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-127">When the `As` clause is omitted for a multi-line lambda function, the return type is inferred to be the dominant type from all the `Return` statements in the multi-line lambda function.</span></span> <span data-ttu-id="e8ee5-128">Der *vorherrschende Typ* ist ein eindeutiger Typ, auf den alle anderen Typen erweitert werden können.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-128">The *dominant type* is a unique type that all other types can widen to.</span></span> <span data-ttu-id="e8ee5-129">Wenn dieser eindeutige Typ nicht bestimmt werden kann, ist der bestimmende Typ der eindeutige Typ, auf den alle anderen Typen im Array eingrenzen können.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-129">If this unique type cannot be determined, the dominant type is the unique type that all other types in the array can narrow to.</span></span> <span data-ttu-id="e8ee5-130">Wenn keiner dieser eindeutigen Typen bestimmt werden kann, ist der bestimmende Typ `Object`.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-130">If neither of these unique types can be determined, the dominant type is `Object`.</span></span> <span data-ttu-id="e8ee5-131">In diesem Fall tritt ein `Option Strict` Compilerfehler `On`auf, wenn auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-131">In this case, if `Option Strict` is set to `On`, a compiler error occurs.</span></span>  
  
     <span data-ttu-id="e8ee5-132">Wenn die Ausdrücke `Return` , die für die-Anweisung bereitgestellt werden, z. b. Werte vom Typ `Integer`, `Long`und `Double`enthalten, `Double`ist das resultierende Array vom Typ.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-132">For example, if the expressions supplied to the `Return` statement contain values of type `Integer`, `Long`, and `Double`, the resulting array is of type `Double`.</span></span> <span data-ttu-id="e8ee5-133">`Integer` Und werden`Long` nur aufund`Double`erweitert. `Double`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-133">Both `Integer` and `Long` widen to `Double` and only `Double`.</span></span> <span data-ttu-id="e8ee5-134">Daher ist `Double` der bestimmende Typ.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-134">Therefore, `Double` is the dominant type.</span></span> <span data-ttu-id="e8ee5-135">Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="e8ee5-135">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
- <span data-ttu-id="e8ee5-136">Der Text einer einzeiligen Funktion muss ein Ausdruck sein, der einen Wert zurückgibt, nicht eine-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-136">The body of a single-line function must be an expression that returns a value, not a statement.</span></span> <span data-ttu-id="e8ee5-137">Es gibt keine `Return` -Anweisung für einzeilige Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-137">There is no `Return` statement for single-line functions.</span></span> <span data-ttu-id="e8ee5-138">Der von der einzeiligen Funktion zurückgegebene Wert ist der Wert des Ausdrucks im Text der Funktion.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-138">The value returned by the single-line function is the value of the expression in the body of the function.</span></span>  
  
- <span data-ttu-id="e8ee5-139">Der Text einer einzeiligen Unterroutine muss eine einzeilige Anweisung sein.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-139">The body of a single-line subroutine must be single-line statement.</span></span>  
  
- <span data-ttu-id="e8ee5-140">Einzeilige Funktionen und Unterroutinen enthalten `End Function` keine-oder `End Sub` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-140">Single-line functions and subroutines do not include an `End Function` or `End Sub` statement.</span></span>  
  
- <span data-ttu-id="e8ee5-141">Sie können den Datentyp eines Lambda-Ausdrucks Parameters angeben, indem Sie `As` das-Schlüsselwort verwenden, oder der Datentyp des Parameters kann abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-141">You can specify the data type of a lambda expression parameter by using the `As` keyword, or the data type of the parameter can be inferred.</span></span> <span data-ttu-id="e8ee5-142">Entweder müssen alle Parameter über bestimmte Datentypen verfügen, oder alle müssen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-142">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="e8ee5-143">`Optional`- `Paramarray` und-Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-143">`Optional` and `Paramarray` parameters are not permitted.</span></span>  
  
- <span data-ttu-id="e8ee5-144">Generische Parameter sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-144">Generic parameters are not permitted.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="e8ee5-145">Asynchrone Lambdas</span><span class="sxs-lookup"><span data-stu-id="e8ee5-145">Async Lambdas</span></span>  
 <span data-ttu-id="e8ee5-146">Sie können problemlos Lambda Ausdrücke und Anweisungen erstellen, die die asynchrone Verarbeitung mithilfe der Schlüsselwörter [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Erwartung des Operators](../../../../visual-basic/language-reference/operators/await-operator.md) einschließen.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-146">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [Async](../../../../visual-basic/language-reference/modifiers/async.md) and [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md) keywords.</span></span> <span data-ttu-id="e8ee5-147">Das folgende Windows Forms enthält z. B. einen Ereignishandler, der eine Async-Methode, `ExampleMethodAsync`, aufruft und erwartet.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-147">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
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
  
 <span data-ttu-id="e8ee5-148">Sie können denselben Ereignishandler hinzufügen, indem Sie einen Async-Lambda in einer [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-148">You can add the same event handler by using an async lambda in an [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md).</span></span> <span data-ttu-id="e8ee5-149">Um diesen Handler hinzuzufügen, fügen Sie einen `Async` -Modifizierer vor der Lambda-Parameterliste, wie im folgenden Beispiel dargestellt, hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-149">To add this handler, add an `Async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
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
  
 <span data-ttu-id="e8ee5-150">Weitere Informationen zum Erstellen und Verwenden von Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und warten](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="e8ee5-150">For more information about how to create and use async methods, see [Asynchronous Programming with Async and Await](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="context"></a><span data-ttu-id="e8ee5-151">Kontext</span><span class="sxs-lookup"><span data-stu-id="e8ee5-151">Context</span></span>  
 <span data-ttu-id="e8ee5-152">Ein Lambda-Ausdruck nutzt seinen Kontext mit dem Bereich, in dem er definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-152">A lambda expression shares its context with the scope within which it is defined.</span></span> <span data-ttu-id="e8ee5-153">Sie verfügt über die gleichen Zugriffsrechte wie jeder Code, der in den enthaltenden Bereich geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-153">It has the same access rights as any code written in the containing scope.</span></span> <span data-ttu-id="e8ee5-154">Dies schließt den Zugriff auf Member-Variablen,-Funktionen und `Me`-subs,-Parameter und-Parameter sowie lokale Variablen im enthaltenden Bereich ein.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-154">This includes access to member variables, functions and subs, `Me`, and parameters and local variables in the containing scope.</span></span>  
  
 <span data-ttu-id="e8ee5-155">Der Zugriff auf lokale Variablen und Parameter im enthaltenden Bereich kann über die Gültigkeitsdauer dieses Bereichs hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-155">Access to local variables and parameters in the containing scope can extend beyond the lifetime of that scope.</span></span> <span data-ttu-id="e8ee5-156">Solange ein Delegat, der sich auf einen Lambda-Ausdruck bezieht, nicht für Garbage Collection verfügbar ist, wird der Zugriff auf die Variablen in der ursprünglichen Umgebung beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-156">As long as a delegate referring to a lambda expression is not available to garbage collection, access to the variables in the original environment is retained.</span></span> <span data-ttu-id="e8ee5-157">Im folgenden Beispiel ist Variable `target` `makeTheGame`local in, die Methode, in der der Lambda-Ausdruck `playTheGame` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-157">In the following example, variable `target` is local to `makeTheGame`, the method in which the lambda expression `playTheGame` is defined.</span></span> <span data-ttu-id="e8ee5-158">Beachten Sie, dass der zurückgegebene Lambda- `takeAGuess` Ausdruck `Main`, der in zugewiesen ist, weiterhin auf `target`die lokale Variable zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-158">Note that the returned lambda expression, assigned to `takeAGuess` in `Main`, still has access to the local variable `target`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class6.vb#12)]  
  
 <span data-ttu-id="e8ee5-159">Im folgenden Beispiel wird der große Bereich von Zugriffsrechten für den in einem Lambda-Ausdruck aufgeführten Ausdruck veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-159">The following example demonstrates the wide range of access rights of the nested lambda expression.</span></span> <span data-ttu-id="e8ee5-160">Wenn der zurückgegebene Lambda-Ausdruck von `Main` als `aDel`ausgeführt wird, greift er auf diese Elemente zu:</span><span class="sxs-lookup"><span data-stu-id="e8ee5-160">When the returned lambda expression is executed from `Main` as `aDel`, it accesses these elements:</span></span>  
  
- <span data-ttu-id="e8ee5-161">Ein Feld der Klasse, in der es definiert ist:`aField`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-161">A field of the class in which it is defined: `aField`</span></span>  
  
- <span data-ttu-id="e8ee5-162">Eine Eigenschaft der Klasse, in der Sie definiert ist:`aProp`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-162">A property of the class in which it is defined: `aProp`</span></span>  
  
- <span data-ttu-id="e8ee5-163">Ein Parameter der- `functionWithNestedLambda`Methode, in der er definiert ist:`level1`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-163">A parameter of method `functionWithNestedLambda`, in which it is defined: `level1`</span></span>  
  
- <span data-ttu-id="e8ee5-164">Eine lokale Variable von `functionWithNestedLambda`:`localVar`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-164">A local variable of `functionWithNestedLambda`: `localVar`</span></span>  
  
- <span data-ttu-id="e8ee5-165">Ein Parameter des Lambda-Ausdrucks, in dem er sich befindet:`level2`</span><span class="sxs-lookup"><span data-stu-id="e8ee5-165">A parameter of the lambda expression in which it is nested: `level2`</span></span>  
  
 [!code-vb[VbVbalrLambdas#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class3.vb#9)]  
  
## <a name="converting-to-a-delegate-type"></a><span data-ttu-id="e8ee5-166">Umstellen in einen Delegattyp</span><span class="sxs-lookup"><span data-stu-id="e8ee5-166">Converting to a Delegate Type</span></span>  
 <span data-ttu-id="e8ee5-167">Ein Lambda-Ausdruck kann implizit in einen kompatiblen Delegattyp konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-167">A lambda expression can be implicitly converted to a compatible delegate type.</span></span> <span data-ttu-id="e8ee5-168">Informationen zu den allgemeinen Kompatibilitätsanforderungen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="e8ee5-168">For information about the general requirements for compatibility, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span> <span data-ttu-id="e8ee5-169">Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit in `Func(Of Integer, Boolean)` oder eine entsprechende Delegatsignatur konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-169">For example, the following code example shows a lambda expression that implicitly converts to `Func(Of Integer, Boolean)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#16)]  
  
 <span data-ttu-id="e8ee5-170">Das folgende Codebeispiel zeigt einen Lambda-Ausdruck, der implizit `Sub(Of Double, String, Double)` in oder eine entsprechende Delegatsignatur konvertiert.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-170">The following code example shows a lambda expression that implicitly converts to `Sub(Of Double, String, Double)` or a matching delegate signature.</span></span>  
  
 [!code-vb[VbVbalrLambdas#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/class7.vb#23)]  
  
 <span data-ttu-id="e8ee5-171">Wenn Sie Delegaten Lambda-Ausdrücke zuweisen oder Sie als Argumente an Prozeduren übergeben, können Sie die Parameternamen angeben, deren Datentypen jedoch weglassen und die Typen aus dem Delegaten entnommen werden.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-171">When you assign lambda expressions to delegates or pass them as arguments to procedures, you can specify the parameter names but omit their data types, letting the types be taken from the delegate.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e8ee5-172">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e8ee5-172">Examples</span></span>  
  
- <span data-ttu-id="e8ee5-173">Im folgenden Beispiel wird ein Lambda-Ausdruck definiert `True` , der zurückgibt, wenn das Werte zulässt-Argument `False` über einen zugewiesenen Wert `Nothing`verfügt und wenn sein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-173">The following example defines a lambda expression that returns `True` if the nullable argument has an assigned value, and `False` if its value is `Nothing`.</span></span>  
  
     [!code-vb[VbVbalrLambdas#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#4)]  
  
- <span data-ttu-id="e8ee5-174">Im folgenden Beispiel wird ein Lambda-Ausdruck definiert, der den Index des letzten Elements in einem Array zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e8ee5-174">The following example defines a lambda expression that returns the index of the last element in an array.</span></span>  
  
     [!code-vb[VbVbalrLambdas#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="e8ee5-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8ee5-175">See also</span></span>

- [<span data-ttu-id="e8ee5-176">Verfahren</span><span class="sxs-lookup"><span data-stu-id="e8ee5-176">Procedures</span></span>](./index.md)
- [<span data-ttu-id="e8ee5-177">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ee5-177">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="e8ee5-178">Delegaten</span><span class="sxs-lookup"><span data-stu-id="e8ee5-178">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="e8ee5-179">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e8ee5-179">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="e8ee5-180">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e8ee5-180">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="e8ee5-181">Auf NULL festlegbare Werttypen</span><span class="sxs-lookup"><span data-stu-id="e8ee5-181">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="e8ee5-182">Vorgehensweise: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8ee5-182">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="e8ee5-183">Vorgehensweise: Erstellen eines Lambda Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="e8ee5-183">How to: Create a Lambda Expression</span></span>](./how-to-create-a-lambda-expression.md)
- [<span data-ttu-id="e8ee5-184">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="e8ee5-184">Relaxed Delegate Conversion</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
