---
title: 'Übersicht über LINQ: .NET'
description: LINQ (Language Integrated Query) bietet Abfragefunktionen auf Sprachebene und eine API einer Funktion höherer Ordnung für C# und Visual Basic, die es Ihnen ermöglichen, aussagekräftigen deklarativen Code zu schreiben.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.openlocfilehash: 65370a2bd21e2474af4cb070bb8d82a167f10070
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554995"
---
# <a name="linq-overview"></a><span data-ttu-id="d3edb-103">Übersicht über LINQ</span><span class="sxs-lookup"><span data-stu-id="d3edb-103">LINQ overview</span></span>

<span data-ttu-id="d3edb-104">LINQ (Language-Integrated Query) bietet Abfragefunktionen auf Sprachebene und eine API einer [Funktion höherer Ordnung](https://en.wikipedia.org/wiki/Higher-order_function) für C# und Visual Basic, die es Ihnen ermöglichen, aussagekräftigen deklarativen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d3edb-104">Language-Integrated Query (LINQ) provides language-level querying capabilities, and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic, that enable you to write expressive declarative code.</span></span>

## <a name="language-level-query-syntax"></a><span data-ttu-id="d3edb-105">Abfragesyntax auf Sprachebene</span><span class="sxs-lookup"><span data-stu-id="d3edb-105">Language-level query syntax</span></span>

<span data-ttu-id="d3edb-106">Dies ist die Abfragesyntax auf Sprachebene:</span><span class="sxs-lookup"><span data-stu-id="d3edb-106">This is the language-level query syntax:</span></span>

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

```vb
Dim linqExperts = From p in programmers
                  Where p.IsNewToLINQ
                  Select New LINQExpert(p)
```

<span data-ttu-id="d3edb-107">Dies ist das gleiche Beispiel mit der `IEnumerable<T>`-API:</span><span class="sxs-lookup"><span data-stu-id="d3edb-107">This is the same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="d3edb-108">LINQ ist ausdrucksstark</span><span class="sxs-lookup"><span data-stu-id="d3edb-108">LINQ is expressive</span></span>

<span data-ttu-id="d3edb-109">Nehmen Sie an, Sie haben eine Liste mit Haustieren, möchten diese aber in ein Wörterbuch konvertieren, damit Sie direkt über den `RFID`-Wert auf ein Haustier zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d3edb-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="d3edb-110">Dies ist herkömmlicher imperativer Code:</span><span class="sxs-lookup"><span data-stu-id="d3edb-110">This is traditional imperative code:</span></span>

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

```vb
Dim petLookup = New Dictionary(Of Integer, Pet)()

For Each pet in pets
    petLookup.Add(pet.RFID, pet)
Next
```

<span data-ttu-id="d3edb-111">Der Zweck des Codes ist nicht, ein neues `Dictionary<int, Pet>`-Element zu erstellen und es über eine Schleife zu erweitern, sondern eine vorhandene Liste in ein Wörterbuch zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="d3edb-111">The intention behind the code isn't to create a new `Dictionary<int, Pet>` and add to it via a loop, it's to convert an existing list into a dictionary!</span></span> <span data-ttu-id="d3edb-112">Mit LINQ bleibt dieser Zweck erhalten, mit imperativem Code hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="d3edb-112">LINQ preserves the intention whereas the imperative code doesn't.</span></span>

<span data-ttu-id="d3edb-113">Dies ist der entsprechende LINQ-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="d3edb-113">This is the equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="d3edb-114">Der Code mit LINQ ist hilfreich, da er aus der Perspektive eines Programmierers einen Ausgleich zwischen Zweck und Code schafft.</span><span class="sxs-lookup"><span data-stu-id="d3edb-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="d3edb-115">Ein weiter Bonus ist die Kürze des Codes.</span><span class="sxs-lookup"><span data-stu-id="d3edb-115">Another bonus is code brevity.</span></span> <span data-ttu-id="d3edb-116">Stellen Sie sich vor, Sie könnten große Teile einer Codebasis um 1/3 reduzieren, wie oben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d3edb-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="d3edb-117">Klingt das nicht überzeugend?</span><span class="sxs-lookup"><span data-stu-id="d3edb-117">Sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="d3edb-118">LINQ-Anbieter vereinfachen den Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="d3edb-118">LINQ providers simplify data access</span></span>

<span data-ttu-id="d3edb-119">Für einen erheblichen Teil der verwendeten Software dreht sich alles um den Umgang mit Daten aus unterschiedlichen Quellen (Datenbanken, JSON, XML usw.).</span><span class="sxs-lookup"><span data-stu-id="d3edb-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, and so on).</span></span> <span data-ttu-id="d3edb-120">Häufig gehört dazu das Erlernen einer neuen API für jede Datenquelle, was lästig sein kann.</span><span class="sxs-lookup"><span data-stu-id="d3edb-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="d3edb-121">LINQ vereinfacht dies durch das Abstrahieren gemeinsamer Elemente des Datenzugriffs in eine Abfragesyntax, die immer gleich aussieht, unabhängig davon, welche Datenquelle Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="d3edb-121">LINQ simplifies this by abstracting common elements of data access into a query syntax that looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="d3edb-122">Dieser Code findet alle XML-Elemente mit einem bestimmten Attributwert:</span><span class="sxs-lookup"><span data-stu-id="d3edb-122">This finds all XML elements with a specific attribute value:</span></span>

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

```vb
Public Shared Function FindAllElementsWithAttribute(documentRoot As XElement, elementName As String,
                                           attributeName As String, value As String) As IEnumerable(Of XElement)
    Return From el In documentRoot.Elements(elementName)
           Where el.Element(attributeName).ToString() = value
           Select el
End Function
```

<span data-ttu-id="d3edb-123">Code zu schreiben, um das XML-Dokument zu diesem Zweck manuell zu durchlaufen, wäre eine wesentlich größere Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="d3edb-123">Writing code to manually traverse the XML document to do this task would be far more challenging.</span></span>

<span data-ttu-id="d3edb-124">LINQ-Anbieter ermöglichen nicht nur die Interaktion mit XML.</span><span class="sxs-lookup"><span data-stu-id="d3edb-124">Interacting with XML isn't the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="d3edb-125">[LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) ist ein ziemlich reduzierter objektrelationaler Mapper (ORM) für eine MSSQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d3edb-125">[Linq to SQL](../../framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="d3edb-126">Die [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm)-Bibliothek bietet einen effizienten Durchlauf von JSON-Dokumenten über LINQ.</span><span class="sxs-lookup"><span data-stu-id="d3edb-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="d3edb-127">Wenn es allerdings keine Bibliothek gibt, die Ihre Anforderungen erfüllt, können Sie auch [Ihren eigenen LINQ-Anbieter schreiben](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="d3edb-127">Furthermore, if there isn't a library that does what you need, you can also [write your own LINQ Provider](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="reasons-to-use-the-query-syntax"></a><span data-ttu-id="d3edb-128">Gründe für die Verwendung der Abfragesyntax</span><span class="sxs-lookup"><span data-stu-id="d3edb-128">Reasons to use the query syntax</span></span>

<span data-ttu-id="d3edb-129">Warum sollte die Abfragesyntax verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="d3edb-129">Why use query syntax?</span></span> <span data-ttu-id="d3edb-130">Dies ist eine Frage, die häufig gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d3edb-130">This is a question that often comes up.</span></span> <span data-ttu-id="d3edb-131">Schließlich ist der folgende Code:</span><span class="sxs-lookup"><span data-stu-id="d3edb-131">After all, the following code:</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="d3edb-132">sehr viel präziser als dies:</span><span class="sxs-lookup"><span data-stu-id="d3edb-132">is a lot more concise than this:</span></span>

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

```vb
Dim filteredItems = From item In myItems
                    Where item.Foo
                    Select item
```

<span data-ttu-id="d3edb-133">Ist die API-Syntax nicht nur eine präzisere Methode für die Abfragesyntax?</span><span class="sxs-lookup"><span data-stu-id="d3edb-133">Isn't the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="d3edb-134">Nein.</span><span class="sxs-lookup"><span data-stu-id="d3edb-134">No.</span></span> <span data-ttu-id="d3edb-135">Die Abfragesyntax ermöglicht die Verwendung der **let**-Klausel, mit der Sie eine Variable im Bereich des Ausdrucks einführen und binden können, um sie in nachfolgenden Teilen des Ausdrucks zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-135">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="d3edb-136">Das Reproduzieren des gleichen Codes nur mit der API-Syntax ist möglich, führt jedoch wahrscheinlich zu Code, der schwer lesbar ist.</span><span class="sxs-lookup"><span data-stu-id="d3edb-136">Reproducing the same code with only the API syntax can be done, but will most likely lead to code that's hard to read.</span></span>

<span data-ttu-id="d3edb-137">Daher stellt sich die folgende Frage: **Sollten Sie einfach die Abfragesyntax verwenden?**</span><span class="sxs-lookup"><span data-stu-id="d3edb-137">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="d3edb-138">Die Antwort auf diese Frage ist **Ja**, wenn:</span><span class="sxs-lookup"><span data-stu-id="d3edb-138">The answer to this question is **yes** if:</span></span>

- <span data-ttu-id="d3edb-139">Ihre vorhandene Codebasis bereits die Abfragesyntax verwendet.</span><span class="sxs-lookup"><span data-stu-id="d3edb-139">Your existing codebase already uses the query syntax.</span></span>
- <span data-ttu-id="d3edb-140">Sie den Gültigkeitsbereich von Variablen in Ihren Abfragen aufgrund der Komplexität festlegen müssen.</span><span class="sxs-lookup"><span data-stu-id="d3edb-140">You need to scope variables within your queries because of complexity.</span></span>
- <span data-ttu-id="d3edb-141">Sie die Abfragesyntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-141">You prefer the query syntax and it won't distract from your codebase.</span></span>

<span data-ttu-id="d3edb-142">Die Antwort auf diese Frage ist **Nein**, wenn...</span><span class="sxs-lookup"><span data-stu-id="d3edb-142">The answer to this question is **no** if...</span></span>

- <span data-ttu-id="d3edb-143">Ihre vorhandene Codebasis die API-Syntax bereits verwendet</span><span class="sxs-lookup"><span data-stu-id="d3edb-143">Your existing codebase already uses the API syntax</span></span>
- <span data-ttu-id="d3edb-144">Sie den Bereich von Variablen in Ihren Abfragen nicht festlegen müssen</span><span class="sxs-lookup"><span data-stu-id="d3edb-144">You have no need to scope variables within your queries</span></span>
- <span data-ttu-id="d3edb-145">Sie die API-Syntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-145">You prefer the API syntax and it won't distract from your codebase</span></span>

## <a name="essential-linq"></a><span data-ttu-id="d3edb-146">Grundlegendes zu LINQ</span><span class="sxs-lookup"><span data-stu-id="d3edb-146">Essential LINQ</span></span>

<span data-ttu-id="d3edb-147">Eine umfassende Liste der LINQ-Beispiele finden Sie unter [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/) (101 LINQ-Beispiele).</span><span class="sxs-lookup"><span data-stu-id="d3edb-147">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/).</span></span>

<span data-ttu-id="d3edb-148">Die folgenden Beispiele sind eine kurze Darstellung einiger der grundlegenden Bestandteile von LINQ.</span><span class="sxs-lookup"><span data-stu-id="d3edb-148">The following examples are a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="d3edb-149">Sie ist bei weitem nicht vollständig, da LINQ mehr Funktionen bietet, als hier vorgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-149">This is in no way comprehensive, as LINQ provides more functionality than what is showcased here.</span></span>

### <a name="the-bread-and-butter---where-select-and-aggregate"></a><span data-ttu-id="d3edb-150">Die Grundbestandteile sind `Where`, `Select` und `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="d3edb-150">The bread and butter - `Where`, `Select`, and `Aggregate`</span></span>

```csharp
// Filtering a list.
var germanShepherds = dogs.Where(dog => dog.Breed == DogBreed.GermanShepherd);

// Using the query syntax.
var queryGermanShepherds = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepherd
                          select dog;

// Mapping a list from type A to type B.
var cats = dogs.Select(dog => dog.TurnIntoACat());

// Using the query syntax.
var queryCats = from dog in dogs
                select dog.TurnIntoACat();

// Summing the lengths of a set of strings.
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

```vb
' Filtering a list.
Dim germanShepherds = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepherd)

