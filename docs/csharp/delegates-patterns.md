---
title: "Gängige Muster für Delegate"
description: "Erfahren Sie etwas über allgemeine Muster für die Verwendung von Delegaten in Ihrem Code, um starke Kopplung zwischen Komponenten zu vermeiden."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0ff8fdfd-6a11-4327-b061-0f2526f35b43
ms.openlocfilehash: 83214800fb997e9274cacfd1bae85ab07c4515a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="common-patterns-for-delegates"></a><span data-ttu-id="20149-104">Gängige Muster für Delegate</span><span class="sxs-lookup"><span data-stu-id="20149-104">Common Patterns for Delegates</span></span>

[<span data-ttu-id="20149-105">Vorheriges</span><span class="sxs-lookup"><span data-stu-id="20149-105">Previous</span></span>](delegates-strongly-typed.md)

<span data-ttu-id="20149-106">Delegaten bieten einen Mechanismus, der Software-Entwürfe ermöglicht, die minimale Kopplung zwischen Komponenten umfassen.</span><span class="sxs-lookup"><span data-stu-id="20149-106">Delegates provide a mechanism that enables software designs involving minimal coupling between components.</span></span>

<span data-ttu-id="20149-107">Ein hervorragendes Beispiel für diese Art von Design ist LINQ.</span><span class="sxs-lookup"><span data-stu-id="20149-107">One excellent example for this kind of design is LINQ.</span></span> <span data-ttu-id="20149-108">Das LINQ-Abfrageausdrucksmuster stützt sich auf Delegaten für alle Funktionen.</span><span class="sxs-lookup"><span data-stu-id="20149-108">The LINQ Query Expression Pattern relies on delegates for all of its features.</span></span> <span data-ttu-id="20149-109">Betrachten Sie folgendes einfaches Beispiel:</span><span class="sxs-lookup"><span data-stu-id="20149-109">Consider this simple example:</span></span>

```csharp
var smallNumbers = numbers.Where(n => n < 10);
```

<span data-ttu-id="20149-110">Die Sequenz von Zahlen wird auf nur die, die kleiner als der Wert 10 sind, gefiltert.</span><span class="sxs-lookup"><span data-stu-id="20149-110">This filters the sequence of numbers to only those less than the value 10.</span></span>
<span data-ttu-id="20149-111">Die `Where`-Methode verwendet einen Delegaten, der bestimmt, welche Elemente einer Sequenz den Filter passieren.</span><span class="sxs-lookup"><span data-stu-id="20149-111">The `Where` method uses a delegate that determines which elements of a sequence pass the filter.</span></span> <span data-ttu-id="20149-112">Wenn Sie eine LINQ-Abfrage erstellen, geben Sie die Implementierung des Delegaten für diesen bestimmten Zweck an.</span><span class="sxs-lookup"><span data-stu-id="20149-112">When you create a LINQ query, you supply the implementation of the delegate for this specific purpose.</span></span>

<span data-ttu-id="20149-113">Der Prototyp für die Where-Methode ist:</span><span class="sxs-lookup"><span data-stu-id="20149-113">The prototype for the Where method is:</span></span>

```csharp
public static IEnumerable<TSource> Where<in TSource> (IEnumerable<TSource> source, Func<TSource, bool> predicate);
```

<span data-ttu-id="20149-114">Dieses Beispiel wird mit allen Methoden wiederholt, die Teil von LINQ sind.</span><span class="sxs-lookup"><span data-stu-id="20149-114">This example is repeated with all the methods that are part of LINQ.</span></span> <span data-ttu-id="20149-115">Alle basieren auf Delegaten für den Code, der die jeweilige Abfrage verwaltet.</span><span class="sxs-lookup"><span data-stu-id="20149-115">They all rely on delegates for the code that manages the specific query.</span></span> <span data-ttu-id="20149-116">Dieses API-Entwurfsmuster ist ein sehr leistungsfähiges Muster zum Erlernen und Verstehen.</span><span class="sxs-lookup"><span data-stu-id="20149-116">This API design pattern is a very powerful one to learn and understand.</span></span>

