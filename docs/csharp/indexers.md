---
title: Indexer
description: "Erfahren Sie mehr über C#-Indexer und wie sie indizierte Eigenschaften, d.h. Eigenschaften, auf die mit mindestens einem Argument verwiesen wird, implementieren."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 468c86f36fe71558dcd7a9150337f5a3cce066b8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="indexers"></a><span data-ttu-id="50003-104">Indexer</span><span class="sxs-lookup"><span data-stu-id="50003-104">Indexers</span></span>

<span data-ttu-id="50003-105">*Indexer* sind ähnlich wie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="50003-105">*Indexers* are similar to properties.</span></span> <span data-ttu-id="50003-106">In vielen Aspekten bauen Indexer genauso wie [Eigenschaften](properties.md) auf den gleichen Sprachfunktionen auf.</span><span class="sxs-lookup"><span data-stu-id="50003-106">In many ways indexers build on the same language features as [properties](properties.md).</span></span> <span data-ttu-id="50003-107">Indexer ermöglichen *indizierte* Eigenschaften: Eigenschaften, auf die von mindestens einem Argument verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="50003-107">Indexers enable *indexed* properties: properties referenced using one or more arguments.</span></span> <span data-ttu-id="50003-108">Diese Argumente stellen einen Index in einer Auflistung von Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="50003-108">Those arguments provide an index into some collection of values.</span></span>

## <a name="indexer-syntax"></a><span data-ttu-id="50003-109">Indexersyntax</span><span class="sxs-lookup"><span data-stu-id="50003-109">Indexer Syntax</span></span>

<span data-ttu-id="50003-110">Sie können mithilfe eines Variablennamens und eckiger Klammern auf einen Indexer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="50003-110">You access an indexer through a variable name and square brackets .</span></span> <span data-ttu-id="50003-111">Geben Sie die Indexerargumente innerhalb der Klammern ein:</span><span class="sxs-lookup"><span data-stu-id="50003-111">You place the indexer arguments inside the brackets:</span></span>

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

<span data-ttu-id="50003-112">Sie können Indexer deklarieren, in dem sie das Schlüsselwort `this` als Eigenschaftenname verwenden und die Argumente in eckigen Klammern deklarieren.</span><span class="sxs-lookup"><span data-stu-id="50003-112">You declare indexers using the `this` keyword as the property name, and declaring the arguments within square brackets.</span></span> <span data-ttu-id="50003-113">Diese Deklaration stimmt mit dem Gebrauch in oben stehendem Abschnitt überein:</span><span class="sxs-lookup"><span data-stu-id="50003-113">This declaration would match the usage shown in the previous paragraph:</span></span>

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

<span data-ttu-id="50003-114">Dieses erste Beispiel veranschaulicht die Beziehung zwischen der Syntax der Eigenschaften und der Indexer.</span><span class="sxs-lookup"><span data-stu-id="50003-114">From this initial example, you can see the relationship between the syntax for properties and for indexers.</span></span> <span data-ttu-id="50003-115">Diese Analogie wirkt sich auf die meisten Syntaxregeln für Indexer auf.</span><span class="sxs-lookup"><span data-stu-id="50003-115">This analogy carries through most of the syntax rules for indexers.</span></span> <span data-ttu-id="50003-116">Indexer können beliebige Zugriffsmodifizierer aufweisen (öffentliche, geschützte interne, geschützte, interne oder private).</span><span class="sxs-lookup"><span data-stu-id="50003-116">Indexers can have any valid access modifiers (public, protected internal, protected, internal, or private).</span></span> <span data-ttu-id="50003-117">Sie können versiegelt, virtuell oder abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="50003-117">They may be sealed, virtual, or abstract.</span></span> <span data-ttu-id="50003-118">Bei Eigenschaften können Sie verschiedene Zugriffsmodifizierer für die get- und set-Zugriffsmethoden eines Indexers angeben.</span><span class="sxs-lookup"><span data-stu-id="50003-118">As with properties, you can specify different access modifiers for the get and set accesssors in an indexer.</span></span>
<span data-ttu-id="50003-119">Außerdem können Sie schreibgeschützte Indexer (indem Sie die set-Zugriffsmethode auslassen) oder lesegeschützte Indexer (indem Sie die get-Zugriffsmethode auslassen) angeben.</span><span class="sxs-lookup"><span data-stu-id="50003-119">You may also specify read-only indexers (by omitting the set accessor), or write-only indexers (by omitting the get accessor).</span></span>