' Using the query syntax.
Dim queryGermanShepherds = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepherd
                          Select dog

' Mapping a list from type A to type B.
Dim cats = dogs.Select(Function(dog) dog.TurnIntoACat())

' Using the query syntax.
Dim queryCats = From dog In dogs
                Select dog.TurnIntoACat()

' Summing the lengths of a set of strings.
Dim seed As Integer = 0
Dim sumOfStrings As Integer = strings.Aggregate(seed, Function(s1, s2) s1.Length + s2.Length)
```

### <a name="flattening-a-list-of-lists"></a><span data-ttu-id="d3edb-151">Reduzieren einer Liste mit Listen</span><span class="sxs-lookup"><span data-stu-id="d3edb-151">Flattening a list of lists</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a><span data-ttu-id="d3edb-152">Vereinigung von zwei Gruppen (mit benutzerdefiniertem Vergleichsoperator)</span><span class="sxs-lookup"><span data-stu-id="d3edb-152">Union between two sets (with custom comparator)</span></span>

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
        // Default hashcode is enough here, as these are simple objects.
        return d.GetHashCode();
    }
}
...

// Gets all the short-haired dogs between two different kennels.
var allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, new DogHairLengthComparer());

```

```vb
Public Class DogHairLengthComparer
  Inherits IEqualityComparer(Of Dog)

  Public Function Equals(a As Dog,b As Dog) As Boolean
      If a Is Nothing AndAlso b Is Nothing Then
          Return True
      ElseIf (a Is Nothing AndAlso b IsNot Nothing) OrElse (a IsNot Nothing AndAlso b Is Nothing) Then
          Return False
      Else
          Return a.HairLengthType = b.HairLengthType
      End If
  End Function

  Public Function GetHashCode(d As Dog) As Integer
      ' Default hashcode is enough here, as these are simple objects.
      Return d.GetHashCode()
  End Function
End Class

...

' Gets all the short-haired dogs between two different kennels.
Dim allShortHairedDogs = kennel1.Dogs.Union(kennel2.Dogs, New DogHairLengthComparer())
```

