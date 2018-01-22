---
title: Standardereignismuster in .NET
description: "Erfahren Sie etwas über Ereignismuster in .NET und wie Sie standardmäßige Ereignisquellen erstellen und Standardereignisse in Ihrem Code abonnieren und verarbeiten können."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: ff36438ab02ae6822d7df8425a615aef2ddbf2f2
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="standard-net-event-patterns"></a><span data-ttu-id="a32c6-104">Standardereignismuster in .NET</span><span class="sxs-lookup"><span data-stu-id="a32c6-104">Standard .NET event patterns</span></span>

[<span data-ttu-id="a32c6-105">Vorherige</span><span class="sxs-lookup"><span data-stu-id="a32c6-105">Previous</span></span>](events-overview.md)

<span data-ttu-id="a32c6-106">.NET-Ereignisse folgen in der Regel einigen bekannten Mustern.</span><span class="sxs-lookup"><span data-stu-id="a32c6-106">.NET events generally follow a few known patterns.</span></span> <span data-ttu-id="a32c6-107">Standardisierung auf diese Muster bedeutet, dass Entwickler Kenntnisse über diese Standardmuster nutzen können, die auf ein beliebiges .NET Ereignisprogramm angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a32c6-107">Standardizing on these patterns means that developers can leverage knowledge of those standard patterns, which can be applied to any .NET event program.</span></span>

<span data-ttu-id="a32c6-108">Schauen wir uns diese Standardmuster an, sodass Sie über alle Kenntnisse verfügen, die Sie benötigen, um Standardereignisquellen zu erstellen und Standardereignisse in Ihrem Code zu abonnieren und zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a32c6-108">Let's go through these standard patterns so you will have all the knowledge you need to create standard event sources, and subscribe and process standard events in your code.</span></span>

## <a name="event-delegate-signatures"></a><span data-ttu-id="a32c6-109">Ereignisdelegatsignaturen</span><span class="sxs-lookup"><span data-stu-id="a32c6-109">Event Delegate Signatures</span></span>

<span data-ttu-id="a32c6-110">Die Standardsignatur für ein .NET-Ereignisdelegat lautet:</span><span class="sxs-lookup"><span data-stu-id="a32c6-110">The standard signature for a .NET event delegate is:</span></span>

```csharp
void OnEventRaised(object sender, EventArgs args);
```

<span data-ttu-id="a32c6-111">Der Rückgabetyp ist void.</span><span class="sxs-lookup"><span data-stu-id="a32c6-111">The return type is void.</span></span> <span data-ttu-id="a32c6-112">Ereignisse basieren auf Delegaten und sind Multicastdelegaten.</span><span class="sxs-lookup"><span data-stu-id="a32c6-112">Events are based on delegates and are multicast delegates.</span></span> <span data-ttu-id="a32c6-113">Dies unterstützt mehrere Abonnenten für jede Ereignisquelle.</span><span class="sxs-lookup"><span data-stu-id="a32c6-113">That supports multiple subscribers for any event source.</span></span> <span data-ttu-id="a32c6-114">Der einzelne Rückgabewert einer Methode wird nicht auf mehrere Ereignisabonnenten skaliert.</span><span class="sxs-lookup"><span data-stu-id="a32c6-114">The single return value from a method doesn't scale to multiple event subscribers.</span></span> <span data-ttu-id="a32c6-115">Welchen Rückgabewert findet die Ereignisquelle nach dem Auslösen eines Ereignisses vor?</span><span class="sxs-lookup"><span data-stu-id="a32c6-115">Which return value does the event source see after raising an event?</span></span> <span data-ttu-id="a32c6-116">In diesem Artikel sehen Sie später, wie Sie Ereignisprotokolle zur Unterstützung der Ereignisabonnenten, die Informationen an die Ereignisquelle senden, erstellen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-116">Later in this article you'll see how to create event protocols that support event subscribers that report information to the event source.</span></span>

<span data-ttu-id="a32c6-117">Die Argumentliste enthält zwei Argumente: Den Absender und die Ereignisargumente.</span><span class="sxs-lookup"><span data-stu-id="a32c6-117">The argument list contains two arguments: the sender, and the event arguments.</span></span> <span data-ttu-id="a32c6-118">Der Kompilierzeittyp von `sender` ist `System.Object`, obwohl Sie wahrscheinlich einen stärker abgeleiteten Typ kennen, die immer korrekt wäre.</span><span class="sxs-lookup"><span data-stu-id="a32c6-118">The compile time type of `sender` is `System.Object`, even though you likely know a more derived type that would always be correct.</span></span> <span data-ttu-id="a32c6-119">Verwenden Sie gemäß der Konvention `object`.</span><span class="sxs-lookup"><span data-stu-id="a32c6-119">By convention, use `object`.</span></span>