<span data-ttu-id="20149-117">In diesem einfachen Beispiel wird veranschaulicht, wie Delegaten nur wenig Kopplung zwischen Komponenten erfordern.</span><span class="sxs-lookup"><span data-stu-id="20149-117">This simple example illustrates how delegates require very little coupling between components.</span></span> <span data-ttu-id="20149-118">Sie müssen keine Klasse erstellen, die von einer bestimmten Basisklasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="20149-118">You don't need to create a class that derives from a particular base class.</span></span> <span data-ttu-id="20149-119">Sie müssen keine bestimmte Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="20149-119">You don't need to implement a specific interface.</span></span>
<span data-ttu-id="20149-120">Die einzige Voraussetzung ist die Bereitstellung der Implementierung einer Methode, die für den jeweiligen Task unerlässlich ist.</span><span class="sxs-lookup"><span data-stu-id="20149-120">The only requirement is to provide the implementation of one method that is fundamental to the task at hand.</span></span>

## <a name="building-your-own-components-with-delegates"></a><span data-ttu-id="20149-121">Erstellen eigener Komponenten mit Delegaten</span><span class="sxs-lookup"><span data-stu-id="20149-121">Building Your Own Components with Delegates</span></span>

<span data-ttu-id="20149-122">Erstellen Sie für dieses Beispiel mithilfe eines Entwurfs, das auf Delegaten basiert, eine Komponente.</span><span class="sxs-lookup"><span data-stu-id="20149-122">Let's build on that example by creating a component using a design that relies on delegates.</span></span>

<span data-ttu-id="20149-123">Definieren wir eine Komponente, die in einem umfangreichen System für Protokollmeldungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="20149-123">Let's define a component that could be used for log messages in a large system.</span></span> <span data-ttu-id="20149-124">Bibliothekskomponenten können in vielen verschiedenen Umgebungen auf mehreren verschiedenen Plattformen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20149-124">The library components could be used in many different environments, on multiple different platforms.</span></span> <span data-ttu-id="20149-125">Es gibt zahlreiche allgemeine Funktionen in der Komponente, die die Protokolle verwalten.</span><span class="sxs-lookup"><span data-stu-id="20149-125">There are a lot of common features in the component that manages the logs.</span></span> <span data-ttu-id="20149-126">Es muss Meldungen von jeder Komponente im System annehmen.</span><span class="sxs-lookup"><span data-stu-id="20149-126">It will need to accept messages from any component in the system.</span></span> <span data-ttu-id="20149-127">Diese Meldungen werden über unterschiedliche Prioritäten verfügen, die die Kernkomponente verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="20149-127">Those messages will have different priorities, which the core component can manage.</span></span> <span data-ttu-id="20149-128">Die Meldungen sollten einen Zeitstempel in ihrer endgültigen archivierten Form aufweisen.</span><span class="sxs-lookup"><span data-stu-id="20149-128">The messages should have timestamps in their final archived form.</span></span> <span data-ttu-id="20149-129">Für komplexere Szenarios können Sie Meldungen von der Quellkomponente filtern.</span><span class="sxs-lookup"><span data-stu-id="20149-129">For more advanced scenarios, you could filter messages by the source component.</span></span>

<span data-ttu-id="20149-130">Es gibt ein Aspekt der Funktion, der sich häufig ändern wird: An welchem Standort Meldungen geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="20149-130">There is one aspect of the feature that will change often: where messages are written.</span></span> <span data-ttu-id="20149-131">In einigen Umgebungen können sie in der Fehlerkonsole geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="20149-131">In some environments, they may be written to the error console.</span></span> <span data-ttu-id="20149-132">In anderen Fällen in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="20149-132">In others, a file.</span></span> <span data-ttu-id="20149-133">Andere können beispielsweise Datenbankspeicher, Betriebssystem-Ereignisprotokolle oder andere Dokumentspeicher sein.</span><span class="sxs-lookup"><span data-stu-id="20149-133">Other possibilities include database storage, OS event logs, or other document storage.</span></span>