### <a name="intersection-between-two-sets"></a><span data-ttu-id="d3edb-153">Schnittmenge von zwei Mengen</span><span class="sxs-lookup"><span data-stu-id="d3edb-153">Intersection between two sets</span></span>

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

```vb
' Gets the volunteers who spend share time with two humane societies.
Dim volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     New VolunteerTimeComparer())
```

### <a name="ordering"></a><span data-ttu-id="d3edb-154">Sortieren</span><span class="sxs-lookup"><span data-stu-id="d3edb-154">Ordering</span></span>

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

```vb
' Get driving directions, ordering by if it's toll-free before estimated driving time.
Dim results = DirectionsProcessor.GetDirections(start, end).
                OrderBy(Function(direction) direction.HasNoTolls).
                ThenBy(Function(direction) direction.EstimatedTime)
```

### <a name="equality-of-instance-properties"></a><span data-ttu-id="d3edb-155">Gleichheit von Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="d3edb-155">Equality of instance properties</span></span>

<span data-ttu-id="d3edb-156">Schließlich ein erweitertes Beispiel: Ermitteln, ob die Werte der Eigenschaften von zwei Instanzen desselben Typs gleich sind (aus [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/844855) übernommen und geändert):</span><span class="sxs-lookup"><span data-stu-id="d3edb-156">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