<span data-ttu-id="a32c6-120">Das zweite Argument ist in der Regel ein Typ, der von `System.EventArgs` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="a32c6-120">The second argument has typically been a type that is derived from `System.EventArgs`.</span></span> <span data-ttu-id="a32c6-121">(Im [nächsten Abschnitt](modern-events.md) werden Sie sehen, dass diese Konvention nicht mehr erzwungen wird.) Wenn der Ereignistyp keine zusätzlichen Argumente benötigt, werden Sie dennoch beide Argumente bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-121">(You'll see in the [next section](modern-events.md) that this convention is no longer enforced.) If your event type does not need any additional arguments, you will still provide both arguments.</span></span>
<span data-ttu-id="a32c6-122">Es gibt einen speziellen Wert, `EventArgs.Empty`, den Sie verwenden sollten, um anzugeben, dass Ihr Ereignis keine weiteren Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="a32c6-122">There is a special value, `EventArgs.Empty` that you should use to denote that your event does not contain any additional information.</span></span>

<span data-ttu-id="a32c6-123">Erstellen Sie eine Klasse, die Dateien in einem Verzeichnis oder einem seiner Unterverzeichnisse, die einem Muster folgen, auflistet.</span><span class="sxs-lookup"><span data-stu-id="a32c6-123">Let's build a class that lists files in a directory, or any of its subdirectories that follow a pattern.</span></span> <span data-ttu-id="a32c6-124">Diese Komponente löst ein Ereignis für jede gefundene Datei aus, die mit dem Muster übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a32c6-124">This component raises an event for each file found that matches the pattern.</span></span>

<span data-ttu-id="a32c6-125">Ein Ereignismodell bietet einige Vorteile beim Entwurf.</span><span class="sxs-lookup"><span data-stu-id="a32c6-125">Using an event model provides some design advantages.</span></span> <span data-ttu-id="a32c6-126">Sie können mehrere Ereignislistener erstellen, die verschiedene Aktionen ausführen, wenn eine gesuchte Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="a32c6-126">You can create multiple event listeners that perform different actions when a sought file is found.</span></span> <span data-ttu-id="a32c6-127">Das Kombinieren der verschiedenen Listener kann robustere Algorithmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-127">Combining the different listeners can create more robust algorithms.</span></span>