<span data-ttu-id="20149-134">Es gibt auch Ausgabekombinationen, die in verschiedenen Szenarios verwendet werden könnten.</span><span class="sxs-lookup"><span data-stu-id="20149-134">There are also combinations of output that might be used in different scenarios.</span></span> <span data-ttu-id="20149-135">Möglicherweise möchten Sie Meldungen an die Konsole und in eine Datei schreiben.</span><span class="sxs-lookup"><span data-stu-id="20149-135">You may want to write messages to the console and to a file.</span></span>

<span data-ttu-id="20149-136">Ein Entwurf, basierend auf den Delegaten bietet ein hohes Maß an Flexibilität, und erleichtert Ihnen die Unterstützung von Speichermechanismen, die in der Zukunft möglicherweise hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="20149-136">A design based on delegates will provide a great deal of flexibility, and make it easy to support storage mechanisms that may be added in the future.</span></span>

<span data-ttu-id="20149-137">Durch dieses Design kann die primäre Protokollkomponente eine nicht virtuelle, sogar eine versiegelte Klasse sein.</span><span class="sxs-lookup"><span data-stu-id="20149-137">Under this design, the primary log component can be a non-virtual, even sealed class.</span></span> <span data-ttu-id="20149-138">Sie können eine beliebige Anzahl von Delegaten angeben, um die Meldungen in unterschiedliche Speichermedien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="20149-138">You can plug in any set of delegates to write the messages to different storage media.</span></span> <span data-ttu-id="20149-139">Die integrierte Unterstützung für Multicastdelegaten erleichtert die Unterstützung von Szenarios, in denen Meldungen an mehreren Standorten (eine Datei und eine Konsole) geschrieben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="20149-139">The built in support for multicast delegates makes it easy to support scenarios where messages must be written to multiple locations (a file, and a console).</span></span>

## <a name="a-first-implementation"></a><span data-ttu-id="20149-140">Erste Implementierung</span><span class="sxs-lookup"><span data-stu-id="20149-140">A First Implementation</span></span>

<span data-ttu-id="20149-141">Fangen wir klein an: Die anfängliche Implementierung akzeptiert neue Meldungen, und schreibt mithilfe von angefügten Delegaten.</span><span class="sxs-lookup"><span data-stu-id="20149-141">Let's start small: the initial implementation will accept new messages, and write them using any attached delegate.</span></span> <span data-ttu-id="20149-142">Sie können mit einem Delegaten beginnen, der Meldungen in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="20149-142">You can start with one delegate that writes messages to the console.</span></span>

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(string msg)
    {
        WriteMessage(msg);
    }
}
```

<span data-ttu-id="20149-143">Die statische Klasse oben ist die einfachste Sache, die funktionieren kann.</span><span class="sxs-lookup"><span data-stu-id="20149-143">The static class above is the simplest thing that can work.</span></span> <span data-ttu-id="20149-144">Wir müssen die einzelne Implementierung für die Methode schreiben, die Meldungen in die Konsole schreibt:</span><span class="sxs-lookup"><span data-stu-id="20149-144">We need to write the single implementation for the method that writes messages to the console:</span></span> 

```csharp
public static void LogToConsole(string message)
{
    Console.Error.WriteLine(message);
}
```

<span data-ttu-id="20149-145">Abschließend müssen Sie den Delegaten verknüpfen, indem Sie ihn an den WriteMessage-Delegaten anfügen, der in der Protokollierung deklariert wurde:</span><span class="sxs-lookup"><span data-stu-id="20149-145">Finally, you need to hook up the delegate by attaching it to the WriteMessage delegate declared in the logger:</span></span>

```csharp
Logger.WriteMessage += LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="20149-146">Methoden</span><span class="sxs-lookup"><span data-stu-id="20149-146">Practices</span></span>