```csharp
public static bool PublicInstancePropertiesEqual<T>(this T self, T to, params string[] ignore) where T : class
{
    if (self == null || to == null)
    {
        return self == to;
    }

    // Selects the properties which have unequal values into a sequence of those properties.
    var unequalProperties = from property in typeof(T).GetProperties(BindingFlags.Public | BindingFlags.Instance)
                            where !ignore.Contains(property.Name)
                            let selfValue = property.GetValue(self, null)
                            let toValue = property.GetValue(to, null)
                            where !Equals(selfValue, toValue)
                            select property;
    return !unequalProperties.Any();
}
```

```vb
<System.Runtime.CompilerServices.Extension()>
Public Function PublicInstancePropertiesEqual(Of T As Class)(self As T, [to] As T, ParamArray ignore As String()) As Boolean
    If self Is Nothing OrElse [to] Is Nothing Then
        Return self Is [to]
    End If

    ' Selects the properties which have unequal values into a sequence of those properties.
    Dim unequalProperties = From [property] In GetType(T).GetProperties(BindingFlags.Public Or BindingFlags.Instance)
                            Where Not ignore.Contains([property].Name)
                            Let selfValue = [property].GetValue(self, Nothing)
                            Let toValue = [property].GetValue([to], Nothing)
                            Where Not Equals(selfValue, toValue) Select [property]
    Return Not unequalProperties.Any()
End Function
```

