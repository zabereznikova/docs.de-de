---
title: Asynchrone Rückgabetypen
ms.date: 07/20/2015
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
ms.openlocfilehash: 96d3a945a49a12f7c2d5d60e8ee59ce047a0bae6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347979"
---
# <a name="async-return-types-visual-basic"></a><span data-ttu-id="0b831-102">Async-Rückgabe Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b831-102">Async Return Types (Visual Basic)</span></span>

<span data-ttu-id="0b831-103">Asynchrone Methoden haben drei mögliche Rückgabetypen: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> und den void-Typ.</span><span class="sxs-lookup"><span data-stu-id="0b831-103">Async methods have three possible return types: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, and void.</span></span> <span data-ttu-id="0b831-104">In Visual Basic wird der void-Rückgabetyp als [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)-Prozedur geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b831-104">In Visual Basic, the void return type is written as a [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedure.</span></span> <span data-ttu-id="0b831-105">Weitere Informationen zu Async-Methoden finden Sie unter [asynchrone Programmierung mit Async und warten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="0b831-105">For more information about async methods, see [Asynchronous Programming with Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).</span></span>

<span data-ttu-id="0b831-106">Jeder Rückgabetyp wird in einem der folgenden Abschnitte untersucht und am Ende des Themas wird ein vollständiges Beispiel aller drei Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0b831-106">Each return type is examined in one of the following sections, and you can find a full example that uses all three types at the end of the topic.</span></span>

> [!NOTE]
> <span data-ttu-id="0b831-107">Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="0b831-107">To run the example, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>

## <a name="BKMK_TaskTReturnType"></a> <span data-ttu-id="0b831-108">Task(T)-Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="0b831-108">Task(T) Return Type</span></span>