<span data-ttu-id="20149-147">Unser Beispiel ist bisher recht einfach, aber es veranschaulicht immer noch einige der wichtigen Richtlinien für Entwürfe, die Delegaten umfassen.</span><span class="sxs-lookup"><span data-stu-id="20149-147">Our sample so far is fairly simple, but it still demonstrates some of the important guidelines for designs involving delegates.</span></span>

<span data-ttu-id="20149-148">Delegattypen zu verwenden, die in der Kern-Framework definiert sind, erleichtert Benutzern die Arbeit mit den Delegaten.</span><span class="sxs-lookup"><span data-stu-id="20149-148">Using the delegate types defined in the Core Framework makes it easier for users to work with the delegates.</span></span> <span data-ttu-id="20149-149">Sie müssen keine neue Typen definieren, und Entwickler, die die Bibliothek nutzen, müssen keine neuen, spezialisierten Delegattypen erlernen.</span><span class="sxs-lookup"><span data-stu-id="20149-149">You don't need to define new types, and developers using your library do not need to learn new, specialized delegate types.</span></span>

<span data-ttu-id="20149-150">Die verwendeten Schnittstellen sind so minimal und so flexibel wie möglich: Um eine neue Ausgabeprotokollierung zu erstellen, müssen Sie eine Methode erstellen.</span><span class="sxs-lookup"><span data-stu-id="20149-150">The interfaces used are as minimal and as flexible as possible: To create a new output logger, you must create one method.</span></span> <span data-ttu-id="20149-151">Diese Methode kann eine statische Methode oder eine Instanzmethode sein.</span><span class="sxs-lookup"><span data-stu-id="20149-151">That method may be a static method, or an instance method.</span></span> <span data-ttu-id="20149-152">Es kann über jeden Zugriff verfügen.</span><span class="sxs-lookup"><span data-stu-id="20149-152">It may have any access.</span></span>

## <a name="formatting-output"></a><span data-ttu-id="20149-153">Formatieren der Ausgabe</span><span class="sxs-lookup"><span data-stu-id="20149-153">Formatting Output</span></span>

<span data-ttu-id="20149-154">Lassen Sie uns die erste Version etwas stabiler machen und anschließend andere Protokollierungsmechanismen erstellen.</span><span class="sxs-lookup"><span data-stu-id="20149-154">Let's make this first version a bit more robust, and then start creating other logging mechanisms.</span></span>

<span data-ttu-id="20149-155">Als Nächstes fügen wir einige Argumente in die `LogMessage()`-Methode ein, damit Ihre Protokollklasse mehr strukturierte Meldungen erstellt:</span><span class="sxs-lookup"><span data-stu-id="20149-155">Next, let's add a few arguments to the `LogMessage()` method so that your log class creates more structured messages:</span></span>

```csharp
// Logger implementation two
public enum Severity
{
    Verbose,
    Trace,
    Information,
    Warning,
    Error,
    Critical
}

public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```

<span data-ttu-id="20149-156">Als Nächstes verwenden wir dieses `Severity`-Argument, um die Meldungen zu filtern, die in das Ausgabeprotokoll gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="20149-156">Next, let's make use of that `Severity` argument to filter the messages that are sent to the log's output.</span></span> 

```csharp
public static class Logger
{
    public static Action<string> WriteMessage;
    
    public static Severity LogLevel {get;set;} = Severity.Warning;
    
    public static void LogMessage(Severity s, string component, string msg)
    {
        if (s < LogLevel)
            return;
            
        var outputMsg = $"{DateTime.Now}\t{s}\t{component}\t{msg}";
        WriteMessage(outputMsg);
    }
}
```
## <a name="practices"></a><span data-ttu-id="20149-157">Methoden</span><span class="sxs-lookup"><span data-stu-id="20149-157">Practices</span></span>