<span data-ttu-id="50003-120">Fast alles, was Sie von der Arbeit mit Eigenschaften kennen, können sie auch für Indexer anwenden.</span><span class="sxs-lookup"><span data-stu-id="50003-120">You can apply almost everything you learn from working with properties to indexers.</span></span> <span data-ttu-id="50003-121">Die einzige Ausnahme von dieser Regel sind *automatisch implementierte Eigenschaften*.</span><span class="sxs-lookup"><span data-stu-id="50003-121">The only exception to that rule is *auto implemented properties*.</span></span> <span data-ttu-id="50003-122">Der Compiler kann nicht immer angemessenen Speicher für einen Indexer generieren.</span><span class="sxs-lookup"><span data-stu-id="50003-122">The compiler cannot always generate the correct storage for an indexer.</span></span>

<span data-ttu-id="50003-123">Indexer unterscheiden sich durch das Vorhandensein von Argumenten, die auf ein Element in einem Satz von Elementen verweisen, von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="50003-123">The presence of arguments to reference an item in a set of items distinguishes indexers from properties.</span></span> <span data-ttu-id="50003-124">Sie können mehrere Indexer in einem Typ definieren, solange die Argumentauflistung für jeden Indexer eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="50003-124">You may define multiple indexers on a type, as long as the argument lists for each indexer is unique.</span></span> <span data-ttu-id="50003-125">In den folgenden Szenarios erfahren Sie mehr über das Verwenden von einem oder mehreren Indexern in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="50003-125">Let's explore different scenarios where you might use one or more indexers in a class definition.</span></span> 

## <a name="scenarios"></a><span data-ttu-id="50003-126">Szenarien</span><span class="sxs-lookup"><span data-stu-id="50003-126">Scenarios</span></span>

<span data-ttu-id="50003-127">Sie definieren *Indexer* in Ihrem Typ, wenn dessen API eine Auflistung modelliert, in der Sie die Argumente der Auflistung definieren.</span><span class="sxs-lookup"><span data-stu-id="50003-127">You would define *indexers* in your type when its API models some collection where you define the arguments to that collection.</span></span> <span data-ttu-id="50003-128">Ihre Indexer ordnen möglicherweise direkt zu Ihren Auflistungstypen zu, die Teil des .NET Core Frameworks sind.</span><span class="sxs-lookup"><span data-stu-id="50003-128">Your indexers may or may not map directly to the collection types that are part of the .NET core framework.</span></span> <span data-ttu-id="50003-129">Ihr Typ hat möglicherweise andere Verpflichtungen als nur das Modellieren einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="50003-129">Your type may have other responsibilities in addition to modeling a collection.</span></span>
<span data-ttu-id="50003-130">Mit Indexern können Sie die API bereitstellen, die mit der Abstraktion Ihres Typs übereinstimmt, ohne die inneren Details offen zu legen, wie die Werte dieser Abstraktion gespeichert oder berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="50003-130">Indexers enable you to provide the API that matches your type's abstraction without exposing the inner details of how the values for that abstraction are stored or computed.</span></span>

<span data-ttu-id="50003-131">Die häufigsten Szenarios für das Verwenden von *Indexern*.</span><span class="sxs-lookup"><span data-stu-id="50003-131">Let's walk through some of the common scenarios for using *indexers*.</span></span> <span data-ttu-id="50003-132">Sie können auf den [Beispielordner für Indexer](https://github.com/dotnet/docs/tree/master/samples/csharp/indexers) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="50003-132">You can access the [sample folder for indexers](https://github.com/dotnet/docs/tree/master/samples/csharp/indexers).</span></span> <span data-ttu-id="50003-133">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="50003-133">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="arrays-and-vectors"></a><span data-ttu-id="50003-134">Arrays und Vektoren</span><span class="sxs-lookup"><span data-stu-id="50003-134">Arrays and Vectors</span></span>

