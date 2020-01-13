---
title: async – C#-Referenz
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 3d3f045eed3bad3624ed4994aebb862c52a4e196
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713786"
---
# <a name="async-c-reference"></a><span data-ttu-id="ec3b7-102">async (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ec3b7-102">async (C# Reference)</span></span>

<span data-ttu-id="ec3b7-103">Mit dem `async`-Modifizierer können Sie angeben, dass eine Methode, ein [Lambdaausdruck](../../programming-guide/statements-expressions-operators/lambda-expressions.md) oder eine [anonyme Methode](../operators/delegate-operator.md) asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-103">Use the `async` modifier to specify that a method, [lambda expression](../../programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="ec3b7-104">Wenn Sie diesen Modifizierer auf Methoden oder Ausdrücke anwenden, wird dies als *asynchrone Methode* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="ec3b7-105">Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `ExampleMethodAsync` definiert:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-105">The following example defines an async method named `ExampleMethodAsync`:</span></span>
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  

<span data-ttu-id="ec3b7-106">Wenn Sie mit der asynchronen Programmierung noch nicht vertraut sind oder nicht wissen, wie eine Async-Methode den [Operator `await`](../operators/await.md) verwendet, um Aufgaben mit potenziell langer Laufzeit auszuführen, ohne den Thread des Aufrufers zu blockieren, können Sie sich die Einführung unter [Asynchrone Programmierung mit „async“ und „await“](../../programming-guide/concepts/async/index.md) durchlesen.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-106">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="ec3b7-107">Der folgende Code befindet sich in einer asynchronen Methode und ruft die <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="ec3b7-108">Eine asynchrone Methode wird bis zum ersten `await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="ec3b7-109">In der Zwischenzeit wird die Steuerung an den Aufrufer der Methode zurückgegeben, wie das Beispiel in nächsten Thema zeigt.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="ec3b7-110">Wenn die Methode, die mit dem `async`-Schlüsselwort geändert wird, keinen `await`-Ausdruck oder keine await-Anweisung enthält, wird die Methode synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="ec3b7-111">Mit einer Compilerwarnung werden Sie auf alle asynchronen Methoden hingewiesen, die keine `await`-Anweisungen enthalten, da dies möglicherweise auf einen Fehler hindeutet.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="ec3b7-112">Siehe [Compilerwarnung (Stufe 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="ec3b7-112">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="ec3b7-113">Das `async`-Schlüsselwort ist insofern kontextabhängig, dass es nur dann ein Schlüsselwort ist, wenn mit ihm eine Methode, ein Lambda-Ausdruck oder eine anonyme Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="ec3b7-114">In allen anderen Kontexten wird es als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec3b7-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec3b7-115">Example</span></span>  
<span data-ttu-id="ec3b7-116">Im folgenden Beispiel werden die Struktur und Ablaufsteuerung zwischen einem asynchronen Ereignishandler, `StartButton_Click`, und einer asynchronen Methode, `ExampleMethodAsync`, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="ec3b7-117">Das Ergebnis der asynchronen Methode ist die Anzahl von Zeichen einer Webseite.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="ec3b7-118">Der Code ist für eine Windows Presentation Foundation (WPF)- oder Windows Store-Anwendung geeignet, die Sie in Visual Studio erstellen. Informationen zum Einrichten der Anwendung finden Sie in den Codekommentaren.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="ec3b7-119">Sie können diesen Code in Visual Studio als Windows Presentation Foundation (WPF)-App oder Windows Store-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="ec3b7-120">Sie benötigen ein Schaltflächen-Steuerelement mit dem Namen `StartButton` und ein Textfeldsteuerelement mit dem Namen `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="ec3b7-121">Denken Sie daran, die Namen und den Handler so festzulegen, dass es in etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="ec3b7-122">So führen Sie den Code als WPF-App aus:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="ec3b7-123">Fügen Sie diesen Code in die `MainWindow`-Klasse in „MainWindow.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="ec3b7-124">Fügen Sie einen Verweis auf „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="ec3b7-125">Fügen Sie eine `using`-Anweisung für „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="ec3b7-126">So führen Sie den Code als Windows Store-App aus:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-126">To run the code as a Windows Store app:</span></span>  

- <span data-ttu-id="ec3b7-127">Fügen Sie diesen Code in die `MainPage`-Klasse in „MainPage.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="ec3b7-128">Fügen Sie using-Anweisungen für „System.Net.Http“ und „System.Threading.Tasks“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
> <span data-ttu-id="ec3b7-129">Weitere Informationen zu Aufgaben und zum Code, der während des Wartens auf eine Aufgabe ausgeführt wird, finden Sie unter [Asynchrone Programmierung mit Async und Await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="ec3b7-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="ec3b7-130">Ein vollständiges WPF-Beispiel, das ähnliche Elemente verwendet, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="ec3b7-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="ec3b7-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="ec3b7-131">Return Types</span></span>  
<span data-ttu-id="ec3b7-132">Eine asynchrone Methode kann folgende Rückgabetypen haben:</span><span class="sxs-lookup"><span data-stu-id="ec3b7-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="ec3b7-133">[void](./void.md).</span><span class="sxs-lookup"><span data-stu-id="ec3b7-133">[void](./void.md).</span></span> <span data-ttu-id="ec3b7-134">Von den `async void`-Methoden wird außer für Code für Ereignishandler allgemein abgeraten, da aufrufende Funktionen für diese Methoden `await` nicht verwenden können und einen anderen Mechanismus implementieren müssen, um den erfolgreichen Abschluss oder Fehler zu melden.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-134">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="ec3b7-135">Ab C# 7.0: jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-135">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="ec3b7-136">Der Typ `System.Threading.Tasks.ValueTask<TResult>` ist eine solche Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-136">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="ec3b7-137">Er ist verfügbar, wenn Sie das NuGet-Paket `System.Threading.Tasks.Extensions` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-137">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="ec3b7-138">Mit der asynchronen Methode können keine [in](./in-parameter-modifier.md)-, [ref](./ref.md)- oder [out](./out-parameter-modifier.md)-Parameter deklariert werden, und sie kann auch keinen [Verweisrückgabewert](../../programming-guide/classes-and-structs/ref-returns.md) aufweisen, es können mit ihr jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-138">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="ec3b7-139">`Task<TResult>` wird als Rückgabetyp einer Async-Methode angegeben, wenn mit der [return](./return.md)-Anweisung der Methode ein Operand vom Typ `TResult` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-139">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="ec3b7-140">`Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-140">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="ec3b7-141">Das bedeutet, dass ein Aufruf der Methode einen `Task` zurückgibt. Wenn der `Task` aber abgeschlossen ist, wird jeder `await`-Ausdruck, der auf den `Task` wartet, als `void` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-141">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="ec3b7-142">Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, die diesen Rückgabetyp erfordern.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-142">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="ec3b7-143">Der Aufrufer einer Async-Methode, die `void` zurückgibt, kann auf ihn nicht warten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-143">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="ec3b7-144">Ab C# 7.0 wird ein anderer Typ zurückgegeben, üblicherweise ein Werttyp, der über eine `GetAwaiter`-Methode verfügt, um Speicherzuteilungen in Codeabschnitten zu minimieren, die für die Leistung entscheidend sind.</span><span class="sxs-lookup"><span data-stu-id="ec3b7-144">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="ec3b7-145">Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="ec3b7-145">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec3b7-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec3b7-146">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="ec3b7-147">await</span><span class="sxs-lookup"><span data-stu-id="ec3b7-147">await</span></span>](../operators/await.md)
- [<span data-ttu-id="ec3b7-148">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="ec3b7-148">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [<span data-ttu-id="ec3b7-149">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="ec3b7-149">Asynchronous Programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