<span data-ttu-id="20149-158">Sie haben der Protokollierungsinfrastruktur neue Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20149-158">You've added new features to the logging infrastructure.</span></span> <span data-ttu-id="20149-159">Da die Protokollierungskomponente sehr lose an Ausgabemechanismen gekoppelt ist, können diese neuen Funktionen ohne Auswirkung auf den Code, der die Protokollierungsdelegaten implementiert, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="20149-159">Because the logger component is very loosely coupled to any output mechanism, these new features can be added with no impact on any of the code implementing the logger delegate.</span></span>

<span data-ttu-id="20149-160">Solange Sie dies erstellen, sehen Sie weitere Beispiele, wie diese lose Verbindung mehr Flexibilität bei der Aktualisierung von Teilen der Site ohne Änderungen an anderen Speicherorten ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="20149-160">As you keep building this, you'll see more examples of how this loose coupling enables greater flexibility in updating parts of the site without any changes to other locations.</span></span> <span data-ttu-id="20149-161">In der Tat könnten die Klassen der Protokollierungsausgabe in einer umfangreicheren Anwendung in einer anderen Assembly sein. Sie müssen auch nicht neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="20149-161">In fact, in a larger application, the logger output classes might be in a different assembly, and not even need to be rebuilt.</span></span>

## <a name="building-a-second-output-engine"></a><span data-ttu-id="20149-162">Erstellen eines zweiten Ausgabemoduls</span><span class="sxs-lookup"><span data-stu-id="20149-162">Building a Second Output Engine</span></span>

<span data-ttu-id="20149-163">Die Protokollierungskomponente kommt gut voran.</span><span class="sxs-lookup"><span data-stu-id="20149-163">The Log component is coming along well.</span></span> <span data-ttu-id="20149-164">Fügen wir ein weiteres Ausgabemodul hinzu, das Meldungen in einer Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="20149-164">Let's add one more output engine that logs messages to a file.</span></span> <span data-ttu-id="20149-165">Dies wird ein etwas komplexeres Ausgabemodul werden.</span><span class="sxs-lookup"><span data-stu-id="20149-165">This will be a slightly more involved output engine.</span></span> <span data-ttu-id="20149-166">Es wird eine Klasse sein, die die Dateivorgänge kapselt, und sicherstellt, dass die Datei nach jedem Schreibvorgang immer geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="20149-166">It will be a class that encapsulates the file operations, and ensures that the file is always closed after each write.</span></span> <span data-ttu-id="20149-167">Dadurch wird sichergestellt, dass alle Daten auf den Datenträger geschrieben werden, nachdem jede Meldung generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="20149-167">That ensures that all the data is flushed to disk after each message is generated.</span></span>

<span data-ttu-id="20149-168">Hier ist diese dateibasierte-Protokollierung:</span><span class="sxs-lookup"><span data-stu-id="20149-168">Here is that file based logger:</span></span>

```csharp
public class FileLogger
{
    private readonly string logPath;
    public FileLogger(string path)
    {
        logPath = path;
        Logger.WriteMessage += LogMessage;
    }
    
    public void DetachLog() => Logger.WriteMessage -= LogMessage;

    // make sure this can't throw.
    private void LogMessage(string msg)
    {
        try {
            using (var log = File.AppendText(logPath))
            {
                log.WriteLine(msg);
                log.Flush();
            }
        } catch (Exception e)
        {
            // Hmm. Not sure what to do.
            // Logging is failing...
        }
    }
}
```

<span data-ttu-id="20149-169">Wenn Sie diese Klasse erstellt haben, können Sie sie instanziieren und sie fügt ihre LogMessage-Methode in die Protokollierungskomponente an:</span><span class="sxs-lookup"><span data-stu-id="20149-169">Once you've created this class, you can instantiate it and it attaches its LogMessage method to the Logger component:</span></span>

```csharp
var file = new FileLogger("log.txt");
```

