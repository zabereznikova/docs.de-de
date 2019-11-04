---
title: Einführung in Ereignisse
description: Erfahren Sie in diesem Überblick etwas über Ereignisse in .NET Core und über Ziele beim Sprachentwurf für Ereignisse.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: b1fd2ebe2ae91b55c9179f280d8894f6b40ced9b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771921"
---
# <a name="introduction-to-events"></a><span data-ttu-id="c5b0a-103">Einführung in Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c5b0a-103">Introduction to Events</span></span>

[<span data-ttu-id="c5b0a-104">Vorherige</span><span class="sxs-lookup"><span data-stu-id="c5b0a-104">Previous</span></span>](delegates-patterns.md)

<span data-ttu-id="c5b0a-105">Ereignisse sind, wie Delegaten, ein Mechanismus mit *später Bindung*.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-105">Events are, like delegates, a *late binding* mechanism.</span></span> <span data-ttu-id="c5b0a-106">In der Tat werden Ereignisse basierend auf der Sprachunterstützung für Delegaten erstellt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-106">In fact, events are built on the language support for delegates.</span></span>

<span data-ttu-id="c5b0a-107">Ereignisse sind eine Möglichkeit für ein Objekt (für alle interessierten Komponenten im System) weiterzugeben, dass etwas passiert ist.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-107">Events are a way for an object to broadcast (to all interested components in the system) that something has happened.</span></span> <span data-ttu-id="c5b0a-108">Jede andere Komponente kann das Ereignis abonnieren, und benachrichtigt werden, wenn ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-108">Any other component can subscribe to the event, and be notified when an event is raised.</span></span>

<span data-ttu-id="c5b0a-109">Sie haben wahrscheinlich Ereignisse in einigen ihrer Programmierungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-109">You've probably used events in some of your programming.</span></span> <span data-ttu-id="c5b0a-110">Viele grafische Systeme verfügen über ein Ereignismodell, um über Benutzerinteraktion zu berichten.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-110">Many graphical systems have an event model to report user interaction.</span></span> <span data-ttu-id="c5b0a-111">Diese Ereignisse berichten über die Mausbewegung, das Betätigen der Schaltflächen und ähnliche Interaktionen.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-111">These events would report mouse movement, button presses and similar interactions.</span></span> <span data-ttu-id="c5b0a-112">Dies ist eines der am häufigsten verwendeten, aber sicherlich nicht das einzige Szenario, in dem Ereignisse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-112">That's one of the most common, but certainly not the only scenario where events are used.</span></span>

<span data-ttu-id="c5b0a-113">Sie können Ereignisse, die für Ihre Klassen ausgelöst werden sollen, definieren.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-113">You can define events that should be raised for your classes.</span></span> <span data-ttu-id="c5b0a-114">Ein wichtiger Aspekt bei der Arbeit mit Ereignissen ist, dass es möglicherweise kein registriertes Objekt für ein bestimmtes Ereignis gibt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-114">One important consideration when working with events is that there may not be any object registered for a particular event.</span></span> <span data-ttu-id="c5b0a-115">Sie müssen Ihren Code so schreiben, damit er keine Ereignisse auslöst, wenn keine Listener konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-115">You must write your code so that it does not raise events when no listeners are configured.</span></span>

<span data-ttu-id="c5b0a-116">Das Abonnieren eines Ereignisses erstellt auch eine Kopplung zwischen zwei Objekten (die Ereignisquelle und die Ereignissenke).</span><span class="sxs-lookup"><span data-stu-id="c5b0a-116">Subscribing to an event also creates a coupling between two objects (the event source, and the event sink).</span></span> <span data-ttu-id="c5b0a-117">Sie müssen sicherstellen, dass sich die Ereignissenke von der Ereignisquelle abmeldet, wenn Sie nicht mehr an Ereignissen interessiert ist.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-117">You need to ensure that the event sink unsubscribes from the event source when no longer interested in events.</span></span>

## <a name="design-goals-for-event-support"></a><span data-ttu-id="c5b0a-118">Entwurfsziele für die Ereignisunterstützung</span><span class="sxs-lookup"><span data-stu-id="c5b0a-118">Design Goals for Event Support</span></span>

<span data-ttu-id="c5b0a-119">Der Sprachentwurf für Ereignisse ist auf diese Ziele ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-119">The language design for events targets these goals.</span></span>