## <a name="plinq"></a><span data-ttu-id="d3edb-157">PLINQ</span><span class="sxs-lookup"><span data-stu-id="d3edb-157">PLINQ</span></span>

<span data-ttu-id="d3edb-158">PLINQ (Parallel LINQ) ist eine Engine für die parallele Ausführung für LINQ-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="d3edb-158">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="d3edb-159">Reguläre LINQ-Ausdrücke können also im Grunde ganz einfach über eine beliebige Anzahl von Threads parallelisiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-159">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="d3edb-160">Dies erfolgt über einen Aufruf von `AsParallel()` vor dem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="d3edb-160">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="d3edb-161">Beachten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d3edb-161">Consider the following:</span></span>

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

```vb
Public Shared GetAllFacebookUserLikesMessage(facebookUsers As IEnumerable(Of FacebookUser)) As String
{
    Dim seed As UInt64 = 0

    Dim threadAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim threadResultAccumulator As Func(Of UInt64, UInt64, UInt64) = Function(t1, t2) t1 + t2
    Dim resultSelector As Func(Of Uint64, string) = Function(total) $"Facebook has {total} likes!"

    Return facebookUsers.AsParallel().
                        Aggregate(seed, threadAccumulator, threadResultAccumulator, resultSelector)
}
```

<span data-ttu-id="d3edb-162">Dieser Code partitioniert bei Bedarf `facebookUsers` über Systemthreads, summiert die Gesamtanzahl der „Likes“ parallel für jeden Thread, summiert die von allen Threads berechneten Ergebnisse und bringt das Ergebnis in eine nützliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d3edb-162">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="d3edb-163">In Diagrammform:</span><span class="sxs-lookup"><span data-stu-id="d3edb-163">In diagram form:</span></span>

![PLINQ-Diagramm](media/index/plinq-diagram.png)

<span data-ttu-id="d3edb-165">Parallelisierbare CPU-gebundene Aufträge, die problemlos über LINQ ausgedrückt werden können (die also reine Funktionen ohne Nebeneffekte darstellen) sind gute Kandidaten für PLINQ.</span><span class="sxs-lookup"><span data-stu-id="d3edb-165">Parallelizable CPU-bound jobs that can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="d3edb-166">Für Aufträge, die einen Nebeneffekt _haben_, sollten Sie die [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="d3edb-166">For jobs that _do_ have a side effect, consider using the [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="d3edb-167">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d3edb-167">More resources</span></span>

* [<span data-ttu-id="d3edb-168">101 LINQ-Beispiele</span><span class="sxs-lookup"><span data-stu-id="d3edb-168">101 LINQ Samples</span></span>](/samples/dotnet/try-samples/101-linq-samples/)
* <span data-ttu-id="d3edb-169">[Linqpad](https://www.linqpad.net/), eine Umgebung und eine Datenbankabfrage-Engine für C#/F#/Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3edb-169">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="d3edb-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), ein E-Book, in dem die Implementierung von LINQ to Objects erläutert wird</span><span class="sxs-lookup"><span data-stu-id="d3edb-170">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