<span data-ttu-id="0b831-109">Der <xref:System.Threading.Tasks.Task%601> Rückgabetyp wird für eine asynchrone Methode verwendet, die eine [Return](../../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung enthält, in der der Operand vom Typ `TResult`ist.</span><span class="sxs-lookup"><span data-stu-id="0b831-109">The <xref:System.Threading.Tasks.Task%601> return type is used for an async method that contains a [Return](../../../../visual-basic/language-reference/statements/return-statement.md) statement in which the operand has type `TResult`.</span></span>

<span data-ttu-id="0b831-110">Im folgenden Beispiel enthält die asynchrone `TaskOfT_MethodAsync`-Methode eine "return"-Anweisung, die eine ganze Zahl zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0b831-110">In the following example, the `TaskOfT_MethodAsync` async method contains a return statement that returns an integer.</span></span> <span data-ttu-id="0b831-111">Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task(Of Integer)` haben.</span><span class="sxs-lookup"><span data-stu-id="0b831-111">Therefore, the method declaration must specify a return type of `Task(Of Integer)`.</span></span>

```vb
' TASK(OF T) EXAMPLE
Async Function TaskOfT_MethodAsync() As Task(Of Integer)

    ' The body of an async method is expected to contain an awaited
    ' asynchronous call.
    ' Task.FromResult is a placeholder for actual work that returns a string.
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())

    ' The method then can process the result in some way.
    Dim leisureHours As Integer
    If today.First() = "S" Then
        leisureHours = 16
    Else
        leisureHours = 5
    End If

    ' Because the return statement specifies an operand of type Integer, the
    ' method must have a return type of Task(Of Integer).
    Return leisureHours
End Function
```

<span data-ttu-id="0b831-112">Wenn `TaskOfT_MethodAsync` aus einem "await"-Ausdruck aufgerufen wird, ruft der "await"-Ausdruck den ganzzahligen Wert ab (der Wert von `leisureHours`), der in der Aufgabe gespeichert wird, die von `TaskOfT_MethodAsync` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0b831-112">When `TaskOfT_MethodAsync` is called from within an await expression, the await expression retrieves the integer value (the value of `leisureHours`) that's stored in the task that's returned by `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="0b831-113">Weitere Informationen zu Erwartungs Ausdrücken finden Sie unter [Erwartung eines Operators](../../../../visual-basic/language-reference/operators/await-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0b831-113">For more information about await expressions, see [Await Operator](../../../../visual-basic/language-reference/operators/await-operator.md).</span></span>

<span data-ttu-id="0b831-114">Der folgende Code ruft auf und erwartet die `TaskOfT_MethodAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="0b831-114">The following code calls and awaits method `TaskOfT_MethodAsync`.</span></span> <span data-ttu-id="0b831-115">Das Ergebnis wird der `result1`-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0b831-115">The result is assigned to the `result1` variable.</span></span>

```vb
' Call and await the Task(Of T)-returning async method in the same statement.
Dim result1 As Integer = Await TaskOfT_MethodAsync()
```

<span data-ttu-id="0b831-116">Sie können die Vorgehensweise besser verstehen, wenn Sie den Aufruf von `TaskOfT_MethodAsync` von der Anwendung von `Await` trennen, wie der folgenden Code zeigt.</span><span class="sxs-lookup"><span data-stu-id="0b831-116">You can better understand how this happens by separating the call to `TaskOfT_MethodAsync` from the application of `Await`, as the following code shows.</span></span> <span data-ttu-id="0b831-117">Ein Aufruf der `TaskOfT_MethodAsync`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task(Of Integer)` zurück, wie Sie es von der Deklaration der Methode erwarten.</span><span class="sxs-lookup"><span data-stu-id="0b831-117">A call to method `TaskOfT_MethodAsync` that isn't immediately awaited returns a `Task(Of Integer)`, as you would expect from the declaration of the method.</span></span> <span data-ttu-id="0b831-118">Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0b831-118">The task is assigned to the `integerTask` variable in the example.</span></span> <span data-ttu-id="0b831-119">Da `integerTask` eine <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`.</span><span class="sxs-lookup"><span data-stu-id="0b831-119">Because `integerTask` is a <xref:System.Threading.Tasks.Task%601>, it contains a <xref:System.Threading.Tasks.Task%601.Result> property of type `TResult`.</span></span> <span data-ttu-id="0b831-120">In diesem Fall stellt TResult einen ganzzahligen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="0b831-120">In this case, TResult represents an integer type.</span></span> <span data-ttu-id="0b831-121">Wenn `Await` auf `integerTask` angewendet wird, wertet der „await“-Ausdruck den Inhalt der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> von `integerTask` aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-121">When `Await` is applied to `integerTask`, the await expression evaluates to the contents of the <xref:System.Threading.Tasks.Task%601.Result%2A> property of `integerTask`.</span></span> <span data-ttu-id="0b831-122">Der Wert wird der `result2`-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0b831-122">The value is assigned to the `result2` variable.</span></span>

> [!WARNING]
> <span data-ttu-id="0b831-123">Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0b831-123">The <xref:System.Threading.Tasks.Task%601.Result%2A> property is a blocking property.</span></span> <span data-ttu-id="0b831-124">Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0b831-124">If you try to access it before its task is finished, the thread that's currently active is blocked until the task completes and the value is available.</span></span> <span data-ttu-id="0b831-125">In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `Await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="0b831-125">In most cases, you should access the value by using `Await` instead of accessing the property directly.</span></span>

```vb
' Call and await in separate statements.
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()

' You can do other work that does not rely on resultTask before awaiting.
textBox1.Text &= "Application can continue working while the Task(Of T) runs. . . . " & vbCrLf

Dim result2 As Integer = Await integerTask
```

<span data-ttu-id="0b831-126">Die Anzeigeanweisungen im folgenden Code überprüfen, dass die Werte der `result1`-Variable, der `result2`-Variable und der `Result`-Eigenschaft gleich sind.</span><span class="sxs-lookup"><span data-stu-id="0b831-126">The display statements in the following code verify that the values of the `result1` variable, the `result2` variable, and the `Result` property are the same.</span></span> <span data-ttu-id="0b831-127">Beachten Sie, dass die `Result`-Eigenschaft eine Blocking-Eigenschaft ist und nicht darauf zugegriffen werden sollte, bevor die Aufgabe abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0b831-127">Remember that the `Result` property is a blocking property and shouldn't be accessed before its task has been awaited.</span></span>

```vb
' Display the values of the result1 variable, the result2 variable, and
' the resultTask.Result property.
textBox1.Text &= vbCrLf & $"Value of result1 variable:   {result1}" & vbCrLf
textBox1.Text &= $"Value of result2 variable:   {result2}" & vbCrLf
textBox1.Text &= $"Value of resultTask.Result:  {integerTask.Result}" & vbCrLf
```

## <a name="BKMK_TaskReturnType"></a> <span data-ttu-id="0b831-128">Aufgabenrückgabetyp</span><span class="sxs-lookup"><span data-stu-id="0b831-128">Task Return Type</span></span>

<span data-ttu-id="0b831-129">Asynchrone Methoden, die keine return-Anweisung enthalten oder eine return-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="0b831-129">Async methods that don't contain a return statement or that contain a return statement that doesn't return an operand usually have a return type of <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="0b831-130">Bei solchen Methoden handelt es sich um [unter](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Prozeduren, wenn Sie zur synchronen Durchführung geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="0b831-130">Such methods would be [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) procedures if they were written to run synchronously.</span></span> <span data-ttu-id="0b831-131">Wenn Sie einen `Task`-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen `Await`-Operator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.</span><span class="sxs-lookup"><span data-stu-id="0b831-131">If you use a `Task` return type for an async method, a calling method can use an `Await` operator to suspend the caller's completion until the called async method has finished.</span></span>

<span data-ttu-id="0b831-132">Im folgenden Beispiel enthält die asynchrone `Task_MethodAsync`-Methode keine "return"-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0b831-132">In the following example, async method `Task_MethodAsync` doesn't contain a return statement.</span></span> <span data-ttu-id="0b831-133">Daher geben Sie einen `Task`-Rückgabetyp für die Methode an, die `Task_MethodAsync` ein Warten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0b831-133">Therefore, you specify a return type of `Task` for the method, which enables `Task_MethodAsync` to be awaited.</span></span> <span data-ttu-id="0b831-134">Die Definition des `Task`-Typs enthält keine `Result`-Eigenschaft, um einen Rückgabewert zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0b831-134">The definition of the `Task` type doesn't include a `Result` property to store a return value.</span></span>

```vb
' TASK EXAMPLE
Async Function Task_MethodAsync() As Task

    ' The body of an async method is expected to contain an awaited
    ' asynchronous call.
    ' Task.Delay is a placeholder for actual work.
    Await Task.Delay(2000)
    textBox1.Text &= vbCrLf & "Sorry for the delay. . . ." & vbCrLf

    ' This method has no return statement, so its return type is Task.
End Function
```

<span data-ttu-id="0b831-135">`Task_MethodAsync` wird aufgerufen und erwartet, indem eine Erwartungs Anweisung anstelle eines Erwartungs Ausdrucks verwendet wird, ähnlich der aufrufenden Anweisung für eine synchrone `Sub` oder eine void-Rückgabe Methode.</span><span class="sxs-lookup"><span data-stu-id="0b831-135">`Task_MethodAsync` is called and awaited by using an await statement instead of an await expression, similar to the calling statement for a synchronous `Sub` or void-returning method.</span></span> <span data-ttu-id="0b831-136">Die Anwendung eines `Await`-Operators erzeugt in diesem Fall keinen Wert.</span><span class="sxs-lookup"><span data-stu-id="0b831-136">The application of an `Await` operator in this case doesn't produce a value.</span></span>

<span data-ttu-id="0b831-137">Der folgende Code ruft auf und erwartet die `Task_MethodAsync`-Methode.</span><span class="sxs-lookup"><span data-stu-id="0b831-137">The following code calls and awaits method `Task_MethodAsync`.</span></span>

```vb
' Call and await the Task-returning async method in the same statement.
Await Task_MethodAsync()
```

<span data-ttu-id="0b831-138">Wie im vorherigen <xref:System.Threading.Tasks.Task%601> Beispiel können Sie den-Aufruf`Task_MethodAsync` von der Anwendung eines `Await`-Operators trennen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b831-138">As in the previous <xref:System.Threading.Tasks.Task%601> example, you can separate the call to `Task_MethodAsync` from the application of an `Await` operator, as the following code shows.</span></span> <span data-ttu-id="0b831-139">Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b831-139">However, remember that a `Task` doesn't have a `Result` property, and that no value is produced when an await operator is applied to a `Task`.</span></span>

<span data-ttu-id="0b831-140">Der folgende Code trennt Aufrufe von `Task_MethodAsync` vom Erwarten der Aufgabe, die `Task_MethodAsync` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0b831-140">The following code separates calling `Task_MethodAsync` from awaiting the task that `Task_MethodAsync` returns.</span></span>

```vb
' Call and await in separate statements.
Dim simpleTask As Task = Task_MethodAsync()

' You can do other work that does not rely on simpleTask before awaiting.
textBox1.Text &= vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf

Await simpleTask
```

## <a name="BKMK_VoidReturnType"></a> <span data-ttu-id="0b831-141">Rückgabetyp „Void“</span><span class="sxs-lookup"><span data-stu-id="0b831-141">Void Return Type</span></span>

<span data-ttu-id="0b831-142">Die primäre Verwendung von `Sub` Prozeduren erfolgt in Ereignis Handlern, bei denen kein Rückgabetyp (in anderen Sprachen als void-Rückgabetyp bezeichnet) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0b831-142">The primary use of `Sub` procedures is in event handlers, where there is no return type (referred to as a void return type in other languages).</span></span> <span data-ttu-id="0b831-143">Eine "void"-Rückgabe kann auch verwendet werden, um Methoden mit einer "void"-Rückgabe zu überschreiben, oder auch für Methoden, die "Fire-and-Forget"-Aktivitäten ausführen.</span><span class="sxs-lookup"><span data-stu-id="0b831-143">A void return also can be used to override void-returning methods or for methods that perform activities that can be categorized as "fire and forget."</span></span> <span data-ttu-id="0b831-144">Sie sollten nach Möglichkeit immer eine `Task` zurückgeben, da eine "void" zurückgebende asynchrone Methode nicht erwartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b831-144">However, you should return a `Task` wherever possible, because a void-returning async method can't be awaited.</span></span> <span data-ttu-id="0b831-145">Jeder Aufrufer einer solchen Methode muss in der Lage sein, in seiner Ausführung bis zum Abschluss fortzufahren, ohne auf die aufgerufene asynchrone Methode zu warten, und der Aufrufer muss unabhängig von den Werten oder Ausnahmen sein, die die asynchrone Methode generiert.</span><span class="sxs-lookup"><span data-stu-id="0b831-145">Any caller of such a method must be able to continue to completion without waiting for the called async method to finish, and the caller must be independent of any values or exceptions that the async method generates.</span></span>

<span data-ttu-id="0b831-146">Der Aufrufer einer "void" zurückgebenden asynchronen Methode kann die von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen.</span><span class="sxs-lookup"><span data-stu-id="0b831-146">The caller of a void-returning async method can't catch exceptions that are thrown from the method, and such unhandled exceptions are likely to cause your application to fail.</span></span> <span data-ttu-id="0b831-147">Wenn eine Ausnahme in einer asynchronen Methode auftritt, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, wird die Ausnahme in der zurückgegebenen Aufgabe gespeichert und erneut ausgelöst, wenn die Aufgabe erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="0b831-147">If an exception occurs in an async method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>, the exception is stored in the returned task, and rethrown when the task is awaited.</span></span> <span data-ttu-id="0b831-148">Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt und die Aufrufe der Methode erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="0b831-148">Therefore, make sure that any async method that can produce an exception has a return type of <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> and that calls to the method are awaited.</span></span>

<span data-ttu-id="0b831-149">Weitere Informationen zum Auffangen von Ausnahmen in async-Methoden finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally-Anweisung).</span><span class="sxs-lookup"><span data-stu-id="0b831-149">For more information about how to catch exceptions in async methods, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>

<span data-ttu-id="0b831-150">Der folgende Code definiert einen asynchrone Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="0b831-150">The following code defines an async event handler.</span></span>

```vb
' SUB EXAMPLE
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click

    textBox1.Clear()

    ' Start the process and await its completion. DriverAsync is a
    ' Task-returning async method.
    Await DriverAsync()

    ' Say goodbye.
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."
End Sub
```

## <a name="BKMK_Example"></a> <span data-ttu-id="0b831-151">Vollständiges Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b831-151">Complete Example</span></span>

<span data-ttu-id="0b831-152">Das nächste Windows Presentation Foundation (WPF)-Projekt enthält die Codebeispiele aus diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="0b831-152">The following Windows Presentation Foundation (WPF) project contains the code examples from this topic.</span></span>

 <span data-ttu-id="0b831-153">Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0b831-153">To run the project, perform the following steps:</span></span>

1. <span data-ttu-id="0b831-154">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b831-154">Start Visual Studio.</span></span>

2. <span data-ttu-id="0b831-155">Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-155">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="0b831-156">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b831-156">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="0b831-157">Wählen Sie in der Kategorie **installiert**, **Vorlagen** die Option **Visual Basic**aus, und wählen Sie dann **Windows**aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-157">In the **Installed**, **Templates** category, choose **Visual Basic**, and then choose **Windows**.</span></span> <span data-ttu-id="0b831-158">Wählen Sie in der Liste der Projekttypen die **WPF-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-158">Choose **WPF Application** from the list of project types.</span></span>

4. <span data-ttu-id="0b831-159">Geben Sie `AsyncReturnTypes` als Name für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-159">Enter `AsyncReturnTypes` as the name of the project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="0b831-160">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b831-160">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="0b831-161">Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-161">In the Visual Studio Code Editor, choose the **MainWindow.xaml** tab.</span></span>

     <span data-ttu-id="0b831-162">Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer** und wählen dann **Öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-162">If the tab is not visible, open the shortcut menu for MainWindow.xaml in **Solution Explorer**, and then choose **Open**.</span></span>

6. <span data-ttu-id="0b831-163">Ersetzen Sie den Code im Fenster **XAML** von „MainWindow.xaml“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="0b831-163">In the **XAML** window of MainWindow.xaml, replace the code with the following code.</span></span>

    ```vb
    <Window x:Class="MainWindow"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            Title="MainWindow" Height="350" Width="525">
        <Grid>
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>

        </Grid>
    </Window>
    ```

     <span data-ttu-id="0b831-164">Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird im Fenster **Entwurf** von „MainWindow.xaml“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b831-164">A simple window that contains a text box and a button appears in the **Design** window of MainWindow.xaml.</span></span>

7. <span data-ttu-id="0b831-165">Öffnen Sie in **Projektmappen-Explorer**das Kontextmenü für "MainWindow. XAML. vb", und wählen Sie dann **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="0b831-165">In **Solution Explorer**, open the shortcut menu for MainWindow.xaml.vb, and then choose **View Code**.</span></span>

8. <span data-ttu-id="0b831-166">Ersetzen Sie den Code in „MainWindow.xaml.vb“ durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="0b831-166">Replace the code in MainWindow.xaml.vb with the following code.</span></span>

    ```vb
    Class MainWindow

        ' SUB EXAMPLE
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click

            textBox1.Clear()

            ' Start the process and await its completion. DriverAsync is a
            ' Task-returning async method.
            Await DriverAsync()

            ' Say goodbye.
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."
        End Sub

        Async Function DriverAsync() As Task

            ' Task(Of T)
            ' Call and await the Task(Of T)-returning async method in the same statement.
            Dim result1 As Integer = Await TaskOfT_MethodAsync()

            ' Call and await in separate statements.
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()

            ' You can do other work that does not rely on resultTask before awaiting.
            textBox1.Text &= "Application can continue working while the Task(Of T) runs. . . . " & vbCrLf

            Dim result2 As Integer = Await integerTask

            ' Display the values of the result1 variable, the result2 variable, and
            ' the resultTask.Result property.
            textBox1.Text &= vbCrLf & $"Value of result1 variable:   {result1}" & vbCrLf
            textBox1.Text &= $"Value of result2 variable:   {result2}" & vbCrLf
            textBox1.Text &= $"Value of resultTask.Result:  {integerTask.Result}" & vbCrLf

            ' Task
            ' Call and await the Task-returning async method in the same statement.
            Await Task_MethodAsync()

            ' Call and await in separate statements.
            Dim simpleTask As Task = Task_MethodAsync()

            ' You can do other work that does not rely on simpleTask before awaiting.
            textBox1.Text &= vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf

            Await simpleTask
        End Function

        ' TASK(OF T) EXAMPLE
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)

            ' The body of an async method is expected to contain an awaited
            ' asynchronous call.
            ' Task.FromResult is a placeholder for actual work that returns a string.
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())

            ' The method then can process the result in some way.
            Dim leisureHours As Integer
            If today.First() = "S" Then
                leisureHours = 16
            Else
                leisureHours = 5
            End If

            ' Because the return statement specifies an operand of type Integer, the
            ' method must have a return type of Task(Of Integer).
            Return leisureHours
        End Function

        ' TASK EXAMPLE
        Async Function Task_MethodAsync() As Task

            ' The body of an async method is expected to contain an awaited
            ' asynchronous call.
            ' Task.Delay is a placeholder for actual work.
            Await Task.Delay(2000)
            textBox1.Text &= vbCrLf & "Sorry for the delay. . . ." & vbCrLf

            ' This method has no return statement, so its return type is Task.
        End Function

    End Class
    ```

9. <span data-ttu-id="0b831-167">Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .</span><span class="sxs-lookup"><span data-stu-id="0b831-167">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>

     <span data-ttu-id="0b831-168">Die folgende Ausgabe sollte angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="0b831-168">The following output should appear:</span></span>

    ```console
    Application can continue working while the Task<T> runs. . . .

    Value of result1 variable:   5
    Value of result2 variable:   5
    Value of integerTask.Result: 5

    Sorry for the delay. . . .

    Application can continue working while the Task runs. . . .

    Sorry for the delay. . . .

    All done, exiting button-click event handler.
    ```

## <a name="see-also"></a><span data-ttu-id="0b831-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b831-169">See also</span></span>

- <xref:System.Threading.Tasks.Task.FromResult%2A>
- <span data-ttu-id="0b831-170">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md) (Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0b831-170">[Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)</span></span>
- [<span data-ttu-id="0b831-171">Ablaufsteuerung in asynchronen Programmen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b831-171">Control Flow in Async Programs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
- [<span data-ttu-id="0b831-172">Async</span><span class="sxs-lookup"><span data-stu-id="0b831-172">Async</span></span>](../../../../visual-basic/language-reference/modifiers/async.md)
- [<span data-ttu-id="0b831-173">Await-Operator</span><span class="sxs-lookup"><span data-stu-id="0b831-173">Await Operator</span></span>](../../../../visual-basic/language-reference/operators/await-operator.md)