<span data-ttu-id="20149-170">Diese beiden schließen einander nicht aus.</span><span class="sxs-lookup"><span data-stu-id="20149-170">These two are not mutually exclusive.</span></span> <span data-ttu-id="20149-171">Sie können beide Protokollmethoden anfügen, und Meldungen in die Konsole und eine Datei generieren:</span><span class="sxs-lookup"><span data-stu-id="20149-171">You could attach both log methods and generate messages to the console and a file:</span></span>

```csharp
var fileOutput = new FileLogger("log.txt");
Logger.WriteMessage += LogToConsole;
```

<span data-ttu-id="20149-172">Später können Sie auch in derselben Anwendung einen Delegaten ohne andere Probleme auf dem System entfernen:</span><span class="sxs-lookup"><span data-stu-id="20149-172">Later, even in the same application, you can remove one of the delegates without any other issues to the system:</span></span>

```csharp
Logger.WriteMessage -= LogToConsole;
```

## <a name="practices"></a><span data-ttu-id="20149-173">Methoden</span><span class="sxs-lookup"><span data-stu-id="20149-173">Practices</span></span>

<span data-ttu-id="20149-174">Sie haben nun einen zweiten Ausgabehandler für das Protokollierungs-Subsystem hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20149-174">Now, you've added a second output handler for the logging sub-system.</span></span>
<span data-ttu-id="20149-175">Dieses Objekt benötigt ein wenig mehr Infrastruktur, um das Dateisystem ordnungsgemäß zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="20149-175">This one needs a bit more infrastructure to correctly support the file system.</span></span> <span data-ttu-id="20149-176">Bei dem Delegat handelt es sich um eine Instanzmethode.</span><span class="sxs-lookup"><span data-stu-id="20149-176">The delegate is an instance method.</span></span> <span data-ttu-id="20149-177">Es ist auch eine private Methode.</span><span class="sxs-lookup"><span data-stu-id="20149-177">It's also a private method.</span></span>
<span data-ttu-id="20149-178">Es besteht keine Notwendigkeit für höhere Verfügbarkeit, da die Delegat-Infrastruktur die Delegaten verbinden kann.</span><span class="sxs-lookup"><span data-stu-id="20149-178">There's no need for greater accessibility because the delegate infrastructure can connect the delegates.</span></span>

<span data-ttu-id="20149-179">Zweitens ermöglicht der delegatbasierte Entwurf mehrere Ausgabemethoden ohne zusätzlichen Code.</span><span class="sxs-lookup"><span data-stu-id="20149-179">Second, the delegate-based design enables multiple output methods without any extra code.</span></span> <span data-ttu-id="20149-180">Sie müssen keine zusätzliche Infrastruktur zur Unterstützung von mehreren Ausgabemethoden erstellen.</span><span class="sxs-lookup"><span data-stu-id="20149-180">You don't need to build any additional infrastructure to support multiple output methods.</span></span> <span data-ttu-id="20149-181">Sie erhalten einfach eine andere Methode auf der Aufrufliste.</span><span class="sxs-lookup"><span data-stu-id="20149-181">They simply become another method on the invocation list.</span></span>

<span data-ttu-id="20149-182">Achten Sie besonders auf den Code in der Ausgabemethode, die die Datei protokolliert.</span><span class="sxs-lookup"><span data-stu-id="20149-182">Pay special attention to the code in the file logging output method.</span></span> <span data-ttu-id="20149-183">Es wird codiert, um sicherzustellen, dass keine Ausnahmen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="20149-183">It is coded to ensure that it does not throw any exceptions.</span></span> <span data-ttu-id="20149-184">Obwohl dies nicht immer unbedingt erforderlich ist, ist es häufig sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="20149-184">While this isn't always strictly necessary, it's often a good practice.</span></span> <span data-ttu-id="20149-185">Wenn eine der Delegatmethoden eine Ausnahme auslöst, werden die im Aufruf verbleibenden Delegaten nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="20149-185">If either of the delegate methods throws an exception, the remaining delegates that are on the invocation won't be invoked.</span></span>

