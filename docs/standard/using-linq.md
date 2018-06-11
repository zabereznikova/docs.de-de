---
title: LINQ (Language Integrated Query)
description: LINQ bietet Abfragefunktionen auf Sprachebene und eine API für C# und VB, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben.
author: cartermp
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: c00939e1-59e3-4e61-8fe9-08ad6b3f1295
ms.openlocfilehash: 31b0a7b9e11d46e6453d9fcad87e7beadba9a1e3
ms.sourcegitcommit: 6c480773ae896f45af4671fb3e26611a50e4dd81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2018
ms.locfileid: "35251089"
---
# <a name="linq-language-integrated-query"></a>LINQ (Language Integrated Query)

## <a name="what-is-it"></a>Was ist das?

LINQ bietet Abfragefunktionen auf Sprachebene und eine API einer [Funktion höherer Ordnung](https://en.wikipedia.org/wiki/Higher-order_function) für C# und VB, sodass die Möglichkeit besteht, aussagekräftigen, deklarativen Code zu schreiben.

Abfragesyntax auf Sprachebene:

```csharp
var linqExperts = from p in programmers
                  where p.IsNewToLINQ
                  select new LINQExpert(p);
```

Gleiches Beispiel mit der `IEnumerable<T>`-API:

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

## <a name="linq-is-expressive"></a>LINQ ist ausdrucksstark

Nehmen Sie an, Sie haben eine Liste mit Haustieren, möchten diese aber in ein Wörterbuch konvertieren, damit Sie direkt über den `RFID`-Wert auf ein Haustier zugreifen können.

Herkömmlicher imperativer Code:

```csharp
var petLookup = new Dictionary<int, Pet>();

foreach (var pet in pets)
{
    petLookup.Add(pet.RFID, pet);
}
```

Der Zweck des Codes ist nicht, ein neues `Dictionary<int, Pet>` zu erstellen und es über eine Schleife zu erweitern, sondern eine vorhandene Liste in ein Wörterbuch zu konvertieren. Mit LINQ bleibt dieser Zweck erhalten, mit imperativem Code hingegen nicht.

Entsprechender LINQ-Ausdruck:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

Der Code mit LINQ ist hilfreich, da er aus der Perspektive eines Programmierers einen Ausgleich zwischen Zweck und Code schafft. Ein weiter Bonus ist die Kürze des Codes. Stellen Sie sich vor, Sie könnten große Teile einer Codebasis um 1/3 reduzieren, wie oben dargestellt. Klingt das nicht überzeugend?

## <a name="linq-providers-simplify-data-access"></a>LINQ-Anbieter vereinfachen den Datenzugriff

Für einen erheblichen Teil der verwendeten Software dreht sich alles um den Umgang mit Daten aus unterschiedlichen Quellen (Datenbanken, JSON, XML usw.). Häufig gehört dazu das Erlernen einer neuen API für jede Datenquelle, was lästig sein kann. LINQ vereinfacht dies durch das Abstrahieren gemeinsamer Elemente des Datenzugriffs in eine Abfragesyntax, die immer gleich aussieht, unabhängig davon, welche Datenquelle Sie auswählen.

Stellen Sie sich Folgendes vor: Sie möchten alle XML-Elemente mit einem bestimmten Attributwert finden.

```csharp
public static IEnumerable<XElement> FindAllElementsWithAttribute(XElement documentRoot, string elementName,
                                           string attributeName, string value)
{
    return from el in documentRoot.Elements(elementName)
           where (string)el.Element(attributeName) == value
           select el;
}
```

Code zu schreiben, um das XML-Dokument zu diesem Zweck manuell zu durchlaufen, wäre eine wesentlich größere Herausforderung.

LINQ-Anbieter ermöglichen nicht nur die Interaktion mit XML. [LINQ to SQL](../../docs/framework/data/adonet/sql/linq/index.md) ist ein ziemlich reduzierter objektrelationaler Mapper (ORM) für eine MSSQL Server-Datenbank. Die [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm)-Bibliothek bietet einen effizienten Durchlauf von JSON-Dokumenten über LINQ. Wenn es allerdings keine Bibliothek gibt, die Ihre Anforderungen erfüllt, können Sie auch [Ihren eigenen LINQ-Anbieter schreiben](https://msdn.microsoft.com/library/Bb546158.aspx).

## <a name="why-use-the-query-syntax"></a>Warum sollte die Abfragesyntax verwendet werden?

Dies ist eine Frage, die häufig gestellt wird. Im Grunde ist dies:

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

sehr viel präziser als dies:

```csharp
var filteredItems = from item in myItems
                    where item.Foo
                    select item;
```

Ist die API-Syntax nicht nur eine präzisere Methode für die Abfragesyntax?

Nein. Die Abfragesyntax ermöglicht die Verwendung der **let**-Klausel, mit der Sie eine Variable im Bereich des Ausdrucks einführen und binden können, um sie in nachfolgenden Teilen des Ausdrucks zu verwenden. Das Reproduzieren des gleichen Codes nur mit der API-Syntax ist möglich, führt jedoch wahrscheinlich zu Code, der schwer lesbar ist.

Daher stellt sich die folgende Frage: **Sollten Sie einfach die Abfragesyntax verwenden?**

Die Antwort auf diese Frage ist **Ja**, wenn...

*   Ihre vorhandene Codebasis bereits die Abfragesyntax verwendet
*   Sie den Bereich von Variablen in Ihren Abfragen aufgrund der Komplexität festlegen müssen
*   Sie die Abfragesyntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden

Die Antwort auf diese Frage ist **Nein**, wenn...

*   Ihre vorhandene Codebasis die API-Syntax bereits verwendet
*   Sie den Bereich von Variablen in Ihren Abfragen nicht festlegen müssen
*   Sie die API-Syntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden

## <a name="essential-samples"></a>Grundlegende Beispiele

Eine umfassende Liste der LINQ-Beispiele finden Sie unter [101 LINQ Samples](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b) (101 LINQ-Beispiele).

Im Folgenden finden eine kurze Darstellung einiger der grundlegenden Bestandteile von LINQ. Sie ist bei weitem nicht vollständig, da LINQ erheblich mehr Funktionen bietet, als hier präsentiert werden.

*   Die Grundbestandteile sind `Where`, `Select` und `Aggregate`:

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

// Summing the lengths of a set of strings
int seed = 0;
int sumOfStrings = strings.Aggregate(seed, (s1, s2) => s1.Length + s2.Length);
```

*   Reduzieren einer Liste mit Listen:

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

*   Vereinigung von zwei Gruppen (mit benutzerdefiniertem Vergleichsoperator):

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

*   Schnittmenge zwischen zwei Gruppen:

```csharp
// Gets the volunteers who spend share time with two humane societies.
var volunteers = humaneSociety1.Volunteers.Intersect(humaneSociety2.Volunteers,
                                                     new VolunteerTimeComparer());
```

*   Sortierung:

```csharp
// Get driving directions, ordering by if it's toll-free before estimated driving time.
var results = DirectionsProcessor.GetDirections(start, end)
              .OrderBy(direction => direction.HasNoTolls)
              .ThenBy(direction => direction.EstimatedTime);
```

*   Schließlich ein erweitertes Beispiel: Ermitteln, ob die Werte der Eigenschaften von zwei Instanzen desselben Typs gleich sind (aus [diesem StackOverflow-Beitrag](http://stackoverflow.com/a/844855) übernommen und geändert):

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

## <a name="plinq"></a>PLINQ

PLINQ (Parallel LINQ) ist eine Engine für die parallele Ausführung für LINQ-Ausdrücke. Reguläre LINQ-Ausdrücke können also im Grunde über eine beliebige Anzahl von Threads parallelisiert werden. Dies erfolgt über einen Aufruf von `AsParallel()` vor dem Ausdruck.

Nehmen wir einmal die folgende Situation:

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

Dieser Code partitioniert bei Bedarf `facebookUsers` über Systemthreads, summiert die Gesamtanzahl der „Likes“ parallel für jeden Thread, summiert die von allen Threads berechneten Ergebnisse und bringt das Ergebnis in eine nützliche Zeichenfolge.

In Diagrammform:

![PLINQ-Diagramm](./media/using-linq/plinq-diagram.png)

Parallelisierbare CPU-gebundene Aufträge, die problemlos über LINQ ausgedrückt werden können (die also reine Funktionen ohne Nebeneffekte darstellen) sind gute Kandidaten für PLINQ. Für Aufträge, die einen Nebeneffekt _haben_, sollten Sie die [Task Parallel Library](./parallel-programming/task-parallel-library-tpl.md) verwenden.

## <a name="further-resources"></a>Weitere Ressourcen:

*   [101 LINQ-Beispiele](https://code.msdn.microsoft.com/101-LINQ-Samples-3fb9811b)
*   
  [Linqpad](https://www.linqpad.net/), eine Umgebung und eine Datenbankabfrage-Engine für C#/F#/VB
*   [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), ein E-Book, in dem die Implementierung von LINQ to Objects erläutert wird
