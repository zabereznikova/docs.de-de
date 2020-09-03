---
description: async – C#-Referenz
title: async – C#-Referenz
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 5a70389c9c423300fad03123cfc4738dfe10e481
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118519"
---
# <a name="async-c-reference"></a><span data-ttu-id="e4eb1-103">async (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e4eb1-103">async (C# Reference)</span></span>

<span data-ttu-id="e4eb1-104">Mit dem `async`-Modifizierer können Sie angeben, dass eine Methode, ein [Lambdaausdruck](../operators/lambda-expressions.md) oder eine [anonyme Methode](../operators/delegate-operator.md) asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-104">Use the `async` modifier to specify that a method, [lambda expression](../operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="e4eb1-105">Wenn Sie diesen Modifizierer auf Methoden oder Ausdrücke anwenden, wird dies als *asynchrone Methode* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-105">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="e4eb1-106">Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `ExampleMethodAsync` definiert:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-106">The following example defines an async method named `ExampleMethodAsync`:</span></span>

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

<span data-ttu-id="e4eb1-107">Wenn Sie mit der asynchronen Programmierung noch nicht vertraut sind oder nicht wissen, wie eine Async-Methode den [`await`-Operator](../operators/await.md) verwendet, um Aufgaben mit potenziell langer Laufzeit auszuführen, ohne den Thread des Aufrufers zu blockieren, können Sie sich die Einführung unter [Asynchrone Programmierung mit async und await](../../programming-guide/concepts/async/index.md) durchlesen.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-107">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller's thread, read the introduction in [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="e4eb1-108">Der folgende Code befindet sich in einer asynchronen Methode und ruft die <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-108">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

<span data-ttu-id="e4eb1-109">Eine asynchrone Methode wird bis zum ersten `await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-109">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="e4eb1-110">In der Zwischenzeit wird die Steuerung an den Aufrufer der Methode zurückgegeben, wie das Beispiel in nächsten Thema zeigt.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-110">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>

<span data-ttu-id="e4eb1-111">Wenn die Methode, die mit dem `async`-Schlüsselwort geändert wird, keinen `await`-Ausdruck oder keine await-Anweisung enthält, wird die Methode synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-111">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="e4eb1-112">Mit einer Compilerwarnung werden Sie auf alle asynchronen Methoden hingewiesen, die keine `await`-Anweisungen enthalten, da dies möglicherweise auf einen Fehler hindeutet.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-112">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="e4eb1-113">Siehe [Compilerwarnung (Stufe 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="e4eb1-113">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>

 <span data-ttu-id="e4eb1-114">Das `async`-Schlüsselwort ist insofern kontextabhängig, dass es nur dann ein Schlüsselwort ist, wenn mit ihm eine Methode, ein Lambda-Ausdruck oder eine anonyme Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-114">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="e4eb1-115">In allen anderen Kontexten wird es als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-115">In all other contexts, it's interpreted as an identifier.</span></span>

## <a name="example"></a><span data-ttu-id="e4eb1-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4eb1-116">Example</span></span>
<span data-ttu-id="e4eb1-117">Im folgenden Beispiel werden die Struktur und Ablaufsteuerung zwischen einem asynchronen Ereignishandler, `StartButton_Click`, und einer asynchronen Methode, `ExampleMethodAsync`, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-117">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="e4eb1-118">Das Ergebnis der asynchronen Methode ist die Anzahl von Zeichen einer Webseite.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-118">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="e4eb1-119">Der Code ist für eine Windows Presentation Foundation (WPF)- oder Windows Store-Anwendung geeignet, die Sie in Visual Studio erstellen. Informationen zum Einrichten der Anwendung finden Sie in den Codekommentaren.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-119">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>

<span data-ttu-id="e4eb1-120">Sie können diesen Code in Visual Studio als Windows Presentation Foundation (WPF)-App oder Windows Store-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-120">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="e4eb1-121">Sie benötigen ein Schaltflächen-Steuerelement mit dem Namen `StartButton` und ein Textfeldsteuerelement mit dem Namen `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-121">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="e4eb1-122">Denken Sie daran, die Namen und den Handler so festzulegen, dass es in etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-122">Remember to set the names and handler so that you have something like this:</span></span>

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

<span data-ttu-id="e4eb1-123">So führen Sie den Code als WPF-App aus:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-123">To run the code as a WPF app:</span></span>