<span data-ttu-id="50003-135">Eines der häufigsten Szenarios beim Erstellen von Indexern ist, wenn Ihr Typ ein Array oder einen Vektor modelliert.</span><span class="sxs-lookup"><span data-stu-id="50003-135">One of the most common scenarios for creating indexers is when your type models an array, or a vector.</span></span> <span data-ttu-id="50003-136">Sie können einen Indexer erstellen, um eine geordnete Datenliste zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="50003-136">You can create an indexer to model an ordered list of data.</span></span> 

<span data-ttu-id="50003-137">Der Vorteil beim Erstellen eines eigenen Indexers ist die Tatsache, dass Sie den Speicher für diese Auflistung an Ihre Bedürfnisse anpassen können.</span><span class="sxs-lookup"><span data-stu-id="50003-137">The advantage of creating your own indexer is that you can define the storage for that collection to suit your needs.</span></span> <span data-ttu-id="50003-138">Stellen Sie sich ein Szenario vor, in dem Ihr Typ historische Daten modelliert, die zu groß sind, um sie auf einmal in den Speicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="50003-138">Imagine a scenario where your type models historical data that is too large to load into memory at once.</span></span> <span data-ttu-id="50003-139">Sie müssen Abschnitte der Auflistung nach Verbrauch laden und entladen.</span><span class="sxs-lookup"><span data-stu-id="50003-139">You need to load and unload sections of the collection based on usage.</span></span> <span data-ttu-id="50003-140">Das folgende Beispiel veranschaulicht dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="50003-140">The example following models this behavior.</span></span> <span data-ttu-id="50003-141">Es meldet, wie viele Datenpunkte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50003-141">It reports on how many data points exist.</span></span> <span data-ttu-id="50003-142">Es erstellt Seiten, die auf Abruf Abschnitte der Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="50003-142">It creates pages to hold sections of the data on demand.</span></span> <span data-ttu-id="50003-143">Es entfernt Seiten aus dem Speicher, um Platz für Seiten zu schaffen, die für eine aktuelle Abfrage benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="50003-143">It removes pages from memory to make room for pages needed by more recent requests.</span></span>

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

<span data-ttu-id="50003-144">Sie können diesem Entwurfsausdruck folgen, um jede beliebige Auflistungsart dort zu modellieren, wo es gute Gründe gibt, nicht den gesamten Datensatz in eine Auflistung im Speicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="50003-144">You can follow this design idiom to model any sort of collection where there are good reasons not to load the entire set of data into an in- memory collection.</span></span> <span data-ttu-id="50003-145">Beachten Sie, dass die Klasse `Page` eine private geschachtelte Klasse ist, die nicht Teil der öffentlichen Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="50003-145">Notice that the `Page` class is a private nested class that is not part of the public interface.</span></span> <span data-ttu-id="50003-146">Diese Informationen sind für jeden Benutzer der Klasse verborgen.</span><span class="sxs-lookup"><span data-stu-id="50003-146">Those details are hidden from any users of this class.</span></span>

### <a name="dictionaries"></a><span data-ttu-id="50003-147">Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="50003-147">Dictionaries</span></span>

<span data-ttu-id="50003-148">Ein weiteres häufiges Szenario ist, wenn Sie ein Wörterbuch oder eine Zuordnung modellieren möchten.</span><span class="sxs-lookup"><span data-stu-id="50003-148">Another common scenario is when you need to model a dictionary or a map.</span></span> <span data-ttu-id="50003-149">In diesem Szenario speichert Ihr Typ Werte nach Schlüsseln, typischerweise Textschlüssel.</span><span class="sxs-lookup"><span data-stu-id="50003-149">This scenario is when your type stores values based on key, typically text keys.</span></span> <span data-ttu-id="50003-150">In diesem Beispiel wird ein Wörterbuch erstellt, das Befehlszeilenargumente [Lambdaausdrücken](delegates-overview.md) zuordnet, die diese Optionen verwalten.</span><span class="sxs-lookup"><span data-stu-id="50003-150">This example creates a dictionary that maps command line arguments to [lamdba expressions](delegates-overview.md) that manage those options.</span></span> <span data-ttu-id="50003-151">In folgenden Beispiel werden zwei Klassen gezeigt: eine `ArgsActions`-Klasse, die eine Befehlszeilenoption einem `Action`-Delegaten zuordnet, und ein `ArgsProcessor`, um mit jeder `ArgsActions` eine `Action` auszuführen, wenn es auf diese Option trifft.</span><span class="sxs-lookup"><span data-stu-id="50003-151">The following example shows two classes: an `ArgsActions` class that maps a command line option to an `Action` delegate, and an `ArgsProcessor` that uses the `ArgsActions` to execute each `Action` when it encounters that option.</span></span>

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

