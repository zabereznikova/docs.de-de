---
title: LINQ (Language Integrated Query)
description: LINQ bietet Abfragefunktionen auf Sprachebene und eine API für C# und Visual Basic, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 76872f3ba3ed5106a4cb5bfdd918ae607acc092d
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507519"
---
# <a name="linq-language-integrated-query"></a><span data-ttu-id="e7187-103">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="e7187-103">LINQ (Language Integrated Query)</span></span>

## <a name="what-is-it"></a><span data-ttu-id="e7187-104">Was ist das?</span><span class="sxs-lookup"><span data-stu-id="e7187-104">What is it?</span></span>

<span data-ttu-id="e7187-105">LINQ bietet Abfragefunktionen auf Sprachebene und eine API einer [Funktion höherer Ordnung](https://en.wikipedia.org/wiki/Higher-order_function) für C# und Visual Basic, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="e7187-105">LINQ provides language-level querying capabilities and a [higher-order function](https://en.wikipedia.org/wiki/Higher-order_function) API to C# and Visual Basic as a way to write expressive, declarative code.</span></span>

<span data-ttu-id="e7187-106">Abfragesyntax auf Sprachebene:</span><span class="sxs-lookup"><span data-stu-id="e7187-106">Language-level query syntax:</span></span>

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

<span data-ttu-id="e7187-107">Gleiches Beispiel mit der `IEnumerable<T>`-API:</span><span class="sxs-lookup"><span data-stu-id="e7187-107">Same example using the `IEnumerable<T>` API:</span></span>

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a><span data-ttu-id="e7187-108">LINQ ist ausdrucksstark</span><span class="sxs-lookup"><span data-stu-id="e7187-108">LINQ is Expressive</span></span>

<span data-ttu-id="e7187-109">Nehmen Sie an, Sie haben eine Liste mit Haustieren, möchten diese aber in ein Wörterbuch konvertieren, damit Sie direkt über den `RFID`-Wert auf ein Haustier zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e7187-109">Imagine you have a list of pets, but want to convert it into a dictionary where you can access a pet directly by its `RFID` value.</span></span>

<span data-ttu-id="e7187-110">Herkömmlicher imperativer Code:</span><span class="sxs-lookup"><span data-stu-id="e7187-110">Traditional imperative code:</span></span>

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

<span data-ttu-id="e7187-111">Der Zweck des Codes ist nicht, ein neues `Dictionary<int, Pet>` zu erstellen und es über eine Schleife zu erweitern, sondern eine vorhandene Liste in ein Wörterbuch zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="e7187-111">The intention behind the code is not to create a new `Dictionary<int, Pet>` and add to it via a loop, it is to convert an existing list into a dictionary!</span></span> <span data-ttu-id="e7187-112">Mit LINQ bleibt dieser Zweck erhalten, mit imperativem Code hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="e7187-112">LINQ preserves the intention whereas the imperative code does not.</span></span>

<span data-ttu-id="e7187-113">Entsprechender LINQ-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="e7187-113">Equivalent LINQ expression:</span></span>

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

<span data-ttu-id="e7187-114">Der Code mit LINQ ist hilfreich, da er aus der Perspektive eines Programmierers einen Ausgleich zwischen Zweck und Code schafft.</span><span class="sxs-lookup"><span data-stu-id="e7187-114">The code using LINQ is valuable because it evens the playing field between intent and code when reasoning as a programmer.</span></span> <span data-ttu-id="e7187-115">Ein weiter Bonus ist die Kürze des Codes.</span><span class="sxs-lookup"><span data-stu-id="e7187-115">Another bonus is code brevity.</span></span> <span data-ttu-id="e7187-116">Stellen Sie sich vor, Sie könnten große Teile einer Codebasis um 1/3 reduzieren, wie oben dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7187-116">Imagine reducing large portions of a codebase by 1/3 as done above.</span></span> <span data-ttu-id="e7187-117">Klingt das nicht überzeugend?</span><span class="sxs-lookup"><span data-stu-id="e7187-117">Pretty sweet deal, right?</span></span>

## <a name="linq-providers-simplify-data-access"></a><span data-ttu-id="e7187-118">LINQ-Anbieter vereinfachen den Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="e7187-118">LINQ Providers Simplify Data Access</span></span>

<span data-ttu-id="e7187-119">Für einen erheblichen Teil der verwendeten Software dreht sich alles um den Umgang mit Daten aus unterschiedlichen Quellen (Datenbanken, JSON, XML usw.).</span><span class="sxs-lookup"><span data-stu-id="e7187-119">For a significant chunk of software out in the wild, everything revolves around dealing with data from some source (Databases, JSON, XML, etc).</span></span> <span data-ttu-id="e7187-120">Häufig gehört dazu das Erlernen einer neuen API für jede Datenquelle, was lästig sein kann.</span><span class="sxs-lookup"><span data-stu-id="e7187-120">Often this involves learning a new API for each data source, which can be annoying.</span></span> <span data-ttu-id="e7187-121">LINQ vereinfacht dies durch das Abstrahieren gemeinsamer Elemente des Datenzugriffs in eine Abfragesyntax, die immer gleich aussieht, unabhängig davon, welche Datenquelle Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="e7187-121">LINQ simplifies this by abstracting common elements of data access into a query syntax which looks the same no matter which data source you pick.</span></span>

<span data-ttu-id="e7187-122">Stellen Sie sich Folgendes vor: Sie möchten alle XML-Elemente mit einem bestimmten Attributwert finden.</span><span class="sxs-lookup"><span data-stu-id="e7187-122">Consider the following: finding all XML elements with a specific attribute value.</span></span>

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

<span data-ttu-id="e7187-123">Code zu schreiben, um das XML-Dokument zu diesem Zweck manuell zu durchlaufen, wäre eine wesentlich größere Herausforderung.</span><span class="sxs-lookup"><span data-stu-id="e7187-123">Writing code to manually traverse the XML document to perform this task would be far more challenging.</span></span>

<span data-ttu-id="e7187-124">LINQ-Anbieter ermöglichen nicht nur die Interaktion mit XML.</span><span class="sxs-lookup"><span data-stu-id="e7187-124">Interacting with XML isn’t the only thing you can do with LINQ Providers.</span></span> <span data-ttu-id="e7187-125">[LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) ist ein ziemlich reduzierter objektrelationaler Mapper (ORM) für eine MSSQL Server-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e7187-125">[Linq to SQL](../../docs/framework/data/adonet/sql/linq/index.md) is a fairly bare-bones Object-Relational Mapper (ORM) for an MSSQL Server Database.</span></span> <span data-ttu-id="e7187-126">Die [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm)-Bibliothek bietet einen effizienten Durchlauf von JSON-Dokumenten über LINQ.</span><span class="sxs-lookup"><span data-stu-id="e7187-126">The [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm) library provides efficient JSON Document traversal via LINQ.</span></span> <span data-ttu-id="e7187-127">Wenn es allerdings keine Bibliothek gibt, die Ihre Anforderungen erfüllt, können Sie auch [Ihren eigenen LINQ-Anbieter schreiben](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).</span><span class="sxs-lookup"><span data-stu-id="e7187-127">Furthermore, if there isn’t a library which does what you need, you can also [write your own LINQ Provider](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110))!</span></span>

## <a name="why-use-the-query-syntax"></a><span data-ttu-id="e7187-128">Warum sollte die Abfragesyntax verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="e7187-128">Why Use the Query Syntax?</span></span>

<span data-ttu-id="e7187-129">Dies ist eine Frage, die häufig gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e7187-129">This is a question which often comes up.</span></span> <span data-ttu-id="e7187-130">Im Grunde ist dies:</span><span class="sxs-lookup"><span data-stu-id="e7187-130">After all, this,</span></span>

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

<span data-ttu-id="e7187-131">sehr viel präziser als dies:</span><span class="sxs-lookup"><span data-stu-id="e7187-131">is a lot more concise than this:</span></span>

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

<span data-ttu-id="e7187-132">Ist die API-Syntax nicht nur eine präzisere Methode für die Abfragesyntax?</span><span class="sxs-lookup"><span data-stu-id="e7187-132">Isn’t the API syntax just a more concise way to do the query syntax?</span></span>

<span data-ttu-id="e7187-133">Nein.</span><span class="sxs-lookup"><span data-stu-id="e7187-133">No.</span></span> <span data-ttu-id="e7187-134">Die Abfragesyntax ermöglicht die Verwendung der **let**-Klausel, mit der Sie eine Variable im Bereich des Ausdrucks einführen und binden können, um sie in nachfolgenden Teilen des Ausdrucks zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7187-134">The query syntax allows for the use of the **let** clause, which allows you to introduce and bind a variable within the scope of the expression, using it in subsequent pieces of the expression.</span></span> <span data-ttu-id="e7187-135">Das Reproduzieren des gleichen Codes nur mit der API-Syntax ist möglich, führt jedoch wahrscheinlich zu Code, der schwer lesbar ist.</span><span class="sxs-lookup"><span data-stu-id="e7187-135">Reproducing the same code with only the API syntax can be done, but will most likely lead to code which is hard to read.</span></span>

<span data-ttu-id="e7187-136">Daher stellt sich die folgende Frage: **Sollten Sie einfach die Abfragesyntax verwenden?**</span><span class="sxs-lookup"><span data-stu-id="e7187-136">So this begs the question, **should you just use the query syntax?**</span></span>

<span data-ttu-id="e7187-137">Die Antwort auf diese Frage ist **Ja**, wenn...</span><span class="sxs-lookup"><span data-stu-id="e7187-137">The answer to this question is **yes** if...</span></span>

* <span data-ttu-id="e7187-138">Ihre vorhandene Codebasis bereits die Abfragesyntax verwendet</span><span class="sxs-lookup"><span data-stu-id="e7187-138">Your existing codebase already uses the query syntax</span></span>
* <span data-ttu-id="e7187-139">Sie den Bereich von Variablen in Ihren Abfragen aufgrund der Komplexität festlegen müssen</span><span class="sxs-lookup"><span data-stu-id="e7187-139">You need to scope variables within your queries due to complexity</span></span>
* <span data-ttu-id="e7187-140">Sie die Abfragesyntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden</span><span class="sxs-lookup"><span data-stu-id="e7187-140">You prefer the query syntax and it won’t distract from your codebase</span></span>

<span data-ttu-id="e7187-141">Die Antwort auf diese Frage ist **Nein**, wenn...</span><span class="sxs-lookup"><span data-stu-id="e7187-141">The answer to this question is **no** if...</span></span>

* <span data-ttu-id="e7187-142">Ihre vorhandene Codebasis die API-Syntax bereits verwendet</span><span class="sxs-lookup"><span data-stu-id="e7187-142">Your existing codebase already uses the API syntax</span></span>
* <span data-ttu-id="e7187-143">Sie den Bereich von Variablen in Ihren Abfragen nicht festlegen müssen</span><span class="sxs-lookup"><span data-stu-id="e7187-143">You have no need to scope variables within your queries</span></span>
* <span data-ttu-id="e7187-144">Sie die API-Syntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden</span><span class="sxs-lookup"><span data-stu-id="e7187-144">You prefer the API syntax and it won’t distract from your codebase</span></span>

## <a name="essential-samples"></a><span data-ttu-id="e7187-145">Grundlegende Beispiele</span><span class="sxs-lookup"><span data-stu-id="e7187-145">Essential Samples</span></span>

<span data-ttu-id="e7187-146">Eine umfassende Liste der LINQ-Beispiele finden Sie unter [101 LINQ Samples](https://docs.microsoft.com/samples/dotnet/try-samples/101-linq-samples/) (101 LINQ-Beispiele).</span><span class="sxs-lookup"><span data-stu-id="e7187-146">For a truly comprehensive list of LINQ samples, visit [101 LINQ Samples](https://docs.microsoft.com/samples/dotnet/try-samples/101-linq-samples/).</span></span>

<span data-ttu-id="e7187-147">Im Folgenden finden eine kurze Darstellung einiger der grundlegenden Bestandteile von LINQ.</span><span class="sxs-lookup"><span data-stu-id="e7187-147">The following is a quick demonstration of some of the essential pieces of LINQ.</span></span> <span data-ttu-id="e7187-148">Sie ist bei weitem nicht vollständig, da LINQ erheblich mehr Funktionen bietet, als hier präsentiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7187-148">This is in no way comprehensive, as LINQ provides significantly more functionality than what is showcased here.</span></span>

* <span data-ttu-id="e7187-149">Die Grundbestandteile sind `Where`, `Select` und `Aggregate`:</span><span class="sxs-lookup"><span data-stu-id="e7187-149">The bread and butter - `Where`, `Select`, and `Aggregate`:</span></span>

```csharp
// Filtering a list.
var germanShepards = dogs.Where(dog => dog.Breed == DogBreed.GermanShepard);

// Using the query syntax.
var queryGermanShepards = from dog in dogs
                          where dog.Breed == DogBreed.GermanShepard
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
Dim germanShepards = dogs.Where(Function(dog) dog.Breed = DogBreed.GermanShepard)

' Using the query syntax.
Dim queryGermanShepards = From dog In dogs
                          Where dog.Breed = DogBreed.GermanShepard
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

* <span data-ttu-id="e7187-150">Reduzieren einer Liste mit Listen:</span><span class="sxs-lookup"><span data-stu-id="e7187-150">Flattening a list of lists:</span></span>

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

* <span data-ttu-id="e7187-151">Vereinigung von zwei Gruppen (mit benutzerdefiniertem Vergleichsoperator):</span><span class="sxs-lookup"><span data-stu-id="e7187-151">Union between two sets (with custom comparator):</span></span>

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

* <span data-ttu-id="e7187-152">Schnittmenge zwischen zwei Gruppen:</span><span class="sxs-lookup"><span data-stu-id="e7187-152">Intersection between two sets:</span></span>

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

* <span data-ttu-id="e7187-153">Sortierung:</span><span class="sxs-lookup"><span data-stu-id="e7187-153">Ordering:</span></span>

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

* <span data-ttu-id="e7187-154">Schließlich ein erweitertes Beispiel: Ermitteln, ob die Werte der Eigenschaften von zwei Instanzen desselben Typs gleich sind (aus [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/844855) übernommen und geändert):</span><span class="sxs-lookup"><span data-stu-id="e7187-154">Finally, a more advanced sample: determining if the values of the properties of two instances of the same type are equal (Borrowed and modified from [this StackOverflow post](https://stackoverflow.com/a/844855)):</span></span>

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

## <a name="plinq"></a><span data-ttu-id="e7187-155">PLINQ</span><span class="sxs-lookup"><span data-stu-id="e7187-155">PLINQ</span></span>

<span data-ttu-id="e7187-156">PLINQ (Parallel LINQ) ist eine Engine für die parallele Ausführung für LINQ-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="e7187-156">PLINQ, or Parallel LINQ, is a parallel execution engine for LINQ expressions.</span></span> <span data-ttu-id="e7187-157">Reguläre LINQ-Ausdrücke können also im Grunde ganz einfach über eine beliebige Anzahl von Threads parallelisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7187-157">In other words, a regular LINQ expression can be trivially parallelized across any number of threads.</span></span> <span data-ttu-id="e7187-158">Dies erfolgt über einen Aufruf von `AsParallel()` vor dem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="e7187-158">This is accomplished via a call to `AsParallel()` preceding the expression.</span></span>

<span data-ttu-id="e7187-159">Nehmen wir einmal die folgende Situation:</span><span class="sxs-lookup"><span data-stu-id="e7187-159">Consider the following:</span></span>

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

<span data-ttu-id="e7187-160">Dieser Code partitioniert bei Bedarf `facebookUsers` über Systemthreads, summiert die Gesamtanzahl der „Likes“ parallel für jeden Thread, summiert die von allen Threads berechneten Ergebnisse und bringt das Ergebnis in eine nützliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7187-160">This code will partition `facebookUsers` across system threads as necessary, sum up the total likes on each thread in parallel, sum the results computed by each thread, and project that result into a nice string.</span></span>

<span data-ttu-id="e7187-161">In Diagrammform:</span><span class="sxs-lookup"><span data-stu-id="e7187-161">In diagram form:</span></span>

![PLINQ-Diagramm](./media/using-linq/plinq-diagram.png)

<span data-ttu-id="e7187-163">Parallelisierbare CPU-gebundene Aufträge, die problemlos über LINQ ausgedrückt werden können (die also reine Funktionen ohne Nebeneffekte darstellen) sind gute Kandidaten für PLINQ.</span><span class="sxs-lookup"><span data-stu-id="e7187-163">Parallelizable CPU-bound jobs which can be easily expressed via LINQ (in other words, are pure functions and have no side effects) are a great candidate for PLINQ.</span></span> <span data-ttu-id="e7187-164">Für Aufträge, die einen Nebeneffekt _haben_, sollten Sie die [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7187-164">For jobs which _do_ have a side effect, consider using the [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md).</span></span>

## <a name="further-resources"></a><span data-ttu-id="e7187-165">Weitere Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="e7187-165">Further Resources:</span></span>

* [<span data-ttu-id="e7187-166">101 LINQ-Beispiele</span><span class="sxs-lookup"><span data-stu-id="e7187-166">101 LINQ Samples</span></span>](https://docs.microsoft.com/samples/dotnet/try-samples/101-linq-samples/)
* <span data-ttu-id="e7187-167">[Linqpad](https://www.linqpad.net/), eine Umgebung und eine Datenbankabfrage-Engine für C#/F#/Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7187-167">[Linqpad](https://www.linqpad.net/), a playground environment and Database querying engine for C#/F#/Visual Basic</span></span>
* <span data-ttu-id="e7187-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), ein E-Book, in dem die Implementierung von LINQ to Objects erläutert wird</span><span class="sxs-lookup"><span data-stu-id="e7187-168">[EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), an e-book for learning how LINQ-to-objects is implemented</span></span>
