---
title: Indexer
description: Erfahren Sie mehr über C#-Indexer und wie sie indizierte Eigenschaften, d.h. Eigenschaften, auf die mit mindestens einem Argument verwiesen wird, implementieren.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: 1369740404c500d8b44b4706959bf4640c26aa2d
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656110"
---
# <a name="indexers"></a><span data-ttu-id="ee1f9-103">Indexer</span><span class="sxs-lookup"><span data-stu-id="ee1f9-103">Indexers</span></span>

<span data-ttu-id="ee1f9-104">*Indexer* sind ähnlich wie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-104">*Indexers* are similar to properties.</span></span> <span data-ttu-id="ee1f9-105">In vielen Aspekten bauen Indexer genauso wie [Eigenschaften](properties.md) auf den gleichen Sprachfunktionen auf.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-105">In many ways indexers build on the same language features as [properties](properties.md).</span></span> <span data-ttu-id="ee1f9-106">Indexer ermöglichen *indizierte* Eigenschaften: Eigenschaften, auf die von mindestens einem Argument verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-106">Indexers enable *indexed* properties: properties referenced using one or more arguments.</span></span> <span data-ttu-id="ee1f9-107">Diese Argumente stellen einen Index in einer Auflistung von Werten bereit.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-107">Those arguments provide an index into some collection of values.</span></span>

## <a name="indexer-syntax"></a><span data-ttu-id="ee1f9-108">Indexersyntax</span><span class="sxs-lookup"><span data-stu-id="ee1f9-108">Indexer Syntax</span></span>

<span data-ttu-id="ee1f9-109">Sie können mithilfe eines Variablennamens und eckiger Klammern auf einen Indexer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-109">You access an indexer through a variable name and square brackets.</span></span> <span data-ttu-id="ee1f9-110">Geben Sie die Indexerargumente innerhalb der Klammern ein:</span><span class="sxs-lookup"><span data-stu-id="ee1f9-110">You place the indexer arguments inside the brackets:</span></span>

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

<span data-ttu-id="ee1f9-111">Sie können Indexer deklarieren, in dem sie das Schlüsselwort `this` als Eigenschaftenname verwenden und die Argumente in eckigen Klammern deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-111">You declare indexers using the `this` keyword as the property name, and declaring the arguments within square brackets.</span></span> <span data-ttu-id="ee1f9-112">Diese Deklaration stimmt mit dem Gebrauch in oben stehendem Abschnitt überein:</span><span class="sxs-lookup"><span data-stu-id="ee1f9-112">This declaration would match the usage shown in the previous paragraph:</span></span>

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

<span data-ttu-id="ee1f9-113">Dieses erste Beispiel veranschaulicht die Beziehung zwischen der Syntax der Eigenschaften und der Indexer.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-113">From this initial example, you can see the relationship between the syntax for properties and for indexers.</span></span> <span data-ttu-id="ee1f9-114">Diese Analogie wirkt sich auf die meisten Syntaxregeln für Indexer auf.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-114">This analogy carries through most of the syntax rules for indexers.</span></span> <span data-ttu-id="ee1f9-115">Indexer können beliebige gültige Zugriffsmodifizierer aufweisen (public, protected internal, protected, internal, private oder private protected).</span><span class="sxs-lookup"><span data-stu-id="ee1f9-115">Indexers can have any valid access modifiers (public, protected internal, protected, internal, private or private protected).</span></span> <span data-ttu-id="ee1f9-116">Sie können versiegelt, virtuell oder abstrakt sein.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-116">They may be sealed, virtual, or abstract.</span></span> <span data-ttu-id="ee1f9-117">Bei Eigenschaften können Sie verschiedene Zugriffsmodifizierer für die Get- und Set-Accessoren eines Indexers angeben.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-117">As with properties, you can specify different access modifiers for the get and set accessors in an indexer.</span></span>
<span data-ttu-id="ee1f9-118">Außerdem können Sie schreibgeschützte Indexer (indem Sie die set-Zugriffsmethode auslassen) oder lesegeschützte Indexer (indem Sie die get-Zugriffsmethode auslassen) angeben.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-118">You may also specify read-only indexers (by omitting the set accessor), or write-only indexers (by omitting the get accessor).</span></span>

<span data-ttu-id="ee1f9-119">Fast alles, was Sie von der Arbeit mit Eigenschaften kennen, können sie auch für Indexer anwenden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-119">You can apply almost everything you learn from working with properties to indexers.</span></span> <span data-ttu-id="ee1f9-120">Die einzige Ausnahme von dieser Regel sind *automatisch implementierte Eigenschaften*.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-120">The only exception to that rule is *auto implemented properties*.</span></span> <span data-ttu-id="ee1f9-121">Der Compiler kann nicht immer angemessenen Speicher für einen Indexer generieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-121">The compiler cannot always generate the correct storage for an indexer.</span></span>