<span data-ttu-id="50003-152">In diesem Beispiel ordnet die `ArgsAction`-Auflistung nah an der zugrundeliegenden Auflistung zu.</span><span class="sxs-lookup"><span data-stu-id="50003-152">In this example, the `ArgsAction` collection maps closely to the underlying collection.</span></span>
<span data-ttu-id="50003-153">`get` legt fest, ob eine gegebene Option konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="50003-153">The `get` determines if a given option has been configured.</span></span> <span data-ttu-id="50003-154">Falls dem so ist, gibt es die mit dieser Option verknüpfte `Action` zurück.</span><span class="sxs-lookup"><span data-stu-id="50003-154">If so, it returns the `Action` associated with that option.</span></span> <span data-ttu-id="50003-155">Falls dem nicht so ist, gibt es eine `Action` zurück, die keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="50003-155">If not, it returns an `Action` that does nothing.</span></span> <span data-ttu-id="50003-156">Die öffentliche Zugriffsmethode enthält keine `set`-Zugriffsmethode.</span><span class="sxs-lookup"><span data-stu-id="50003-156">The public accessor does not include a `set` accessor.</span></span> <span data-ttu-id="50003-157">Stattdessen enthält Sie den Entwurf, der eine öffentliche Methode für das Festlegen von Optionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="50003-157">Rather, the design using a public method for setting options.</span></span>

### <a name="multi-dimensional-maps"></a><span data-ttu-id="50003-158">Mehrdimensionale Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="50003-158">Multi-Dimensional Maps</span></span>

<span data-ttu-id="50003-159">Sie können Indexer erstellen, die mehrere Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="50003-159">You can create indexers that use multiple arguments.</span></span> <span data-ttu-id="50003-160">Zusätzlich sind müssen diese Argumente nicht denselben Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="50003-160">In addition, those arguments are not constrained to be the same type.</span></span> <span data-ttu-id="50003-161">Nachfolgend sehen Sie zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="50003-161">Let's look at two examples.</span></span>   