<span data-ttu-id="20149-186">Ein letzter Hinweis: Die Dateiprotokollierung muss ihre Ressourcen durch Öffnen und Schließen der Datei in jeder Protokollmeldung verwalten.</span><span class="sxs-lookup"><span data-stu-id="20149-186">As a last note, the file logger must manage its resources by opening and closing the file on each log message.</span></span> <span data-ttu-id="20149-187">Sie können die Datei offen lassen und IDisposable implementieren, um die Datei zu schließen, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="20149-187">You could choose to keep the file open and implement IDisposable to close the file when you are completed.</span></span>
<span data-ttu-id="20149-188">Beide Methoden haben Vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="20149-188">Either method has its advantages and disadvantages.</span></span> <span data-ttu-id="20149-189">Beide erstellen etwas mehr Kopplung zwischen den Klassen.</span><span class="sxs-lookup"><span data-stu-id="20149-189">Both do create a bit more coupling between the classes.</span></span>

<span data-ttu-id="20149-190">Kein Teil des Codes in der Protokollierungsklasse müsste aktualisiert werden, um beide Szenarios zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="20149-190">None of the code in the Logger class would need to be updated in order to support either scenario.</span></span>

## <a name="handling-null-delegates"></a><span data-ttu-id="20149-191">Behandlung von NULL-Delegaten</span><span class="sxs-lookup"><span data-stu-id="20149-191">Handling Null Delegates</span></span>

<span data-ttu-id="20149-192">Zum Schluss aktualisieren wir die LogMessage-Methode, damit es für jene Fälle stabil ist, wenn kein Ausgabemechanismus ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="20149-192">Finally, let's update the LogMessage method so that it is robust for those cases when no output mechanism is selected.</span></span> <span data-ttu-id="20149-193">Die aktuelle Implementierung löst eine `NullReferenceException` aus, wenn der `WriteMessage`-Delegat nicht über eine angefügte Aufrufliste verfügt.</span><span class="sxs-lookup"><span data-stu-id="20149-193">The current implementation will throw a `NullReferenceException` when the `WriteMessage` delegate does not have an invocation list attached.</span></span>
<span data-ttu-id="20149-194">Möglicherweise bevorzugen Sie einen Entwurf, der im Hintergrund fortgesetzt wird, wenn keine Methoden angefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="20149-194">You may prefer a design that silently continues when no methods have been attached.</span></span> <span data-ttu-id="20149-195">Dies lässt sich mithilfe des bedingten NULL-Operators, kombiniert mit der `Delegate.Invoke()`-Methode, leicht umsetzen:</span><span class="sxs-lookup"><span data-stu-id="20149-195">This is easy using the null conditional operator, combined with the `Delegate.Invoke()` method:</span></span>

```csharp
public static void LogMessage(string msg)
{
    WriteMessage?.Invoke(msg);
}
```

<span data-ttu-id="20149-196">Der bedingte NULL-Operator (`?.`) wird verkürzt, wenn der linke Operand (`WriteMessage` in diesem Fall) NULL ist, was bedeutet, dass nicht versucht wurde, eine Meldung zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="20149-196">The null conditional operator (`?.`) short-circuits when the left operand (`WriteMessage` in this case) is null, which means no attempt is made to log a message.</span></span>

<span data-ttu-id="20149-197">Sie werden die `Invoke()`-Methode nicht in der Dokumentation für `System.Delegate` oder `System.MulticastDelegate` aufgelistet finden.</span><span class="sxs-lookup"><span data-stu-id="20149-197">You won't find the `Invoke()` method listed in the documentation for `System.Delegate` or `System.MulticastDelegate`.</span></span> <span data-ttu-id="20149-198">Der Compiler generiert eine typsicherer `Invoke`-Methode für jeden deklarierten Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="20149-198">The compiler generates a type safe `Invoke` method for any delegate type declared.</span></span> <span data-ttu-id="20149-199">In diesem Beispiel bedeutet das, dass `Invoke` ein einzelnes `string`-Argument nimmt und über einen void-Rückgabetyp verfügt.</span><span class="sxs-lookup"><span data-stu-id="20149-199">In this example, that means `Invoke` takes a single `string` argument, and has a void return type.</span></span>

