---
title: Das aktualisierte .NET Core-Ereignismuster
description: "Erfahren Sie, wie das .NET Core-Ereignismuster die Flexibilität mit Abwärtskompabilität erhöht und wie Sie sichere Ereignisverarbeitung mit asynchronen Abonnenten implementieren können."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: cf69cbe0a7adbd274d1cb9e9544dda77d9fa1740
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="4001b-104">Das aktualisierte .NET Core-Ereignismuster</span><span class="sxs-lookup"><span data-stu-id="4001b-104">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="4001b-105">Vorherige</span><span class="sxs-lookup"><span data-stu-id="4001b-105">Previous</span></span>](event-pattern.md)

<span data-ttu-id="4001b-106">Im vorherigen Artikel wurden die am häufigsten verwendeten Ereignismuster erläutert.</span><span class="sxs-lookup"><span data-stu-id="4001b-106">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="4001b-107">.NET Core ist ein lockereres Muster.</span><span class="sxs-lookup"><span data-stu-id="4001b-107">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="4001b-108">Die `EventHandler<TEventArgs>`-Definition hat in dieser Version nicht länger die Einschränkung, dass `TEventArgs` eine von `System.EventArgs` abgeleitete Klasse sein muss.</span><span class="sxs-lookup"><span data-stu-id="4001b-108">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="4001b-109">Dies erhöht die Flexibilität für Sie und ist abwärtskompatibel.</span><span class="sxs-lookup"><span data-stu-id="4001b-109">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="4001b-110">Beginnen wir mit der Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="4001b-110">Let's start with the flexibility.</span></span> <span data-ttu-id="4001b-111">Die System.EventArgs-Klasse leitet eine Methode ein: `MemberwiseClone()`, die eine flache Kopie des Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="4001b-111">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="4001b-112">Diese Methode muss Reflektion verwenden, um ihre Funktionalität für jede von `EventArgs` abgeleitete Klasse zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4001b-112">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="4001b-113">Diese Funktionalität lässt sich in einer bestimmten abgeleiteten Klasse einfacher erstellen.</span><span class="sxs-lookup"><span data-stu-id="4001b-113">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="4001b-114">Das bedeutet, dass das Ableiten von System.EventArgs eine Einschränkung ist, die Ihre Entwürfe beschränkt, aber keine zusätzlichen Vorteile bietet.</span><span class="sxs-lookup"><span data-stu-id="4001b-114">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="4001b-115">Tatsächlich können Sie die Definitionen von `FileFoundArgs` und `SearchDirectoryArgs` ändern, sodass sie nicht von `EventArgs` abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4001b-115">In fact, you can changes the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="4001b-116">Das Programm funktioniert genauso.</span><span class="sxs-lookup"><span data-stu-id="4001b-116">The program will work exactly the same.</span></span>

<span data-ttu-id="4001b-117">Sie könnten auch `SearchDirectoryArgs` in eine Struktur ändern, wenn Sie eine weitere Änderung vornehmen:</span><span class="sxs-lookup"><span data-stu-id="4001b-117">You could also change the `SearchDirectoryArgs` to a struct, if you also make one more change:</span></span>

```csharp  
internal struct SearchDirectoryArgs  
{  
    internal string CurrentSearchDirectory { get; }  
    internal int TotalDirs { get; }  
    internal int CompletedDirs { get; }  
    
    internal SearchDirectoryArgs(string dir, int totalDirs, 
        int completedDirs) : this()  
    {  
        CurrentSearchDirectory = dir;  
        TotalDirs = totalDirs;  
        CompletedDirs = completedDirs;  
    }  
}  
```   

<span data-ttu-id="4001b-118">Die zusätzliche Änderung besteht darin, den Standardkonstruktor aufzurufen, bevor der Konstruktor eingegeben wird, der alle Felder initialisiert.</span><span class="sxs-lookup"><span data-stu-id="4001b-118">The additional change is to call the default constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="4001b-119">Ohne diesen Zusatz würden die Regeln von C# berichten, dass auf die Eigenschaften zugegriffen wird, bevor sie zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="4001b-119">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="4001b-120">Ändern Sie `FileFoundArgs` nicht von einer Klasse (Verweistyp) in eine Struktur (Werttyp).</span><span class="sxs-lookup"><span data-stu-id="4001b-120">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="4001b-121">Das Protokoll zur Behandlung von Abbrüchen erfordert, dass die Ereignisargumente als Verweis übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4001b-121">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="4001b-122">Wenn Sie diese Änderung vorgenommen hätten, könnte die Dateisuche-Klasse niemals Änderungen beobachten, die von einem der Ereignisabonnenten vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="4001b-122">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="4001b-123">Für jeden Abonnenten würde eine neue Kopie der Struktur verwendet werden, und diese Kopie würde sich von derjenigen unterscheiden, die vom Dateisuche-Objekt gesehen wird.</span><span class="sxs-lookup"><span data-stu-id="4001b-123">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="4001b-124">Schauen wir uns nun an, wie diese Änderung abwärtskompatibel gemacht werden kann.</span><span class="sxs-lookup"><span data-stu-id="4001b-124">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="4001b-125">Das Entfernen der Einschränkung wirkt sich nicht auf vorhandenen Code aus.</span><span class="sxs-lookup"><span data-stu-id="4001b-125">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="4001b-126">Alle vorhandenen Ereignisargumenttypen werden immer noch von `System.EventArgs` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="4001b-126">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="4001b-127">Abwärtskompatibilität ist ein wichtiger Grund, weshalb sie weiterhin von `System.EventArgs` ableiten.</span><span class="sxs-lookup"><span data-stu-id="4001b-127">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="4001b-128">Vorhandene Ereignisabonnenten werden Abonnenten für ein Ereignis, die dem klassische Muster folgen.</span><span class="sxs-lookup"><span data-stu-id="4001b-128">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="4001b-129">Nach derselben Logik würden alle erstellten Ereignisargumenttypen keine Abonnenten in vorhandenen Codebases haben.</span><span class="sxs-lookup"><span data-stu-id="4001b-129">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="4001b-130">Neue Ereignistypen, die nicht von `System.EventArgs` abgeleitet sind, unterbrechen diese Codebases nicht.</span><span class="sxs-lookup"><span data-stu-id="4001b-130">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="4001b-131">Ereignisse mit asynchronen Abonnenten</span><span class="sxs-lookup"><span data-stu-id="4001b-131">Events with Async subscribers</span></span>