<span data-ttu-id="ee1f9-122">Indexer unterscheiden sich durch das Vorhandensein von Argumenten, die auf ein Element in einem Satz von Elementen verweisen, von Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-122">The presence of arguments to reference an item in a set of items distinguishes indexers from properties.</span></span> <span data-ttu-id="ee1f9-123">Sie können mehrere Indexer in einem Typ definieren, solange die Argumentauflistung für jeden Indexer eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-123">You may define multiple indexers on a type, as long as the argument lists for each indexer is unique.</span></span> <span data-ttu-id="ee1f9-124">In den folgenden Szenarios erfahren Sie mehr über das Verwenden von einem oder mehreren Indexern in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-124">Let's explore different scenarios where you might use one or more indexers in a class definition.</span></span>

## <a name="scenarios"></a><span data-ttu-id="ee1f9-125">Szenarien</span><span class="sxs-lookup"><span data-stu-id="ee1f9-125">Scenarios</span></span>

<span data-ttu-id="ee1f9-126">Sie definieren *Indexer* in Ihrem Typ, wenn dessen API eine Auflistung modelliert, in der Sie die Argumente der Auflistung definieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-126">You would define *indexers* in your type when its API models some collection where you define the arguments to that collection.</span></span> <span data-ttu-id="ee1f9-127">Ihre Indexer ordnen möglicherweise direkt zu Ihren Auflistungstypen zu, die Teil des .NET Core Frameworks sind.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-127">Your indexers may or may not map directly to the collection types that are part of the .NET core framework.</span></span> <span data-ttu-id="ee1f9-128">Ihr Typ hat möglicherweise andere Verpflichtungen als nur das Modellieren einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-128">Your type may have other responsibilities in addition to modeling a collection.</span></span>
<span data-ttu-id="ee1f9-129">Mit Indexern können Sie die API bereitstellen, die mit der Abstraktion Ihres Typs übereinstimmt, ohne die inneren Details offen zu legen, wie die Werte dieser Abstraktion gespeichert oder berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-129">Indexers enable you to provide the API that matches your type's abstraction without exposing the inner details of how the values for that abstraction are stored or computed.</span></span>