<span data-ttu-id="c5b0a-120">Aktivieren Sie zunächst eine sehr geringe Kopplung zwischen der Ereignisquelle und -senke.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-120">First, enable very minimal coupling between an event source and an event sink.</span></span> <span data-ttu-id="c5b0a-121">Diese beiden Komponenten können nicht von derselben Organisation geschrieben werden und werden möglicherweise sogar auf völlig unterschiedliche Zeitpläne aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-121">These two components may not be written by the same organization, and may even be updated on totally different schedules.</span></span>

<span data-ttu-id="c5b0a-122">Zweitens sollte es sehr einfach sein, ein Ereignis zu abonnieren, und sich von demselben Ereignis abzumelden.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-122">Secondly, it should be very simple to subscribe to an event, and to unsubscribe from that same event.</span></span>

<span data-ttu-id="c5b0a-123">Und schließlich sollten Ereignisquellen mehrere Ereignisabonnenten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-123">And finally, event sources should support multiple event subscribers.</span></span> <span data-ttu-id="c5b0a-124">Es sollte auch unterstützen, dass es keine angefügten Ereignisabonnenten gibt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-124">It should also support having no event subscribers attached.</span></span>

<span data-ttu-id="c5b0a-125">Sie sehen, dass die Ziele für Ereignisse, den Zielen für Delegaten sehr ähnlich sind.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-125">You can see that the goals for events are very similar to the goals for delegates.</span></span>
<span data-ttu-id="c5b0a-126">Deshalb basiert die Sprachunterstützung für Ereignisse auf der Sprachunterstützung für Delegaten.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-126">That's why the event language support is built on the delegate language support.</span></span>

## <a name="language-support-for-events"></a><span data-ttu-id="c5b0a-127">Sprachunterstützung für Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c5b0a-127">Language Support for Events</span></span>

<span data-ttu-id="c5b0a-128">Die Syntax zum Definieren von Ereignissen, und zum Abonnieren oder Abmelden von Ereignissen, ist eine Erweiterung der Syntax für Delegaten.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-128">The syntax for defining events, and subscribing or unsubscribing from events is an extension of the syntax for delegates.</span></span>

<span data-ttu-id="c5b0a-129">Zum Definieren eines Ereignisses verwenden Sie das `event`-Schlüsselwort:</span><span class="sxs-lookup"><span data-stu-id="c5b0a-129">To define an event you use the `event` keyword:</span></span>

```csharp
public event EventHandler<FileListArgs> Progress;
```

<span data-ttu-id="c5b0a-130">Der Typ des Ereignisses (`EventHandler<FileListArgs>` in diesem Beispiel) muss ein Delegattyp sein.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-130">The type of the event (`EventHandler<FileListArgs>` in this example) must be a delegate type.</span></span> <span data-ttu-id="c5b0a-131">Es gibt eine Reihe von Konventionen, die Sie befolgen sollten, wenn Sie ein Ereignis deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-131">There are a number of conventions that you should follow when declaring an event.</span></span> <span data-ttu-id="c5b0a-132">Normalerweise verfügt der Delegattyp des Ereignisses über einen „void“-Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-132">Typically, the event delegate type has a void return.</span></span>
<span data-ttu-id="c5b0a-133">Ereignisdeklarationen sollten ein Verb oder eine Verbalphrase sein.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-133">Event declarations should be a verb, or a verb phrase.</span></span>
<span data-ttu-id="c5b0a-134">Verwenden Sie die Vergangenheitsform, wenn das Ereignis meldet, dass etwas geschehen ist.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-134">Use past tense when the event reports something that has happened.</span></span> <span data-ttu-id="c5b0a-135">Verwenden Sie ein Gegenwartsverb (z.B. `Closing`) um etwas zu melden, das geschehen wird.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-135">Use a present tense verb (for example, `Closing`) to report something that is about to happen.</span></span> <span data-ttu-id="c5b0a-136">Häufig gibt die Verwendung der Gegenwartsform an, dass die Klasse eine Art der Anpassung des Verhaltens unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-136">Often, using present tense indicates that your class supports some kind of customization behavior.</span></span> <span data-ttu-id="c5b0a-137">Eines der häufigsten Szenarios ist die Unterstützung des Abbruchs.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-137">One of the most common scenarios is to support cancellation.</span></span> <span data-ttu-id="c5b0a-138">Angenommen, ein `Closing`-Ereignis enthält ein Argument, das angeben würde, ob der Schließvorgang fortgesetzt werden soll oder nicht.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-138">For example, a `Closing` event may include an argument that would indicate if the close operation should continue, or not.</span></span>  <span data-ttu-id="c5b0a-139">Andere Szenarios ermöglichen es Aufrufern, das Verhalten zu ändern, indem die Eigenschaften der Ereignisargumente aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-139">Other scenarios may enable callers to modify behavior by updating properties of the event arguments.</span></span> <span data-ttu-id="c5b0a-140">Sie können ein Ereignis auslösen, um eine vorgeschlagene nächste Aktion anzugeben, die einen Algorithmus auslösen wird.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-140">You may raise an event to indicate a proposed next action an algorithm will take.</span></span> <span data-ttu-id="c5b0a-141">Der Ereignishandler kann eine andere Aktion vorgeben, indem er die Eigenschaften des Ereignisarguments ändert.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-141">The event handler may mandate a different action by modifying  properties of the event argument.</span></span>