<span data-ttu-id="4001b-132">Das letzte, in diesem Artikel behandelte Muster ist die richtige Schreibweise von Ereignisabonnenten, die asynchronen Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4001b-132">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="4001b-133">Informationen hierzu finden Sie im Artikel zu [Async und Await](async.md).</span><span class="sxs-lookup"><span data-stu-id="4001b-133">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="4001b-134">Asynchrone Methoden können einen Rückgabetyp „Void“ haben, aber davon ist dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="4001b-134">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="4001b-135">Wenn Ihr Ereignisabonnent eine asynchrone Methode aufruft, haben Sie keine Wahl, außer eine `async void`-Methode zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4001b-135">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="4001b-136">Sie wird von der Signatur des Ereignishandlers benötigt.</span><span class="sxs-lookup"><span data-stu-id="4001b-136">The event handler signature requires it.</span></span>

<span data-ttu-id="4001b-137">Sie müssen diesen entgegengesetzten Leitfaden abstimmen.</span><span class="sxs-lookup"><span data-stu-id="4001b-137">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="4001b-138">Sie müssen irgendwie eine sichere `async void`-Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="4001b-138">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="4001b-139">Die Grundlagen des Musters, das Sie implementieren müssen, finden Sie untenan:</span><span class="sxs-lookup"><span data-stu-id="4001b-139">The basics of the pattern you need to implement are below:</span></span>

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try 
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

<span data-ttu-id="4001b-140">Beachten Sie, dass der Handler als ein asynchroner Handler markiert ist.</span><span class="sxs-lookup"><span data-stu-id="4001b-140">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="4001b-141">Da er einem Ereignishandler-Delegattyp zugewiesen wurde, weist er den Rückgabetyp „Void“ auf.</span><span class="sxs-lookup"><span data-stu-id="4001b-141">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="4001b-142">Das bedeutet, dass Sie dem im Handler angezeigten Muster folgen müssen und nicht zulassen dürfen, dass Ausnahmen ausgelöst werden, die nicht zum Kontext des asynchronen Handlers gehören.</span><span class="sxs-lookup"><span data-stu-id="4001b-142">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="4001b-143">Da der Handler keine Aufgabe zurückgibt, gibt es keine Aufgabe, die einen Fehler berichten kann, indem sie in den Fehlerzustand tritt.</span><span class="sxs-lookup"><span data-stu-id="4001b-143">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="4001b-144">Da die Methode asynchron ist, kann sie die Ausnahme nicht einfach auslösen.</span><span class="sxs-lookup"><span data-stu-id="4001b-144">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="4001b-145">(Die aufrufende Methode wird weiterhin ausgeführt, weil sie `async` (asynchron) ist.) Das tatsächliche Laufzeitverhalten wird für unterschiedliche Umgebungen unterschiedlich definiert.</span><span class="sxs-lookup"><span data-stu-id="4001b-145">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="4001b-146">Sie kann den Thread oder das Programm beenden oder das Programm in einem unbestimmten Zustand belassen.</span><span class="sxs-lookup"><span data-stu-id="4001b-146">It may terminate the thread, it may terminate the program, or it may leave the program in an undetermined state.</span></span> <span data-ttu-id="4001b-147">Keine dieser Verhaltensweisen erzielt gute Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="4001b-147">None of those are good outcomes.</span></span>

<span data-ttu-id="4001b-148">Deshalb sollten Sie die Await-Anweisung für die asynchrone Aufgabe in Ihrem eigenen try-Block umschließen.</span><span class="sxs-lookup"><span data-stu-id="4001b-148">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="4001b-149">Wenn sie einen fehlerhaften Vorgang verursacht, können Sie den Fehler protokollieren.</span><span class="sxs-lookup"><span data-stu-id="4001b-149">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="4001b-150">Wenn es sich um einen Fehler handelt, aus dem sich Ihre Anwendung nicht wiederherstellen lässt, können Sie das Programm schnell und problemlos beenden.</span><span class="sxs-lookup"><span data-stu-id="4001b-150">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="4001b-151">Dies sind die wichtigsten Updates für das .NET-Ereignismuster.</span><span class="sxs-lookup"><span data-stu-id="4001b-151">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="4001b-152">In den Bibliotheken, mit denen Sie arbeiten, Sie zahlreiche Beispiele für die früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="4001b-152">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="4001b-153">Allerdings sollten Sie auch die neuesten Muster kennenlernen.</span><span class="sxs-lookup"><span data-stu-id="4001b-153">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="4001b-154">Der nächste Artikel dieser Reihe hilft Ihnen dabei, zwischen der Verwendung von `delegates` und `events` in ihren Entwürfen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4001b-154">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="4001b-155">Da sich beide Konzepte ähneln, wird Ihnen dieser Artikel helfen, die beste Entscheidung für Ihre Programme zu treffen.</span><span class="sxs-lookup"><span data-stu-id="4001b-155">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="4001b-156">Nächste</span><span class="sxs-lookup"><span data-stu-id="4001b-156">Next</span></span>](distinguish-delegates-events.md)