## <a name="summary-of-practices"></a><span data-ttu-id="20149-200">Zusammenfassung der Methoden</span><span class="sxs-lookup"><span data-stu-id="20149-200">Summary of Practices</span></span>

<span data-ttu-id="20149-201">Sie haben die Anfänge einer Protokollkomponente gesehen, die mit anderen Writern und anderen Funktionen erweitert werden konnte.</span><span class="sxs-lookup"><span data-stu-id="20149-201">You've seen the beginnings of a log component that could be expanded with other writers, and other features.</span></span> <span data-ttu-id="20149-202">Mithilfe von Delegaten im Entwurf sind diese verschiedenen Komponenten sehr lose gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="20149-202">By using delegates in the design these different components are very loosely coupled.</span></span> <span data-ttu-id="20149-203">Dies bietet mehrere Vorteile.</span><span class="sxs-lookup"><span data-stu-id="20149-203">This provides several advantages.</span></span> <span data-ttu-id="20149-204">Es ist sehr einfach neue Ausgabemechanismen zu erstellen und diese an das System anzufügen.</span><span class="sxs-lookup"><span data-stu-id="20149-204">It's very easy to create new output mechanisms and attach them to the system.</span></span> <span data-ttu-id="20149-205">Diese Mechanismen benötigen nur eine Methode: Die Methode, die die Protokollmeldungen schreibt.</span><span class="sxs-lookup"><span data-stu-id="20149-205">These other mechanisms only need one method: the method that writes the log message.</span></span> <span data-ttu-id="20149-206">Es ist ein Entwurf, der sehr stabil ist, wenn neue Funktionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="20149-206">It's a design that is very resilient when new features are added.</span></span> <span data-ttu-id="20149-207">Der für alle Writer erforderliche Vertrag dient dazu, eine Methode zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="20149-207">The contract required for any writer is to implement one method.</span></span> <span data-ttu-id="20149-208">Diese Methode kann eine statische oder Instanzmethode sein.</span><span class="sxs-lookup"><span data-stu-id="20149-208">That method could be a static or instance method.</span></span> <span data-ttu-id="20149-209">Es kann sich um einen öffentlichen, privaten oder jeden anderen rechtlichen Zugriff handeln.</span><span class="sxs-lookup"><span data-stu-id="20149-209">It could be public, private, or any other legal access.</span></span>

<span data-ttu-id="20149-210">Die Protokollierungsklasse kann eine beliebige Anzahl von Verbesserungen oder Änderungen vornehmen, ohne wichtige Änderungen einzuführen.</span><span class="sxs-lookup"><span data-stu-id="20149-210">The Logger class can make any number of enhancements or changes without introducing breaking changes.</span></span> <span data-ttu-id="20149-211">Wie jede Klasse können Sie die öffentliche API nicht ohne das Risiko von wichtigen Änderungen ändern.</span><span class="sxs-lookup"><span data-stu-id="20149-211">Like any class, you cannot modify the public API without the risk of breaking changes.</span></span> <span data-ttu-id="20149-212">Aber da die Kopplung zwischen der Protokollierung und den Ausgabemodulen nur über den Delegaten stattfindet, sind keine anderen Typen (z.B. Schnittstellen oder Basisklassen) beteiligt.</span><span class="sxs-lookup"><span data-stu-id="20149-212">But, because the coupling between the logger and any output engines is only through the delegate, no other types (like interfaces or base classes) are involved.</span></span> <span data-ttu-id="20149-213">Die Kopplung ist so klein wie möglich.</span><span class="sxs-lookup"><span data-stu-id="20149-213">The coupling is as small as possible.</span></span>

[<span data-ttu-id="20149-214">Weiter</span><span class="sxs-lookup"><span data-stu-id="20149-214">Next</span></span>](events-overview.md)
