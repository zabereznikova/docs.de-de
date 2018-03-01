---
title: async (C#-Referenz)
ms.date: 05/22/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4a89736822342a9d9a24db6d43435f9795b81b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="async-c-reference"></a><span data-ttu-id="a62f1-102">async (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a62f1-102">async (C# Reference)</span></span>
<span data-ttu-id="a62f1-103">Mit dem `async`-Modifizierer können Sie angeben, dass eine Methode, ein [Lambdaausdruck](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) oder eine [anonyme Methode](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) asynchron ist.</span><span class="sxs-lookup"><span data-stu-id="a62f1-103">Use the `async` modifier to specify that a method, [lambda expression](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md), or [anonymous method](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) is asynchronous.</span></span> <span data-ttu-id="a62f1-104">Wenn Sie diesen Modifizierer auf Methoden oder Ausdrücke anwenden, wird dies als *asynchrone Methode* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a62f1-104">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="a62f1-105">Im folgenden Beispiel wird eine asynchrone Methode mit dem Namen `ExampleMethodAsync` definiert:</span><span class="sxs-lookup"><span data-stu-id="a62f1-105">The following example defines an async method named `ExampleMethodAsync`:</span></span> 
  
```csharp  
public async Task<int> ExampleMethodAsync()  
{  
    // . . . .  
}  
```  
 
<span data-ttu-id="a62f1-106">Wenn Sie mit der asynchronen Programmierung noch nicht vertraut sind oder nicht wissen, wie eine asynchrone Methode das `await`-Schlüsselwort verwendet, um Aufgaben mit potenziell langer Laufzeit auszuführen, ohne den Thread des Aufrufers zu blockieren, können Sie die Einführung unter [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md) lesen.</span><span class="sxs-lookup"><span data-stu-id="a62f1-106">If you're new to asynchronous programming or do not understand how an async method uses the `await` keyword to do potentially long-running work without blocking the caller’s thread, read the introduction in [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a62f1-107">Der folgende Code befindet sich in einer asynchronen Methode und ruft die <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>-Methode auf:</span><span class="sxs-lookup"><span data-stu-id="a62f1-107">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span> 
  
```csharp  
string contents = await httpClient.GetStringAsync(requestUrl);  
```  
  
<span data-ttu-id="a62f1-108">Eine asynchrone Methode wird bis zum ersten `await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a62f1-108">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="a62f1-109">In der Zwischenzeit wird die Steuerung an den Aufrufer der Methode zurückgegeben, wie das Beispiel in nächsten Thema zeigt.</span><span class="sxs-lookup"><span data-stu-id="a62f1-109">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>  
  
<span data-ttu-id="a62f1-110">Wenn die Methode, die mit dem `async`-Schlüsselwort geändert wird, keinen `await`-Ausdruck oder keine await-Anweisung enthält, wird die Methode synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a62f1-110">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="a62f1-111">Mit einer Compilerwarnung werden Sie auf alle asynchronen Methoden hingewiesen, die keine `await`-Anweisungen enthalten, da dies möglicherweise auf einen Fehler hindeutet.</span><span class="sxs-lookup"><span data-stu-id="a62f1-111">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="a62f1-112">Siehe [Compilerwarnung (Stufe 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="a62f1-112">See [Compiler Warning (level 1) CS4014](../../../csharp/language-reference/compiler-messages/cs4014.md).</span></span>  
  
 <span data-ttu-id="a62f1-113">Das `async`-Schlüsselwort ist insofern kontextabhängig, dass es nur dann ein Schlüsselwort ist, wenn mit ihm eine Methode, ein Lambda-Ausdruck oder eine anonyme Methode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="a62f1-113">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="a62f1-114">In allen anderen Kontexten wird es als Bezeichner interpretiert.</span><span class="sxs-lookup"><span data-stu-id="a62f1-114">In all other contexts, it's interpreted as an identifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a62f1-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a62f1-115">Example</span></span>  
<span data-ttu-id="a62f1-116">Im folgenden Beispiel werden die Struktur und Ablaufsteuerung zwischen einem asynchronen Ereignishandler, `StartButton_Click`, und einer asynchronen Methode, `ExampleMethodAsync`, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a62f1-116">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="a62f1-117">Das Ergebnis der asynchronen Methode ist die Anzahl von Zeichen einer Webseite.</span><span class="sxs-lookup"><span data-stu-id="a62f1-117">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="a62f1-118">Der Code ist für eine Windows Presentation Foundation (WPF)- oder Windows Store-Anwendung geeignet, die Sie in Visual Studio erstellen. Informationen zum Einrichten der Anwendung finden Sie in den Codekommentaren.</span><span class="sxs-lookup"><span data-stu-id="a62f1-118">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>  

<span data-ttu-id="a62f1-119">Sie können diesen Code in Visual Studio als Windows Presentation Foundation (WPF)-App oder Windows Store-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="a62f1-119">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="a62f1-120">Sie benötigen ein Schaltflächen-Steuerelement mit dem Namen `StartButton` und ein Textfeldsteuerelement mit dem Namen `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="a62f1-120">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="a62f1-121">Denken Sie daran, die Namen und den Handler so festzulegen, dass es in etwa wie folgt aussieht:</span><span class="sxs-lookup"><span data-stu-id="a62f1-121">Remember to set the names and handler so that you have something like this:</span></span>  

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"  
        Click="StartButton_Click" Name="StartButton"/>  
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"   
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>  
```
  
<span data-ttu-id="a62f1-122">So führen Sie den Code als WPF-App aus:</span><span class="sxs-lookup"><span data-stu-id="a62f1-122">To run the code as a WPF app:</span></span>  

- <span data-ttu-id="a62f1-123">Fügen Sie diesen Code in die `MainWindow`-Klasse in „MainWindow.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="a62f1-123">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>  
- <span data-ttu-id="a62f1-124">Fügen Sie einen Verweis auf „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a62f1-124">Add a reference to System.Net.Http.</span></span>  
- <span data-ttu-id="a62f1-125">Fügen Sie eine `using`-Anweisung für „System.Net.Http“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a62f1-125">Add a `using` directive for System.Net.Http.</span></span>  
  
<span data-ttu-id="a62f1-126">So führen Sie den Code als Windows Store-App aus:</span><span class="sxs-lookup"><span data-stu-id="a62f1-126">To run the code as a Windows Store app:</span></span>  
- <span data-ttu-id="a62f1-127">Fügen Sie diesen Code in die `MainPage`-Klasse in „MainPage.xaml.cs“ ein.</span><span class="sxs-lookup"><span data-stu-id="a62f1-127">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>  
- <span data-ttu-id="a62f1-128">Fügen Sie using-Anweisungen für „System.Net.Http“ und „System.Threading.Tasks“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="a62f1-128">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>  
  
[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]
  
> [!IMPORTANT]
>  <span data-ttu-id="a62f1-129">Weitere Informationen zu Aufgaben und zum Code, der während des Wartens auf eine Aufgabe ausgeführt wird, finden Sie unter [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="a62f1-129">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="a62f1-130">Ein vollständiges Beispiel für WPF, das ähnliche Elemente verwendet, finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web durch Verwenden von Async und Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="a62f1-130">For a full WPF example that uses similar elements, see [Walkthrough: Accessing the Web by Using Async and Await](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
## <a name="return-types"></a><span data-ttu-id="a62f1-131">Rückgabetypen</span><span class="sxs-lookup"><span data-stu-id="a62f1-131">Return Types</span></span>  
<span data-ttu-id="a62f1-132">Eine asynchrone Methode kann folgende Rückgabetypen haben:</span><span class="sxs-lookup"><span data-stu-id="a62f1-132">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="a62f1-133">[void](../../../csharp/language-reference/keywords/void.md), der nur für Ereignishandler verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a62f1-133">[void](../../../csharp/language-reference/keywords/void.md), which should only be used for event handlers.</span></span>
- <span data-ttu-id="a62f1-134">Ab C# 7: Jeder Typ, der über eine zugängliche `GetAwaiter`-Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="a62f1-134">Starting with C# 7, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="a62f1-135">Der Typ `System.Threading.Tasks.ValueTask<TResult>` ist eine solche Implementierung.</span><span class="sxs-lookup"><span data-stu-id="a62f1-135">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="a62f1-136">Er ist verfügbar, wenn Sie das NuGet-Paket `System.Threading.Tasks.Extensions` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a62f1-136">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span> 

<span data-ttu-id="a62f1-137">Mit der asynchronen Methode können keine [ref](../../../csharp/language-reference/keywords/ref.md)- oder [out](../../../csharp/language-reference/keywords/out.md)-Parameter deklariert werden und sie kann auch keinen <!-- [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) -->Verweisrückgabewert aufweisen, es können mit ihr jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a62f1-137">The async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters, nor can it have a <!-- [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) -->reference return value, but it can call methods that have such parameters.</span></span>  
  
<span data-ttu-id="a62f1-138">`Task<TResult>` wird als Rückgabetyp einer Async-Methode angegeben, wenn mit der [return](../../../csharp/language-reference/keywords/return.md)-Anweisung der Methode ein Operand vom Typ `TResult` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a62f1-138">You specify `Task<TResult>` as the return type of an async method if the [return](../../../csharp/language-reference/keywords/return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="a62f1-139">`Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a62f1-139">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="a62f1-140">Das bedeutet, dass ein Aufruf der Methode einen `Task` zurückgibt. Wenn der `Task` aber abgeschlossen ist, wird jeder `await`-Ausdruck, der auf den `Task` wartet, als `void` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a62f1-140">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>  
  
<span data-ttu-id="a62f1-141">Der Rückgabetyp `void` wird hauptsächlich zum Definieren von Ereignishandlern verwendet, die diesen Rückgabetyp erfordern.</span><span class="sxs-lookup"><span data-stu-id="a62f1-141">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="a62f1-142">Der Aufrufer einer Async-Methode, die `void` zurückgibt, kann auf ihn nicht warten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="a62f1-142">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>  

<span data-ttu-id="a62f1-143">Ab C# 7 wird ein anderer Typ zurückgegeben, üblicherweise ein Werttyp, der über eine `GetAwaiter`-Methode verfügt, um Speicherreservierungen in Codeabschnitten zu minimieren, die für die Leistung entscheidend sind.</span><span class="sxs-lookup"><span data-stu-id="a62f1-143">Starting with C# 7, you return another type, typically a value type, that has a `GetAwaiter` method to miminize memory allocations in performance-critical sections of code.</span></span> 

<span data-ttu-id="a62f1-144">Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="a62f1-144">For more information and examples, see [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62f1-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a62f1-145">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>  
 [<span data-ttu-id="a62f1-146">await</span><span class="sxs-lookup"><span data-stu-id="a62f1-146">await</span></span>](../../../csharp/language-reference/keywords/await.md)  
 [<span data-ttu-id="a62f1-147">Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="a62f1-147">Walkthrough: Accessing the Web by Using Async and Await</span></span>](../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="a62f1-148">Asynchrone Programmierung mit Async und Await</span><span class="sxs-lookup"><span data-stu-id="a62f1-148">Asynchronous Programming with async and await</span></span>](../../../csharp/programming-guide/concepts/async/index.md)
