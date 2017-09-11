---
title: LINQ (Language Integrated Query)
description: "LINQ bietet Abfragefunktionen auf Sprachebene und eine API für C# und VB, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben."
keywords: .NET, .NET Core
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.translationtype: HT
ms.sourcegitcommit: ef6d1bf9a7153f7adf635d13b4dcfb7647ed2e33
ms.openlocfilehash: 1478b5dc5844cef0abfea44eba88a12801d32bd4
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---

# <a name="linq-language-integrated-query"></a><span data-ttu-id="b4401-104">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="b4401-104">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="b4401-105">Was ist das?</span><span class="sxs-lookup"><span data-stu-id="b4401-105">What is it?</span></span>

<span data-ttu-id="b4401-106">LINQ bietet Abfragefunktionen auf Sprachebene und eine API einer [Funktion höherer Ordnung](https://en.wikipedia.org/wiki/Higher-order_function) für C# und VB, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b4401-106">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and VB as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="b4401-107">Abfragesyntax auf Sprachebene:</span><span class="sxs-lookup"><span data-stu-id="b4401-107">Language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

<span data-ttu-id="b4401-108">Gleiches Beispiel mit der `IEnumerable<T>`-API:</span><span class="sxs-lookup"><span data-stu-id="b4401-108">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a><span data-ttu-id="b4401-109">LINQ ist ausdrucksstark</span><span class="sxs-lookup"><span data-stu-id="b4401-109">LINQ is Expressive</span></span>

<span data-ttu-id="b4401-110">Nehmen Sie an, Sie haben eine Liste mit Haustieren, möchten diese aber in ein Wörterbuch konvertieren, damit Sie direkt über den `RFID`-Wert auf ein Haustier zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="b4401-110">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="b4401-111">Herkömmlicher imperativer Code:</span><span class="sxs-lookup"><span data-stu-id="b4401-111">Traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

<span data-ttu-id="b4401-112">Der Zweck des Codes ist nicht, ein neues `Dictionary<int, Pet>` zu erstellen und es über eine Schleife zu erweitern, sondern eine vorhandene Liste in ein Wörterbuch zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b4401-112">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="b4401-113">Mit LINQ bleibt dieser Zweck erhalten, mit imperativem Code hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="b4401-113">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="b4401-114">Entsprechender LINQ-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="b4401-114">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

<span data-ttu-id="b4401-115">Der Code mit LINQ ist hilfreich, da er aus der Perspektive eines Programmierers einen Ausgleich zwischen Zweck und Code schafft.</span><span class="sxs-lookup"><span data-stu-id="b4401-115">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="b4401-116">Ein weiter Bonus ist die Kürze des Codes.</span><span class="sxs-lookup"><span data-stu-id="b4401-116">Another bonus is code brevity.</span></span> <span data-ttu-id="b4401-117">Stellen Sie sich vor, Sie könnten große Teile einer Codebasis um 1/3 reduzieren, wie oben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b4401-117">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="b4401-118">Klingt das nicht überzeugend?</span><span class="sxs-lookup"><span data-stu-id="b4401-118">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="b4401-119">LINQ-Anbieter vereinfachen den Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="b4401-119">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="b4401-120">Für einen erheblichen Teil der verwendeten Software dreht sich alles um den Umgang mit Daten aus unterschiedlichen Quellen (Datenbanken, JSON, XML usw.).</span><span class="sxs-lookup"><span data-stu-id="b4401-120">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="b4401-121">Häufig gehört dazu das Erlernen einer neuen API für jede Datenquelle, was lästig sein kann.</span><span class="sxs-lookup"><span data-stu-id="b4401-121">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="b4401-122">LINQ vereinfacht dies durch das Abstrahieren gemeinsamer Elemente des Datenzugriffs in eine Abfragesyntax, die immer gleich aussieht, unabhängig davon, welche Datenquelle Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="b4401-122">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="b4401-123">Stellen Sie sich Folgendes vor: Sie möchten alle XML-Elemente mit einem bestimmten Attributwert finden.</span><span class="sxs-lookup"><span data-stu-id="b4401-123">Consider the following: finding all XML elements with a specific attribute value.</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

<span data-ttu-id="b4401-124">Code zu schreiben, um das XML-Dokument zu diesem Zweck manuell zu durchlaufen, wäre eine wesentlich größere Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="b4401-124">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="b4401-125">LINQ-Anbieter ermöglichen nicht nur die Interaktion mit XML.</span><span class="sxs-lookup"><span data-stu-id="b4401-125">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="b4401-126">[LINQ to SQL](https://msdn.microsoft.com/library/bb386976.aspx) ist ein ziemlich reduzierter objektrelationaler Mapper (ORM) für eine MSSQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b4401-126">[Linq to SQL](https://msdn.microsoft.com/library/bb386976.aspx) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="b4401-127">Die [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm)-Bibliothek bietet einen effizienten Durchlauf von JSON-Dokumenten über LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4401-127">The [JSON.NET](http://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="b4401-128">Wenn es allerdings keine Bibliothek gibt, die Ihre Anforderungen erfüllt, können Sie auch [Ihren eigenen LINQ-Anbieter schreiben](https://msdn.microsoft.com/library/Bb546158.aspx).</span><span class="sxs-lookup"><span data-stu-id="b4401-128">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://msdn.microsoft.com/library/Bb546158.aspx)!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="b4401-129">Warum sollte die Abfragesyntax verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="b4401-129">Why Use the Query Syntax?</span></span>

<span data-ttu-id="b4401-130">Dies ist eine Frage, die häufig gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b4401-130">This is a question which often comes up.</span></span> <span data-ttu-id="b4401-131">Im Grunde ist dies:</span><span class="sxs-lookup"><span data-stu-id="b4401-131">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

<span data-ttu-id="b4401-132">sehr viel präziser als dies:</span><span class="sxs-lookup"><span data-stu-id="b4401-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

<span data-ttu-id="b4401-133">Ist die API-Syntax nicht nur eine präzisere Methode für die Abfragesyntax?</span><span class="sxs-lookup"><span data-stu-id="b4401-133">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="b4401-134">Nein.</span><span class="sxs-lookup"><span data-stu-id="b4401-134">No.</span></span> <span data-ttu-id="b4401-135">Die Abfragesyntax ermöglicht die Verwendung der **let**-Klausel, mit der Sie eine Variable im Bereich des Ausdrucks einführen und binden können, um sie in nachfolgenden Teilen des Ausdrucks zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4401-135">The query syntax allows for the use the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="b4401-136">Das Reproduzieren des gleichen Codes nur mit der API-Syntax ist möglich, führt jedoch wahrscheinlich zu Code, der schwer lesbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4401-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="b4401-137">Daher stellt sich die folgende Frage: **Sollten Sie einfach die Abfragesyntax verwenden?**</span><span class="sxs-lookup"><span data-stu-id="b4401-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="b4401-138">Die Antwort auf diese Frage ist **Ja**, wenn...</span><span class="sxs-lookup"><span data-stu-id="b4401-138">The answer to this question is **yes** if...</span></span>

*   <span data-ttu-id="b4401-139">Ihre vorhandene Codebasis bereits die Abfragesyntax verwendet</span><span class="sxs-lookup"><span data-stu-id="b4401-139">Your existing codebase already uses the query syntax</span></span>
*   <span data-ttu-id="b4401-140">Sie den Bereich von Variablen in Ihren Abfragen aufgrund der Komplexität festlegen müssen</span><span class="sxs-lookup"><span data-stu-id="b4401-140">You need to scope variables within your queries due to complexity</span></span>
*   <span data-ttu-id="b4401-141">Sie die Abfragesyntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden</span><span class="sxs-lookup"><span data-stu-id="b4401-141">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="b4401-142">Die Antwort auf diese Frage ist **Nein**, wenn...</span><span class="sxs-lookup"><span data-stu-id="b4401-142">The answer to this question is **no** if...</span></span>

*   <span data-ttu-id="b4401-143">Ihre vorhandene Codebasis die API-Syntax bereits verwendet</span><span class="sxs-lookup"><span data-stu-id="b4401-143">Your existing codebase already uses the API syntax</span></span>
*   <span data-ttu-id="b4401-144">Sie den Bereich von Variablen in Ihren Abfragen nicht festlegen müssen</span><span class="sxs-lookup"><span data-stu-id="b4401-144">You have no need to scope variables within your queries</span></span>
*   <span data-ttu-id="b4401-145">Sie die API-Syntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden</span><span class="sxs-lookup"><span data-stu-id="b4401-145">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="b4401-146">Grundlegende Beispiele</span><span class="sxs-lookup"><span data-stu-id="b4401-146">Essential Samples</span></span>

<span data-ttu-id="b4401-147">Eine umfassende Liste der LINQ-Beispiele finden Sie unter [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 LINQ-Beispiele).</span><span class="sxs-lookup"><span data-stu-id="b4401-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b).</span></span>

<span data-ttu-id="b4401-148">Im Folgenden finden eine kurze Darstellung einiger der grundlegenden Bestandteile von LINQ.</span><span class="sxs-lookup"><span data-stu-id="b4401-148">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="b4401-149">Sie ist bei weitem nicht vollständig, da LINQ erheblich mehr Funktionen bietet, als hier präsentiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4401-149">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

*   <span data-ttu-id="b4401-150">Die Grundbestandteile sind `Where`, `Select` und `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="b4401-150">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
                          select dog;

// Mapping a list from type A to type B
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing then lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   <span data-ttu-id="b4401-151">Reduzieren einer Liste mit Listen:</span><span class="sxs-lookup"><span data-stu-id="b4401-151">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   <span data-ttu-id="b4401-152">Vereinigung von zwei Gruppen (mit benutzerdefiniertem Vergleichsoperator):</span><span class="sxs-lookup"><span data-stu-id="b4401-152">Union between two sets (with custom comparator):</span></span>

```csharp
public class DogHairLengthComparer : IEqualityComparer<Dog>
{
    public bool Equals(Dog a, Dog b)
    {
        if (a == null && b == null)
        {
            return true;
        }
        else if ((a == null && b != null) ||
                 (a != null && b == null))
        {
            return false;
        }
        else
        {
            return a.HairLengthType == b.HairLengthType;
        }
    }

    public int GetHashCode(Dog d)
    {
        // default hashcode is enough here, as these are simple objects.
        return b.GetHashCode();
    }
}

...

// Gets all the short-haired dogs between two different kennels
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());
```

*   <span data-ttu-id="b4401-153">Schnittmenge zwischen zwei Gruppen:</span><span class="sxs-lookup"><span data-stu-id="b4401-153">Intersection between two sets:</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   <span data-ttu-id="b4401-154">Sortierung:</span><span class="sxs-lookup"><span data-stu-id="b4401-154">Ordering:</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   <span data-ttu-id="b4401-155">Schließlich ein erweitertes Beispiel: Ermitteln, ob die Werte der Eigenschaften von zwei Instanzen desselben Typs gleich sind (aus [diesem StackOverflow-Beitrag](http://stackoverflow.com/a/844855) übernommen und geändert):</span><span class="sxs-lookup"><span data-stu-id="b4401-155">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](http://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self != null && to != null)
    {
        var type = typeof(T);
        var ignoreList = new List<string>(ignore);

        // Selects the properties which have unequal values into a sequence of those properties.
        var unequalProperties = from pi in type.GetProperties(BindingFlags.Public | BindingFlags.Instance)
                                where !ignoreList.Contains(pi.Name)
                                let selfValue = type.GetProperty(pi.Name).GetValue(self, null)
                                let toValue = type.GetProperty(pi.Name).GetValue(to, null)
                                where selfValue != toValue && (selfValue == null || !selfValue.Equals(toValue))
                                select new { Prop = pi.Name, selfValue, toValue };
        return !unequalProperties.Any();
    }

    return self == to;
}
```

## <a name="plinq"></a><span data-ttu-id="b4401-156">PLINQ</span><span class="sxs-lookup"><span data-stu-id="b4401-156">PLINQ</span></span>

<span data-ttu-id="b4401-157">PLINQ (Parallel LINQ) ist ein Modul für die parallele Ausführung für LINQ-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="b4401-157">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="b4401-158">Reguläre LINQ-Ausdrücke können also im Grunde über eine beliebige Anzahl von Threads parallelisiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4401-158">In other words, a regular LINQ expressions can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="b4401-159">Dies erfolgt über einen Aufruf von `AsParallel()` vor dem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b4401-159">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="b4401-160">Nehmen wir einmal die folgende Situation:</span><span class="sxs-lookup"><span data-stu-id="b4401-160">Consider the following:</span></span>

```csharp
public static string GetAllFacebookUserLikesMessage(IEnumerable<FacebookUser> facebookUsers)
{
    var seed = default(UInt64);

    Func<UInt64, UInt64, UInt64> threadAccumulator = (t1, t2) => t1 + t2;
    Func<UInt64, UInt64, UInt64> threadResultAccumulator = (t1, t2) => t1 + t2;
    Func<Uint64, string> resultSelector = total => $"Facebook has {total} likes!";

    return facebookUsers.AsParallel()
                        .Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector);
}
```

<span data-ttu-id="b4401-161">Dieser Code partitioniert bei Bedarf `facebookUsers` über Systemthreads, summiert die Gesamtanzahl der „Likes“ parallel für jeden Thread, summiert die von allen Threads berechneten Ergebnisse und bringt das Ergebnis in eine nützliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b4401-161">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="b4401-162">In Diagrammform:</span><span class="sxs-lookup"><span data-stu-id="b4401-162">In diagram form:</span></span>

![PLINQ-Diagramm](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="b4401-164">Parallelisierbare CPU-gebundene Aufträge, die problemlos über LINQ ausgedrückt werden können (die also reine Funktionen ohne Nebeneffekte darstellen) sind gute Kandidaten für PLINQ.</span><span class="sxs-lookup"><span data-stu-id="b4401-164">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="b4401-165">Für Aufträge, die einen Nebeneffekt _haben_, sollten Sie die [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4401-165">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](https://msdn.microsoft.com/library/dd460717.aspx).</span></span>

## <a name="further-resources"></a><span data-ttu-id="b4401-166">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="b4401-166">Further Resources:</span></span>

*   [<span data-ttu-id="b4401-167">101 LINQ-Beispiele</span><span class="sxs-lookup"><span data-stu-id="b4401-167">101 LINQ Samples</span></span>](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   <span data-ttu-id="b4401-168">[Linqpad](https://www.linqpad.net/), eine Umgebung und ein Datenbankabfragemodul für C#/F#/VB</span><span class="sxs-lookup"><span data-stu-id="b4401-168">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/VB</span></span>
*   <span data-ttu-id="b4401-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), ein E-Book, in dem die Implementierung von LINQ to Objects erläutert wird</span><span class="sxs-lookup"><span data-stu-id="b4401-169">[EduLinq](http://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>