- <span data-ttu-id="e4eb1-124">Fügen Sie diesen Code in die `MainWindow`-Klasse in „MainWindow.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-124">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>
- <span data-ttu-id="e4eb1-125">Fügen Sie einen Verweis auf „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-125">Add a reference to System.Net.Http.</span></span>
- <span data-ttu-id="e4eb1-126">Fügen Sie eine `using`-Anweisung für „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-126">Add a `using` directive for System.Net.Http.</span></span>

<span data-ttu-id="e4eb1-127">So führen Sie den Code als Windows Store-App aus:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-127">To run the code as a Windows Store app:</span></span>

- <span data-ttu-id="e4eb1-128">Fügen Sie diesen Code in die `MainPage`-Klasse in „MainPage.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-128">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>
- <span data-ttu-id="e4eb1-129">Fügen Sie using-Anweisungen für „System.Net.Http“ und „System.Threading.Tasks“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-129">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> <span data-ttu-id="e4eb1-130">Weitere Informationen zu Aufgaben und zum Code, der während des Wartens auf eine Aufgabe ausgeführt wird, finden Sie unter [Asynchrone Programmierung mit async und await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="e4eb1-130">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="e4eb1-131">Ein vollständiges Konsolenbeispiel, das ähnliche Elemente verwendet, finden Sie unter [Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="e4eb1-131">For a full console example that uses similar elements, see [Process asynchronous tasks as they complete (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>

## <a name="return-types"></a><span data-ttu-id="e4eb1-132">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="e4eb1-132">Return Types</span></span>
<span data-ttu-id="e4eb1-133">Eine asynchrone Methode kann folgende Rückgabetypen haben:</span><span class="sxs-lookup"><span data-stu-id="e4eb1-133">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="e4eb1-134">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="e4eb1-134">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="e4eb1-135">Von den `async void`-Methoden wird außer für Code für Ereignishandler allgemein abgeraten, da aufrufende Funktionen für diese Methoden `await` nicht verwenden können und einen anderen Mechanismus implementieren müssen, um den erfolgreichen Abschluss oder Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-135">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="e4eb1-136">Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-136">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="e4eb1-137">Der Typ `System.Threading.Tasks.ValueTask<TResult>` ist eine solche Implementierung.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-137">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="e4eb1-138">Er ist verfügbar, wenn Sie das NuGet-Paket `System.Threading.Tasks.Extensions` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-138">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span>

<span data-ttu-id="e4eb1-139">Mit der asynchronen Methode können keine [in](./in-parameter-modifier.md)-, [ref](./ref.md)- oder [out](./out-parameter-modifier.md)-Parameter deklariert werden, und sie kann auch keinen [Verweisrückgabewert](../../programming-guide/classes-and-structs/ref-returns.md) aufweisen, es können mit ihr jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-139">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>

<span data-ttu-id="e4eb1-140">`Task<TResult>` wird als Rückgabetyp einer Async-Methode angegeben, wenn mit der [return](./return.md)-Anweisung der Methode ein Operand vom Typ `TResult` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-140">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="e4eb1-141">`Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-141">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="e4eb1-142">Das bedeutet, dass ein Aufruf der Methode einen `Task` zurückgibt. Wenn der `Task` aber abgeschlossen ist, wird jeder `await`-Ausdruck, der auf den `Task` wartet, als `void` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-142">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>

<span data-ttu-id="e4eb1-143">Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, die diesen Rückgabetyp erfordern.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-143">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="e4eb1-144">Der Aufrufer einer Async-Methode, die `void` zurückgibt, kann auf ihn nicht warten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-144">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="e4eb1-145">Ab C# 7.0 wird ein anderer Typ zurückgegeben, üblicherweise ein Werttyp, der über eine `GetAwaiter`-Methode verfügt, um Speicherzuteilungen in Codeabschnitten zu minimieren, die für die Leistung entscheidend sind.</span><span class="sxs-lookup"><span data-stu-id="e4eb1-145">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span>

<span data-ttu-id="e4eb1-146">Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="e4eb1-146">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4eb1-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4eb1-147">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="e4eb1-148">await</span><span class="sxs-lookup"><span data-stu-id="e4eb1-148">await</span></span>](../operators/await.md)
- [<span data-ttu-id="e4eb1-149">Asynchrone Programmierung mit async und await</span><span class="sxs-lookup"><span data-stu-id="e4eb1-149">Asynchronous programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="e4eb1-150">Verarbeiten asynchroner Aufgaben nach Abschluss</span><span class="sxs-lookup"><span data-stu-id="e4eb1-150">Process asynchronous tasks as they complete</span></span>](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