<span data-ttu-id="a32c6-128">Hier ist die erste Ereignisargumentdeklaration für die Suche nach einer gesuchten Datei:</span><span class="sxs-lookup"><span data-stu-id="a32c6-128">Here is the initial event argument declaration for finding a sought file:</span></span> 

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="a32c6-129">Obwohl dieser Typ wie ein kleiner, Nur-Daten-Typ aussieht, sollten Sie die Konvention einhalten und ihm einen Verweis (`class`)-Typ geben.</span><span class="sxs-lookup"><span data-stu-id="a32c6-129">Even though this type looks like a small, data-only type, you should follow the convention and make it a reference (`class`) type.</span></span> <span data-ttu-id="a32c6-130">Dies bedeutet, dass das Argumentobjekt als Verweis übergeben wird, und alle Updates der Daten von allen Abonnenten gesehen werden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-130">That means the argument object will be passed by reference, and any updates to the data will be viewed by all subscribers.</span></span> <span data-ttu-id="a32c6-131">Die erste Version ist ein unveränderliches Objekt.</span><span class="sxs-lookup"><span data-stu-id="a32c6-131">The first version is an immutable object.</span></span> <span data-ttu-id="a32c6-132">Sie sollten die Eigenschaften im Ereignisargumenttyp auf unveränderlich einstellen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-132">You should prefer to make the properties in your event argument type immutable.</span></span> <span data-ttu-id="a32c6-133">Auf diese Weise kann ein Abonnent die Werte nicht ändern, bevor ein anderer Abonnent sie sieht.</span><span class="sxs-lookup"><span data-stu-id="a32c6-133">That way, one subscriber cannot change the values before another subscriber sees them.</span></span> <span data-ttu-id="a32c6-134">(Es gibt Ausnahmen dafür, wie Sie unten sehen werden.)</span><span class="sxs-lookup"><span data-stu-id="a32c6-134">(There are exceptions to this, as you'll see below.)</span></span>  

<span data-ttu-id="a32c6-135">Als Nächstes müssen wir die Ereignisdeklaration in der FileSearcher-Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-135">Next, we need to create the event declaration in the FileSearcher class.</span></span> <span data-ttu-id="a32c6-136">Die Nutzung des `EventHandler<T>`-Typ bedeutet, dass Sie nicht noch eine Typdefinition erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-136">Leveraging the `EventHandler<T>` type means that you don't need to create yet another type definition.</span></span> <span data-ttu-id="a32c6-137">Sie verwenden einfach eine generische Spezialisierung.</span><span class="sxs-lookup"><span data-stu-id="a32c6-137">You simply use a generic specialization.</span></span>

<span data-ttu-id="a32c6-138">Füllen wir die FileSearcher-Klasse aus, um nach Dateien mit dem Muster zu suchen und das richtige Ereignis auszulösen, wenn eine Übereinstimmung gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="a32c6-138">Let's fill out the FileSearcher class to search for files that match a pattern, and raise the correct event when a match is discovered.</span></span>

```csharp
public class FileSearcher
{
    public event EventHandler<FileFoundArgs> FileFound;

    public void Search(string directory, string searchPattern)
    {
        foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
        {
            FileFound?.Invoke(this, new FileFoundArgs(file));
        }
    }
}
```

## <a name="definining-and-raising-field-like-events"></a><span data-ttu-id="a32c6-139">Definieren und Auslösen von feldähnlichen Ereignissen</span><span class="sxs-lookup"><span data-stu-id="a32c6-139">Definining and Raising Field-Like Events</span></span>

<span data-ttu-id="a32c6-140">Die einfachste Möglichkeit, Ihrer Klasse ein Ereignis hinzuzufügen, ist das Deklarieren des Ereignisses als öffentliches Feld, wie im obigen Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a32c6-140">The simplest way to add an event to your class is to declare that event as a public field, as in the above example:</span></span>

```csharp
public event EventHandler<FileFoundArgs> FileFound;
```

<span data-ttu-id="a32c6-141">Dies scheint ein öffentliches Feld zu deklarieren, das als eine Vorgehensweise eines ungültigen Objekts erscheinen würde.</span><span class="sxs-lookup"><span data-stu-id="a32c6-141">This looks like it's declaring a public field, which would appear to be bad object oriented practice.</span></span> <span data-ttu-id="a32c6-142">Sie möchten den Datenzugriff über Eigenschaften oder Methoden schützen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-142">You want to protect data access through properties, or methods.</span></span> <span data-ttu-id="a32c6-143">Während dies anscheinend kein empfehlenswertes Verfahren ist, erstellt der vom Compiler generierte Code Wrapper, damit auf die Ereignisobjekte nur auf sichere Weise zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a32c6-143">While this make look like a bad practice, the code generated by the compiler does create wrappers so that the event objects can only be accessed in safe ways.</span></span> <span data-ttu-id="a32c6-144">Die einzig verfügbaren Vorgänge für ein feldähnliches Ereignis sind das Hinzufügen von Handlern:</span><span class="sxs-lookup"><span data-stu-id="a32c6-144">The only operations available on a field-like event are add handler:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);
lister.FileFound += onFileFound;
```

<span data-ttu-id="a32c6-145">und das Entfernen von Handlern:</span><span class="sxs-lookup"><span data-stu-id="a32c6-145">and remove handler:</span></span>

```csharp
lister.FileFound -= onFileFound;
```

<span data-ttu-id="a32c6-146">Beachten Sie, dass eine lokale Variable für den Handler vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a32c6-146">Note that there's a local variable for the handler.</span></span> <span data-ttu-id="a32c6-147">Wenn Sie den Text des Lambda-Ausdrucks verwenden, würde das Entfernen nicht ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="a32c6-147">If you used the body of the lambda, the remove would not work correctly.</span></span> <span data-ttu-id="a32c6-148">Es wäre eine andere Instanz des Delegaten, und es würde stillschweigend nichts geschehen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-148">It would be a different instance of the delegate, and silently do nothing.</span></span>

<span data-ttu-id="a32c6-149">Code außerhalb der Klasse kann das Ereignis nicht auslösen, noch kann er andere Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-149">Code outside the class cannot raise the event, nor can it perform any other operations.</span></span>

## <a name="returning-values-from-event-subscribers"></a><span data-ttu-id="a32c6-150">Rückgabe von Werten aus Ereignisabonnenten</span><span class="sxs-lookup"><span data-stu-id="a32c6-150">Returning Values from Event Subscribers</span></span>

<span data-ttu-id="a32c6-151">Ihre einfache Version funktioniert einwandfrei.</span><span class="sxs-lookup"><span data-stu-id="a32c6-151">Your simple version is working fine.</span></span> <span data-ttu-id="a32c6-152">Fügen wir eine weitere Funktion hinzu: Abbruch.</span><span class="sxs-lookup"><span data-stu-id="a32c6-152">Let's add another feature: Cancellation.</span></span>

<span data-ttu-id="a32c6-153">Beim Auslösen des gefunden Ereignisses sollten Listener die weitere Verarbeitung beenden können, wenn diese Datei die letzte gesuchte Datei ist.</span><span class="sxs-lookup"><span data-stu-id="a32c6-153">When you raise the found event, listeners should be able to stop further processing, if this file is that last one sought.</span></span>

<span data-ttu-id="a32c6-154">Die Ereignishandler geben keinen Wert zurück. Daher müssen Sie dies auf andere Weise kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="a32c6-154">The event handlers do not return a value, so you need to communicate that in another way.</span></span> <span data-ttu-id="a32c6-155">Das Standardereignismuster verwendet das EventArgs-Objekt, um Felder einzuschließen, die Ereignisabonnenten zum Kommunizieren von „Abbrechen“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-155">The standard event pattern uses the EventArgs object to include fields that event subscribers can use to communicate cancel.</span></span>

<span data-ttu-id="a32c6-156">Es gibt zwei unterschiedliche Muster, die verwendet werden können, auf der Grundlage der Semantik des Vertrags „Abbrechen“.</span><span class="sxs-lookup"><span data-stu-id="a32c6-156">There are two different patterns that could be used, based on the semantics of the Cancel contract.</span></span> <span data-ttu-id="a32c6-157">In beiden Fällen werden Sie ein boolesches Feld zum EventArguments für das gefundene Dateiereignis hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-157">In both cases, you'll add a boolean field to the EventArguments for the found file event.</span></span> 

<span data-ttu-id="a32c6-158">Ein Muster ermöglicht jedem Abonnenten, den Vorgang abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-158">One pattern would allow any one subscriber to cancel the operation.</span></span>
<span data-ttu-id="a32c6-159">Für dieses Muster wird ein neues Feld mit `false` initialisiert.</span><span class="sxs-lookup"><span data-stu-id="a32c6-159">For this pattern, the new field is initialized to `false`.</span></span> <span data-ttu-id="a32c6-160">Jeder Abonnent kann es in `true` ändern.</span><span class="sxs-lookup"><span data-stu-id="a32c6-160">Any subscriber can change it to `true`.</span></span> <span data-ttu-id="a32c6-161">Nachdem alle Abonnenten das ausgelöste Ereignis gesehen haben, untersucht die Komponente FileSearcher den booleschen Wert und ergreift Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-161">After all subscribers have seen the event raised, the FileSearcher component examines the boolean value and takes action.</span></span>

<span data-ttu-id="a32c6-162">Das zweite Muster würde nur den Vorgang abbrechen, wenn alle Abonnenten den Vorgang abgebrochen haben möchten.</span><span class="sxs-lookup"><span data-stu-id="a32c6-162">The second pattern would only cancel the operation if all subscribers wanted the operation cancelled.</span></span> <span data-ttu-id="a32c6-163">In diesem Muster wird das neue Feld initialisiert, um anzugeben, dass der Vorgang abgebrochen werden soll, und jeder Abonnent kann dies ändern, um anzugeben, dass der Vorgang fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a32c6-163">In this pattern, the new field is initialized to indicate the operation should cancel, and any subscriber could change it to indicate the operation should continue.</span></span>
<span data-ttu-id="a32c6-164">Nachdem alle Abonnenten das ausgelöste Ereignis gesehen haben, untersucht die Komponente FileSearcher den booleschen Wert und ergreift Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-164">After all subscribers have seen the event raised, the FileSearcher component examines the boolean and takes action.</span></span> <span data-ttu-id="a32c6-165">Es gibt einen zusätzlichen Schritt in diesem Muster: Die Komponente muss wissen, ob jeder Abonnent das Ereignis gesehen hat.</span><span class="sxs-lookup"><span data-stu-id="a32c6-165">There is one extra step in this pattern: the component needs to know if any subscribers have seen the event.</span></span> <span data-ttu-id="a32c6-166">Wenn keine Abonnenten vorhanden sind, würde das Feld fälschlicherweise einen Abbruch angeben.</span><span class="sxs-lookup"><span data-stu-id="a32c6-166">If there are no subscribers, the field would indicate a cancel incorrectly.</span></span>

<span data-ttu-id="a32c6-167">Implementieren wir die erste Version für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="a32c6-167">Let's implement the first version for this sample.</span></span> <span data-ttu-id="a32c6-168">Sie müssen ein boolesches Feld zum FileFoundEventArgs-Typ hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a32c6-168">You need to add a boolean field to the FileFoundEventArgs type:</span></span>

```csharp
public class FileFoundArgs : EventArgs
{
    public string FoundFile { get; }
    public bool CancelRequested { get; set; }

    public FileFoundArgs(string fileName)
    {
        FoundFile = fileName;
    }
}
```

<span data-ttu-id="a32c6-169">Dieses neue Feld sollte mit FALSE initialisiert werden, damit Sie nicht ohne Grund abbrechen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-169">This new Field should be initialized to false, so you don't cancel for no reason.</span></span> <span data-ttu-id="a32c6-170">Das ist der Standardwert für ein boolesches Feld, damit dies automatisch geschieht.</span><span class="sxs-lookup"><span data-stu-id="a32c6-170">That is the default value for a boolean field, so that happens automatically.</span></span> <span data-ttu-id="a32c6-171">Die einzige andere Änderung der Komponente ist das Überprüfen des Flag nach dem Auslösen des Ereignisses, um festzustellen, ob einer der Abonnenten einen Abbruch angefordert hat:</span><span class="sxs-lookup"><span data-stu-id="a32c6-171">The only other change to the component is to check the flag after raising the event to see if any of the subscribers have requested a cancellation:</span></span>

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="a32c6-172">Ein Vorteil dieses Musters ist, dass es keine unterbrechende Änderung ist.</span><span class="sxs-lookup"><span data-stu-id="a32c6-172">One advantage of this pattern is that it isn't a breaking change.</span></span>
<span data-ttu-id="a32c6-173">Keiner der Abonnenten hat vorher einen Abbruch angefordert und macht es noch immer nicht.</span><span class="sxs-lookup"><span data-stu-id="a32c6-173">None of the subscribers requested a cancel before, and they still are not.</span></span> <span data-ttu-id="a32c6-174">Kein Teil des Abonnentencodes benötigt eine Aktualisierung, sofern sie das neue Abbrechen-Protokoll nicht unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="a32c6-174">None of the subscriber code needs updating unless they want to support the new cancel protocol.</span></span> <span data-ttu-id="a32c6-175">Es ist sehr lose gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="a32c6-175">It's very loosely coupled.</span></span>

<span data-ttu-id="a32c6-176">Aktualisieren wir den Abonnenten, damit ein Abbruch angefordert wird, sobald die erste ausführbare Datei gefunden wird:</span><span class="sxs-lookup"><span data-stu-id="a32c6-176">Let's update the subscriber so that it requests a cancellation once it finds the first executable:</span></span>

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a><span data-ttu-id="a32c6-177">Hinzufügen einer anderen Ereignisdeklaration</span><span class="sxs-lookup"><span data-stu-id="a32c6-177">Adding Another Event Declaration</span></span>

<span data-ttu-id="a32c6-178">Fügen wir eine weitere Funktion hinzu, und zeigen andere Sprachausdrücke für Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="a32c6-178">Let's add one more feature, and demonstrate other language idioms for events.</span></span> <span data-ttu-id="a32c6-179">Fügen wir eine Überladung der `Search()`-Methode, die alle Unterverzeichnisse auf der Suche nach Dateien durchsucht.</span><span class="sxs-lookup"><span data-stu-id="a32c6-179">Let's add an overload of the `Search()` method that traverses all subdirectories in search of files.</span></span>

<span data-ttu-id="a32c6-180">In einem Verzeichnis mit vielen Unterverzeichnisse könnte dies ein längerer Vorgang werden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-180">This could get to be a lengthy operation in a directory with many sub-directories.</span></span> <span data-ttu-id="a32c6-181">Fügen wir ein Ereignis hinzu, das zu Beginn jeder neuen Verzeichnissuche ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="a32c6-181">Let's add an event that gets raised when each new directory search begins.</span></span> <span data-ttu-id="a32c6-182">Dies ermöglicht es Abonnenten, den Fortschritt zu verfolgen und den Benutzer während des Fortschritts zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a32c6-182">This enables subscribers to track progress, and update the user as to progress.</span></span> <span data-ttu-id="a32c6-183">Die Beispiele, die Sie bisher erstellt haben, sind öffentlich.</span><span class="sxs-lookup"><span data-stu-id="a32c6-183">All the samples you've created so far are public.</span></span> <span data-ttu-id="a32c6-184">Dieses erstellen wir als internes Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a32c6-184">Let's make this one an internal event.</span></span> <span data-ttu-id="a32c6-185">Das bedeutet, dass Sie auch die Typen für die Argumente intern erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a32c6-185">That means you can also make the types used for the arguments internal as well.</span></span>

<span data-ttu-id="a32c6-186">Sie beginnen mit dem Erstellen der neuen abgeleiteten EventArgs-Klasse für die Berichte des neuen Verzeichnisses und Status.</span><span class="sxs-lookup"><span data-stu-id="a32c6-186">You'll start by creating the new EventArgs derived class for reporting the new directory and progress.</span></span> 

```csharp
internal class SearchDirectoryArgs : EventArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs)
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
``` 

<span data-ttu-id="a32c6-187">In diesem Fall können Sie erneut der Empfehlung für das Erstellen eines nicht änderbaren Verweistyps für die Ereignisargumente folgen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-187">Again, you can follow the recommendations to make an immutable reference type for the event arguments.</span></span>

<span data-ttu-id="a32c6-188">Definieren Sie als Nächstes das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a32c6-188">Next, define the event.</span></span> <span data-ttu-id="a32c6-189">Dieses Mal werden Sie eine andere Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-189">This time, you'll use a different syntax.</span></span> <span data-ttu-id="a32c6-190">Zusätzlich zur Verwendung der Feldsyntax, können Sie die Eigenschaft explizit erstellen, mit dem Hinzufügen- und Entfernen-Handler.</span><span class="sxs-lookup"><span data-stu-id="a32c6-190">In addition to using the field syntax, you can explicitly create the property, with add and remove handlers.</span></span> <span data-ttu-id="a32c6-191">In diesem Beispiel werden Sie für diese Handler in diesem Projekt keinen zusätzlichen Code benötigen, aber dies zeigt, wie Sie sie erstellen würden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-191">In this sample, you won't need extra code in those handlers in this project, but this shows how you would create them.</span></span>

```csharp
internal event EventHandler<SearchDirectoryArgs> DirectoryChanged
{
    add { directoryChanged += value; }
    remove { directoryChanged -= value; }
}
private EventHandler<SearchDirectoryArgs> directoryChanged;
```

<span data-ttu-id="a32c6-192">In vielerlei Hinsicht spiegelt der Code, den Sie hier schreiben, den vom Compiler generierten Code für die Feldereignisdefinitionen wider, die Sie zuvor gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="a32c6-192">In may ways, the code you write here mirrors the code the compiler generates for the field event definitions you've seen earlier.</span></span> <span data-ttu-id="a32c6-193">Sie erstellen das Ereignis mithilfe der Syntax ähnlich der für [Eigenschaften](properties.md).</span><span class="sxs-lookup"><span data-stu-id="a32c6-193">You create the event using syntax very similar to that used for [properties](properties.md).</span></span> <span data-ttu-id="a32c6-194">Beachten Sie, dass die Handler unterschiedliche Namen haben: `add` und `remove`.</span><span class="sxs-lookup"><span data-stu-id="a32c6-194">Notice that the handlers have different names: `add` and `remove`.</span></span> <span data-ttu-id="a32c6-195">Diese werden aufgerufen, um das Ereignis zu abonnieren oder sich vom Ereignis abzumelden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-195">These are called to subscribe to the event, or unsubscribe from the event.</span></span> <span data-ttu-id="a32c6-196">Beachten Sie, dass Sie auch ein privates Unterstützungsfeld zum Speichern der Ereignisvariable deklarieren müssen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-196">Notice that you also must declare a private backing field to store the event variable.</span></span> <span data-ttu-id="a32c6-197">Es wird mit NULL initialisiert.</span><span class="sxs-lookup"><span data-stu-id="a32c6-197">It is initialized to null.</span></span>

<span data-ttu-id="a32c6-198">Als Nächstes fügen wir die Überladung der Search()-Methode hinzu, die Unterverzeichnisse durchsucht und beide Ereignisse auslöst.</span><span class="sxs-lookup"><span data-stu-id="a32c6-198">Next, let's add the overload of the Search() method that traverses subdirectories and raises both events.</span></span> <span data-ttu-id="a32c6-199">Die einfachste Möglichkeit besteht darin, ein Standardargument zu verwenden, um anzugeben, dass alle Verzeichnisse durchsucht werden sollen:</span><span class="sxs-lookup"><span data-stu-id="a32c6-199">The easiest way to accomplish this is to use a default argument to specify that you want to search all directories:</span></span>

```csharp
public void Search(string directory, string searchPattern, bool searchSubDirs = false)
{
    if (searchSubDirs)
    {
        var allDirectories = Directory.GetDirectories(directory, "*.*", SearchOption.AllDirectories);
        var completedDirs = 0;
        var totalDirs = allDirectories.Length + 1;
        foreach (var dir in allDirectories)
        {
            directoryChanged?.Invoke(this,
                new SearchDirectoryArgs(dir, totalDirs, completedDirs++));
            // Recursively search this child directory:
            SearchDirectory(dir, searchPattern);
        }
        // Include the Current Directory:
        directoryChanged?.Invoke(this,
            new SearchDirectoryArgs(directory, totalDirs, completedDirs++));
        SearchDirectory(directory, searchPattern);
    }
    else
    {
        SearchDirectory(directory, searchPattern);
    }
}