<span data-ttu-id="c5b0a-142">Wenn Sie das Ereignis auslösen möchten, rufen Sie mithilfe der Aufrufsyntax des Delegaten den Ereignishandler auf:</span><span class="sxs-lookup"><span data-stu-id="c5b0a-142">When you want to raise the event, you call the event handlers using the delegate invocation syntax:</span></span>

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

<span data-ttu-id="c5b0a-143">Wie im Abschnitt unter [Delegaten](delegates-patterns.md) beschrieben, macht der ?.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-143">As discussed in the section on [delegates](delegates-patterns.md), the ?.</span></span>
<span data-ttu-id="c5b0a-144">Operator es leicht, sicherzustellen, dass Sie nicht versuchen das Ereignis auszulösen, wenn keine Abonnenten für dieses Ereignis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-144">operator makes it easy to ensure that you do not attempt to raise the event when there are no subscribers to that event.</span></span>
 
<span data-ttu-id="c5b0a-145">Sie abonnieren ein Ereignis mithilfe des `+=`-Operators:</span><span class="sxs-lookup"><span data-stu-id="c5b0a-145">You subscribe to an event by using the `+=` operator:</span></span>

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) => 
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

<span data-ttu-id="c5b0a-146">Die Handlermethode ist in der Regel das Präfix „On“ gefolgt vom Ereignisnamen, wie oben gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-146">The handler method typically is the prefix 'On' followed by the event name, as shown above.</span></span>

<span data-ttu-id="c5b0a-147">Sie melden sich mithilfe des `-=`-Operators ab:</span><span class="sxs-lookup"><span data-stu-id="c5b0a-147">You unsubscribe using the `-=` operator:</span></span>

```csharp
fileLister.Progress -= onProgress;
```

<span data-ttu-id="c5b0a-148">Es ist wichtig, zu beachten, dass ich eine lokale Variable für den Ausdruck deklariert habe, der den Ereignishandler darstellt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-148">It's important to note that I declared a local variable for the expression that represents the event handler.</span></span> <span data-ttu-id="c5b0a-149">Damit wird sichergestellt, dass UNSUBSCRIBE den Handler entfernt.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-149">That ensures the unsubscribe removes the handler.</span></span>
<span data-ttu-id="c5b0a-150">Wenn Sie stattdessen den Text des Lambdaausdrucks verwendet haben, versuchen Sie einen Handler, der nicht angefügt wurde und nichts tut, zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-150">If, instead, you used the body of the lambda expression, you are attempting to remove a handler that has never been attached, which does nothing.</span></span>

<span data-ttu-id="c5b0a-151">Im nächsten Artikel erfahren Sie mehr über das typische Ereignismuster und verschiedene Varianten dieses Beispiels.</span><span class="sxs-lookup"><span data-stu-id="c5b0a-151">In the next article, you'll learn more about typical event patterns, and different variations on this example.</span></span>

[<span data-ttu-id="c5b0a-152">Nächste</span><span class="sxs-lookup"><span data-stu-id="c5b0a-152">Next</span></span>](event-pattern.md)