<span data-ttu-id="50003-162">Das erste Beispiel zeigt eine Klasse, die Werte einer Mandelbrot-Menge generiert.</span><span class="sxs-lookup"><span data-stu-id="50003-162">The first example shows a class that generates values for a Mandelbrot set.</span></span> <span data-ttu-id="50003-163">Weitere Informationen zur Mathematik der Menge finden Sie in [diesem Artikel](https://en.wikipedia.org/wiki/Mandelbrot_set).</span><span class="sxs-lookup"><span data-stu-id="50003-163">For more information on the mathematics behind the set, read [this article](https://en.wikipedia.org/wiki/Mandelbrot_set).</span></span> <span data-ttu-id="50003-164">Der Indexer verwendet zwei double-Werte, um einen Punkt auf der X-Y-Ebene zu definieren.</span><span class="sxs-lookup"><span data-stu-id="50003-164">The indexer uses two doubles to define a point in the X, Y plane.</span></span>
<span data-ttu-id="50003-165">Die get-Zugriffsmethode berechnet die Anzahl der Iterationen, bis ein Punkt festgelegt wird, der außerhalb der Menge liegt.</span><span class="sxs-lookup"><span data-stu-id="50003-165">The get accessor computes the number of iterations until a point is determined to be not in the set.</span></span> <span data-ttu-id="50003-166">Wenn die maximale Zahl an Iterationen erreicht ist, befindet sich der Punkt in der Menge, und der Wert „maxIterations“ der Klasse wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50003-166">If the maximum iterations is reached, the point is in the set, and the class's maxIterations value is returned.</span></span> <span data-ttu-id="50003-167">(Die vom Computer generierten Bilder, die durch die Mandelbrot-Menge bekannt wurden, definieren Farben für die Anzahl von Iterationen, die benötigt werden, um festzustellen, das sich ein Punkt außerhalb der Menge befindet.)</span><span class="sxs-lookup"><span data-stu-id="50003-167">(The computer generated images popularized for the Mandelbrot set define colors for the number of iterations necessary to determine that a point is outside the set.</span></span>

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

<span data-ttu-id="50003-168">Die Mandelbrot-Menge definiert Werte an jeder (x, y)-Koordinaten für reelle Zahlenwerte.</span><span class="sxs-lookup"><span data-stu-id="50003-168">The Mandelbrot Set defines values at every (x,y) coordinate for real number values.</span></span>
<span data-ttu-id="50003-169">Dadurch wird ein Wörterbuch definiert, das eine unendliche Anzahl von Werten enthalten könnte.</span><span class="sxs-lookup"><span data-stu-id="50003-169">That defines a dictionary that could contain an infinite number of values.</span></span> <span data-ttu-id="50003-170">Deshalb liegt kein Speicher hinter der Menge.</span><span class="sxs-lookup"><span data-stu-id="50003-170">Therefore, there is no storage behind the set.</span></span> <span data-ttu-id="50003-171">Stattdessen berechnet diese Klasse den Wert für jeden Punkt, wenn die `get`-Zugriffsmethode von Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="50003-171">Instead, this class computes the value for each point when code calls the `get` accessor.</span></span> <span data-ttu-id="50003-172">Es wird kein zugrundeliegender Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="50003-172">There's no underlying storage used.</span></span>

<span data-ttu-id="50003-173">Hier ist ein letztes Beispiel für den Gebrauch von Indexern, in dem der Indexer mehrere Argumente mit unterschiedlichen Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="50003-173">Let's examine one last use of indexers, where the indexer takes multiple arguments of different types.</span></span> <span data-ttu-id="50003-174">Stellen Sie sich ein Programm vor, dass Daten zu historischen Temperaturen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="50003-174">Consider a program that manages historical temperature data.</span></span> <span data-ttu-id="50003-175">Dieser Indexer verwendet eine Stadt und ein Datum, um die höchste und niedrigste Temperatur für diesen Ort festzulegen oder abzurufen:</span><span class="sxs-lookup"><span data-stu-id="50003-175">This indexer uses a city and a date to set or get the high and low temperatures for that location:</span></span>

```csharp
using DateMeasurements = 
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = 
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

<span data-ttu-id="50003-176">In diesem Beispiel wird ein Indexer erstellt, der Wetterdaten zwei Argumenten zuordnet: eine Stadt (repräsentiert durch `string`) und ein Datum (repräsentiert durch `DateTime`).</span><span class="sxs-lookup"><span data-stu-id="50003-176">This example creates an indexer that maps weather data on two different arguments: a city (represented by a `string`) and a date (represented by a `DateTime`).</span></span> <span data-ttu-id="50003-177">Der interne Speicher verwendet zwei `Dictionary`-Klassen, die das zweidimensionale Wörterbuch repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="50003-177">The internal storage uses two `Dictionary` classes to represent the two-dimensional dictionary.</span></span> <span data-ttu-id="50003-178">Die öffentliche API repräsentiert nicht mehr den zugrundeliegenden Speicher.</span><span class="sxs-lookup"><span data-stu-id="50003-178">The public API no longer represents the underlying storage.</span></span> <span data-ttu-id="50003-179">Stattdessen können Sie mit den Sprachfunktionen der Indexer eine öffentliche Schnittstelle erstellen, die Ihre Abstraktion repräsentiert, auch wenn der zugrundeliegende Speicher unterschiedliche Kernauflistungstypen verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="50003-179">Rather, the language features of indexers enables you to create a public interface that represents your abstraction, even though the underlying storage must use different core collection types.</span></span>

<span data-ttu-id="50003-180">Es gibt zwei Teile dieses Codes, die Entwicklern möglicherweise unbekannt sind.</span><span class="sxs-lookup"><span data-stu-id="50003-180">There are two parts of this code that may be unfamiliar to some developers.</span></span> <span data-ttu-id="50003-181">Diese zwei `using`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="50003-181">These two `using` statements:</span></span>

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

<span data-ttu-id="50003-182">erstellen einen *Alias* für einen konstruierter generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="50003-182">create an *alias* for a constructed generic type.</span></span> <span data-ttu-id="50003-183">Durch diese Anweisungen kann ein Code später die deskriptiveren Namen `DateMeasurements` und `CityDateMeasurements` statt der generischen Konstruktion von `Dictionary<DateTime, Measurements>` und `Dictionary<string, Dictionary<DateTime, Measurements> >` verwenden.</span><span class="sxs-lookup"><span data-stu-id="50003-183">Those statements enable the code later to use the more descriptive `DateMeasurements` and `CityDateMeasurements` names instead of the generic construction of `Dictionary<DateTime, Measurements>` and `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span></span> <span data-ttu-id="50003-184">Diese Konstruktion erfordert den Gebrauch des vollqualifizierten Typnamens auf der rechten Seite des `=`-Zeichens.</span><span class="sxs-lookup"><span data-stu-id="50003-184">This construct does require using the fully qualified type names on the right side of the `=` sign.</span></span>

<span data-ttu-id="50003-185">In der zweiten Vorgehensweise entfernen Sie die Uhrzeitteile jedes `DateTime`-Objekts, das verwendet wird, um in die Auflistungen zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="50003-185">The second technique is to strip off the time portions of any `DateTime` object used to index into the collections.</span></span> <span data-ttu-id="50003-186">Das .NET Framework enthält keinen „Date only“-Typ.</span><span class="sxs-lookup"><span data-stu-id="50003-186">The .NET framework does not include a Date only type.</span></span>
<span data-ttu-id="50003-187">Entwickler verwenden den `DateTime`-Typ, aber die `Date`-Eigenschaft, um sicherzustellen, das jedes `DateTime`-Objekt dieses Tages gleich ist.</span><span class="sxs-lookup"><span data-stu-id="50003-187">Developers use the `DateTime` type, but use the `Date` property to ensure that any `DateTime` object from that day are equal.</span></span>

## <a name="summing-up"></a><span data-ttu-id="50003-188">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="50003-188">Summing Up</span></span>

<span data-ttu-id="50003-189">Sie sollten Indexer immer dann erstellen, wenn Sie ein Element, das einer Eigenschaft ähnelt, in Ihrer Klasse vorliegen haben, und wenn diese Eigenschaft nicht einen einzelnen Wert repräsentiert, sondern eine Auflistung von Werten, in der jedes einzelne Element durch einen Satz von Argumenten identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="50003-189">You should create indexers anytime you have a property-like element in your class where that property represents not a single value, but rather a collection of values where each individual item is identified by a set of arguments.</span></span> <span data-ttu-id="50003-190">Diese Argumente können eindeutig identifizieren, auf welches Element in der Auflistung verwiesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="50003-190">Those arguments can uniquely identify which item in the collection should be referenced.</span></span>
<span data-ttu-id="50003-191">Indexer erweitern das Konzept der [Eigenschaften](properties.md), wo ein Member außerhalb der Klasse nicht wie ein Datenelement behandelt wird, sondern wie eine Methode von innen.</span><span class="sxs-lookup"><span data-stu-id="50003-191">Indexers extend the concept of [properties](properties.md), where a member is treated like a data item from outside the class, but like a method on the side.</span></span> <span data-ttu-id="50003-192">Indexer ermöglichen es Argumenten, ein einzelnes Element in einer Eigenschaft zu finden, das einen Satz von Elementen repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="50003-192">Indexers allow arguments to find a single item in a property that represents a set of items.</span></span>