<span data-ttu-id="ee1f9-130">Die häufigsten Szenarios für das Verwenden von *Indexern*.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-130">Let's walk through some of the common scenarios for using *indexers*.</span></span> <span data-ttu-id="ee1f9-131">Sie können auf den [Beispielordner für Indexer](https://github.com/dotnet/samples/tree/master/csharp/indexers) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-131">You can access the [sample folder for indexers](https://github.com/dotnet/samples/tree/master/csharp/indexers).</span></span> <span data-ttu-id="ee1f9-132">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="ee1f9-132">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

### <a name="arrays-and-vectors"></a><span data-ttu-id="ee1f9-133">Arrays und Vektoren</span><span class="sxs-lookup"><span data-stu-id="ee1f9-133">Arrays and Vectors</span></span>

<span data-ttu-id="ee1f9-134">Eines der häufigsten Szenarios beim Erstellen von Indexern ist, wenn Ihr Typ ein Array oder einen Vektor modelliert.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-134">One of the most common scenarios for creating indexers is when your type models an array, or a vector.</span></span> <span data-ttu-id="ee1f9-135">Sie können einen Indexer erstellen, um eine geordnete Datenliste zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-135">You can create an indexer to model an ordered list of data.</span></span>

<span data-ttu-id="ee1f9-136">Der Vorteil beim Erstellen eines eigenen Indexers ist die Tatsache, dass Sie den Speicher für diese Auflistung an Ihre Bedürfnisse anpassen können.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-136">The advantage of creating your own indexer is that you can define the storage for that collection to suit your needs.</span></span> <span data-ttu-id="ee1f9-137">Stellen Sie sich ein Szenario vor, in dem Ihr Typ historische Daten modelliert, die zu groß sind, um sie auf einmal in den Speicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-137">Imagine a scenario where your type models historical data that is too large to load into memory at once.</span></span> <span data-ttu-id="ee1f9-138">Sie müssen Abschnitte der Auflistung nach Verbrauch laden und entladen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-138">You need to load and unload sections of the collection based on usage.</span></span> <span data-ttu-id="ee1f9-139">Das folgende Beispiel veranschaulicht dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-139">The example following models this behavior.</span></span> <span data-ttu-id="ee1f9-140">Es meldet, wie viele Datenpunkte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-140">It reports on how many data points exist.</span></span> <span data-ttu-id="ee1f9-141">Es erstellt Seiten, die auf Abruf Abschnitte der Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-141">It creates pages to hold sections of the data on demand.</span></span> <span data-ttu-id="ee1f9-142">Es entfernt Seiten aus dem Speicher, um Platz für Seiten zu schaffen, die für eine aktuelle Abfrage benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-142">It removes pages from memory to make room for pages needed by more recent requests.</span></span>

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

<span data-ttu-id="ee1f9-143">Sie können diesem Entwurfsausdruck folgen, um jede beliebige Auflistungsart dort zu modellieren, wo es gute Gründe gibt, nicht den gesamten Datensatz in eine Auflistung im Speicher zu laden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-143">You can follow this design idiom to model any sort of collection where there are good reasons not to load the entire set of data into an in- memory collection.</span></span> <span data-ttu-id="ee1f9-144">Beachten Sie, dass die Klasse `Page` eine private geschachtelte Klasse ist, die nicht Teil der öffentlichen Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-144">Notice that the `Page` class is a private nested class that is not part of the public interface.</span></span> <span data-ttu-id="ee1f9-145">Diese Informationen sind für jeden Benutzer der Klasse verborgen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-145">Those details are hidden from any users of this class.</span></span>

### <a name="dictionaries"></a><span data-ttu-id="ee1f9-146">Wörterbücher</span><span class="sxs-lookup"><span data-stu-id="ee1f9-146">Dictionaries</span></span>

<span data-ttu-id="ee1f9-147">Ein weiteres häufiges Szenario ist, wenn Sie ein Wörterbuch oder eine Zuordnung modellieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-147">Another common scenario is when you need to model a dictionary or a map.</span></span> <span data-ttu-id="ee1f9-148">In diesem Szenario speichert Ihr Typ Werte nach Schlüsseln, typischerweise Textschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-148">This scenario is when your type stores values based on key, typically text keys.</span></span> <span data-ttu-id="ee1f9-149">In diesem Beispiel wird ein Wörterbuch erstellt, das Befehlszeilenargumente [Lambdaausdrücken](delegates-overview.md) zuordnet, die diese Optionen verwalten.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-149">This example creates a dictionary that maps command line arguments to [lambda expressions](delegates-overview.md) that manage those options.</span></span> <span data-ttu-id="ee1f9-150">In folgenden Beispiel werden zwei Klassen gezeigt: eine `ArgsActions`-Klasse, die eine Befehlszeilenoption einem `Action`-Delegaten zuordnet, und ein `ArgsProcessor`, um mit jeder `ArgsActions` eine `Action` auszuführen, wenn es auf diese Option trifft.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-150">The following example shows two classes: an `ArgsActions` class that maps a command line option to an `Action` delegate, and an `ArgsProcessor` that uses the `ArgsActions` to execute each `Action` when it encounters that option.</span></span>

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

<span data-ttu-id="ee1f9-151">In diesem Beispiel ordnet die `ArgsAction`-Auflistung nah an der zugrundeliegenden Auflistung zu.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-151">In this example, the `ArgsAction` collection maps closely to the underlying collection.</span></span>
<span data-ttu-id="ee1f9-152">`get` legt fest, ob eine gegebene Option konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-152">The `get` determines if a given option has been configured.</span></span> <span data-ttu-id="ee1f9-153">Falls dem so ist, gibt es die mit dieser Option verknüpfte `Action` zurück.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-153">If so, it returns the `Action` associated with that option.</span></span> <span data-ttu-id="ee1f9-154">Falls dem nicht so ist, gibt es eine `Action` zurück, die keine Auswirkungen hat.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-154">If not, it returns an `Action` that does nothing.</span></span> <span data-ttu-id="ee1f9-155">Die öffentliche Zugriffsmethode enthält keine `set`-Zugriffsmethode.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-155">The public accessor does not include a `set` accessor.</span></span> <span data-ttu-id="ee1f9-156">Stattdessen enthält Sie den Entwurf, der eine öffentliche Methode für das Festlegen von Optionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-156">Rather, the design using a public method for setting options.</span></span>

### <a name="multi-dimensional-maps"></a><span data-ttu-id="ee1f9-157">Mehrdimensionale Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="ee1f9-157">Multi-Dimensional Maps</span></span>

<span data-ttu-id="ee1f9-158">Sie können Indexer erstellen, die mehrere Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-158">You can create indexers that use multiple arguments.</span></span> <span data-ttu-id="ee1f9-159">Zusätzlich sind müssen diese Argumente nicht denselben Typen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-159">In addition, those arguments are not constrained to be the same type.</span></span> <span data-ttu-id="ee1f9-160">Nachfolgend sehen Sie zwei Beispiele.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-160">Let's look at two examples.</span></span>

<span data-ttu-id="ee1f9-161">Das erste Beispiel zeigt eine Klasse, die Werte einer Mandelbrot-Menge generiert.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-161">The first example shows a class that generates values for a Mandelbrot set.</span></span> <span data-ttu-id="ee1f9-162">Weitere Informationen zur Mathematik der Menge finden Sie in [diesem Artikel](https://en.wikipedia.org/wiki/Mandelbrot_set).</span><span class="sxs-lookup"><span data-stu-id="ee1f9-162">For more information on the mathematics behind the set, read [this article](https://en.wikipedia.org/wiki/Mandelbrot_set).</span></span>
<span data-ttu-id="ee1f9-163">Der Indexer verwendet zwei double-Werte, um einen Punkt auf der X-Y-Ebene zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-163">The indexer uses two doubles to define a point in the X, Y plane.</span></span>
<span data-ttu-id="ee1f9-164">Die get-Zugriffsmethode berechnet die Anzahl der Iterationen, bis ein Punkt festgelegt wird, der außerhalb der Menge liegt.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-164">The get accessor computes the number of iterations until a point is determined to be not in the set.</span></span> <span data-ttu-id="ee1f9-165">Wenn die maximale Zahl an Iterationen erreicht ist, befindet sich der Punkt in der Menge, und der Wert „maxIterations“ der Klasse wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-165">If the maximum iterations is reached, the point is in the set, and the class's maxIterations value is returned.</span></span> <span data-ttu-id="ee1f9-166">(Die vom Computer generierten Bilder, die durch die Mandelbrot-Menge bekannt wurden, definieren Farben für die Anzahl von Iterationen, die benötigt werden, um festzustellen, das sich ein Punkt außerhalb der Menge befindet.)</span><span class="sxs-lookup"><span data-stu-id="ee1f9-166">(The computer generated images popularized for the Mandelbrot set define colors for the number of iterations necessary to determine that a point is outside the set.</span></span>

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

<span data-ttu-id="ee1f9-167">Die Mandelbrot-Menge definiert Werte an jeder (x, y)-Koordinaten für reelle Zahlenwerte.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-167">The Mandelbrot Set defines values at every (x,y) coordinate for real number values.</span></span>
<span data-ttu-id="ee1f9-168">Dadurch wird ein Wörterbuch definiert, das eine unendliche Anzahl von Werten enthalten könnte.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-168">That defines a dictionary that could contain an infinite number of values.</span></span> <span data-ttu-id="ee1f9-169">Deshalb liegt kein Speicher hinter der Menge.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-169">Therefore, there is no storage behind the set.</span></span> <span data-ttu-id="ee1f9-170">Stattdessen berechnet diese Klasse den Wert für jeden Punkt, wenn die `get`-Zugriffsmethode von Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-170">Instead, this class computes the value for each point when code calls the `get` accessor.</span></span> <span data-ttu-id="ee1f9-171">Es wird kein zugrundeliegender Speicher verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-171">There's no underlying storage used.</span></span>

<span data-ttu-id="ee1f9-172">Hier ist ein letztes Beispiel für den Gebrauch von Indexern, in dem der Indexer mehrere Argumente mit unterschiedlichen Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-172">Let's examine one last use of indexers, where the indexer takes multiple arguments of different types.</span></span> <span data-ttu-id="ee1f9-173">Stellen Sie sich ein Programm vor, dass Daten zu historischen Temperaturen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-173">Consider a program that manages historical temperature data.</span></span> <span data-ttu-id="ee1f9-174">Dieser Indexer verwendet eine Stadt und ein Datum, um die höchste und niedrigste Temperatur für diesen Ort festzulegen oder abzurufen:</span><span class="sxs-lookup"><span data-stu-id="ee1f9-174">This indexer uses a city and a date to set or get the high and low temperatures for that location:</span></span>

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

<span data-ttu-id="ee1f9-175">In diesem Beispiel wird ein Indexer erstellt, der Wetterdaten zwei Argumenten zuordnet: eine Stadt (repräsentiert durch `string`) und ein Datum (repräsentiert durch `DateTime`).</span><span class="sxs-lookup"><span data-stu-id="ee1f9-175">This example creates an indexer that maps weather data on two different arguments: a city (represented by a `string`) and a date (represented by a `DateTime`).</span></span> <span data-ttu-id="ee1f9-176">Der interne Speicher verwendet zwei `Dictionary`-Klassen, die das zweidimensionale Wörterbuch repräsentieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-176">The internal storage uses two `Dictionary` classes to represent the two-dimensional dictionary.</span></span> <span data-ttu-id="ee1f9-177">Die öffentliche API repräsentiert nicht mehr den zugrundeliegenden Speicher.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-177">The public API no longer represents the underlying storage.</span></span> <span data-ttu-id="ee1f9-178">Stattdessen können Sie mit den Sprachfunktionen der Indexer eine öffentliche Schnittstelle erstellen, die Ihre Abstraktion repräsentiert, auch wenn der zugrundeliegende Speicher unterschiedliche Kernauflistungstypen verwenden muss.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-178">Rather, the language features of indexers enables you to create a public interface that represents your abstraction, even though the underlying storage must use different core collection types.</span></span>

<span data-ttu-id="ee1f9-179">Es gibt zwei Teile dieses Codes, die Entwicklern möglicherweise unbekannt sind.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-179">There are two parts of this code that may be unfamiliar to some developers.</span></span> <span data-ttu-id="ee1f9-180">Diese beiden `using`-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="ee1f9-180">These two `using` directives:</span></span>

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

<span data-ttu-id="ee1f9-181">erstellen einen *Alias* für einen konstruierter generischen Typen.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-181">create an *alias* for a constructed generic type.</span></span> <span data-ttu-id="ee1f9-182">Durch diese Anweisungen kann ein Code später die deskriptiveren Namen `DateMeasurements` und `CityDateMeasurements` statt der generischen Konstruktion von `Dictionary<DateTime, Measurements>` und `Dictionary<string, Dictionary<DateTime, Measurements> >` verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-182">Those statements enable the code later to use the more descriptive `DateMeasurements` and `CityDateMeasurements` names instead of the generic construction of `Dictionary<DateTime, Measurements>` and `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span></span>
<span data-ttu-id="ee1f9-183">Diese Konstruktion erfordert den Gebrauch des vollqualifizierten Typnamens auf der rechten Seite des `=`-Zeichens.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-183">This construct does require using the fully qualified type names on the right side of the `=` sign.</span></span>

<span data-ttu-id="ee1f9-184">In der zweiten Vorgehensweise entfernen Sie die Uhrzeitteile jedes `DateTime`-Objekts, das verwendet wird, um in die Auflistungen zu indizieren.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-184">The second technique is to strip off the time portions of any `DateTime` object used to index into the collections.</span></span> <span data-ttu-id="ee1f9-185">.NET bietet keinen reinen Datumstyp.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-185">.NET doesn't include a date-only type.</span></span>
<span data-ttu-id="ee1f9-186">Entwickler verwenden den `DateTime`-Typ, aber die `Date`-Eigenschaft, um sicherzustellen, das jedes `DateTime`-Objekt dieses Tages gleich ist.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-186">Developers use the `DateTime` type, but use the `Date` property to ensure that any `DateTime` object from that day are equal.</span></span>

## <a name="summing-up"></a><span data-ttu-id="ee1f9-187">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="ee1f9-187">Summing Up</span></span>

<span data-ttu-id="ee1f9-188">Sie sollten Indexer immer dann erstellen, wenn Sie ein Element, das einer Eigenschaft ähnelt, in Ihrer Klasse vorliegen haben, und wenn diese Eigenschaft nicht einen einzelnen Wert repräsentiert, sondern eine Auflistung von Werten, in der jedes einzelne Element durch einen Satz von Argumenten identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-188">You should create indexers anytime you have a property-like element in your class where that property represents not a single value, but rather a collection of values where each individual item is identified by a set of arguments.</span></span> <span data-ttu-id="ee1f9-189">Diese Argumente können eindeutig identifizieren, auf welches Element in der Auflistung verwiesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-189">Those arguments can uniquely identify which item in the collection should be referenced.</span></span>
<span data-ttu-id="ee1f9-190">Indexer erweitern das Konzept der [Eigenschaften](properties.md), bei denen ein Member wie ein Datenelement außerhalb der Klasse behandelt wird, sondern wie eine Methode innerhalb der Klasse.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-190">Indexers extend the concept of [properties](properties.md), where a member is treated like a data item from outside the class, but like a method on the inside.</span></span> <span data-ttu-id="ee1f9-191">Indexer ermöglichen es Argumenten, ein einzelnes Element in einer Eigenschaft zu finden, das einen Satz von Elementen repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="ee1f9-191">Indexers allow arguments to find a single item in a property that represents a set of items.</span></span>