private void SearchDirectory(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

<span data-ttu-id="a32c6-200">An diesem Punkt können Sie die Anwendung durch das Aufrufen der Überladung für die Suche aller Unterverzeichnisse ausführen.</span><span class="sxs-lookup"><span data-stu-id="a32c6-200">At this point, you can run the application calling the overload for searching all sub-directories.</span></span> <span data-ttu-id="a32c6-201">Es sind keine Abonnenten auf dem neuen `ChangeDirectory`-Ereignis vorhanden, aber mit den `?.Invoke()`-Ausdruck wird sichergestellt, dass es ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a32c6-201">There are no subscribers on the new `ChangeDirectory` event, but using the `?.Invoke()` idiom ensures that this works correctly.</span></span>

 <span data-ttu-id="a32c6-202">Fügen wir einen Handler hinzu, um eine Zeile zu schreiben, die den Status im Konsolenfenster anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a32c6-202">Let's add a handler to write a line that shows the progress in the console window.</span></span> 

```csharp
lister.DirectoryChanged += (sender, eventArgs) =>
{
    Console.Write($"Entering '{eventArgs.CurrentSearchDirectory}'.");
    Console.WriteLine($" {eventArgs.CompletedDirs} of {eventArgs.TotalDirs} completed...");
};
```

<span data-ttu-id="a32c6-203">Sie haben Muster gesehen, die im .NET-Ökosystem eingehalten werden.</span><span class="sxs-lookup"><span data-stu-id="a32c6-203">You've seen patterns that are followed throughout the .NET ecosystem.</span></span>
<span data-ttu-id="a32c6-204">Indem Sie diese Muster und Konventionen erlernen, werden Sie schnell idiomatische C# und .NET schreiben können.</span><span class="sxs-lookup"><span data-stu-id="a32c6-204">By learning these patterns and conventions, you'll be writing idiomatic C# and .NET quickly.</span></span>

<span data-ttu-id="a32c6-205">Als Nächstes sehen Sie einige Änderungen in diesen Mustern in der neuesten Version von .NET.</span><span class="sxs-lookup"><span data-stu-id="a32c6-205">Next, you'll see some changes in these patterns in the most recent release of .NET.</span></span>

[<span data-ttu-id="a32c6-206">Nächste</span><span class="sxs-lookup"><span data-stu-id="a32c6-206">Next</span></span>](modern-events.md)
