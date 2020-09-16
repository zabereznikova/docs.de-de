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
# <a name="linq-overview"></a>Übersicht über LINQ

LINQ (Language-Integrated Query) bietet Abfragefunktionen auf Sprachebene und eine API einer [Funktion höherer Ordnung](https://en.wikipedia.org/wiki/Higher-order_function) für C# und Visual Basic, die es Ihnen ermöglichen, aussagekräftigen deklarativen Code zu schreiben.

## <a name="language-level-query-syntax"></a>Abfragesyntax auf Sprachebene

Dies ist die Abfragesyntax auf Sprachebene:

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

Dies ist das gleiche Beispiel mit der `IEnumerable<T>`-API:

```csharp
var linqExperts = programmers.Where(p => p.IsNewToLINQ)
                             .Select(p => new LINQExpert(p));
```

```vb
Dim linqExperts = programmers.Where(Function(p) p.IsNewToLINQ).
                             Select(Function(p) New LINQExpert(p))
```

## <a name="linq-is-expressive"></a>LINQ ist ausdrucksstark

Nehmen Sie an, Sie haben eine Liste mit Haustieren, möchten diese aber in ein Wörterbuch konvertieren, damit Sie direkt über den `RFID`-Wert auf ein Haustier zugreifen können.

Dies ist herkömmlicher imperativer Code:

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

Der Zweck des Codes ist nicht, ein neues `Dictionary<int, Pet>`-Element zu erstellen und es über eine Schleife zu erweitern, sondern eine vorhandene Liste in ein Wörterbuch zu konvertieren. Mit LINQ bleibt dieser Zweck erhalten, mit imperativem Code hingegen nicht.

Dies ist der entsprechende LINQ-Ausdruck:

```csharp
var petLookup = pets.ToDictionary(pet => pet.RFID);
```

```vb
Dim petLookup = pets.ToDictionary(Function(pet) pet.RFID)
```

Der Code mit LINQ ist hilfreich, da er aus der Perspektive eines Programmierers einen Ausgleich zwischen Zweck und Code schafft. Ein weiter Bonus ist die Kürze des Codes. Stellen Sie sich vor, Sie könnten große Teile einer Codebasis um 1/3 reduzieren, wie oben dargestellt. Klingt das nicht überzeugend?

## <a name="linq-providers-simplify-data-access"></a>LINQ-Anbieter vereinfachen den Datenzugriff

Für einen erheblichen Teil der verwendeten Software dreht sich alles um den Umgang mit Daten aus unterschiedlichen Quellen (Datenbanken, JSON, XML usw.). Häufig gehört dazu das Erlernen einer neuen API für jede Datenquelle, was lästig sein kann. LINQ vereinfacht dies durch das Abstrahieren gemeinsamer Elemente des Datenzugriffs in eine Abfragesyntax, die immer gleich aussieht, unabhängig davon, welche Datenquelle Sie auswählen.

Dieser Code findet alle XML-Elemente mit einem bestimmten Attributwert:

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

Code zu schreiben, um das XML-Dokument zu diesem Zweck manuell zu durchlaufen, wäre eine wesentlich größere Herausforderung.

LINQ-Anbieter ermöglichen nicht nur die Interaktion mit XML. [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) ist ein ziemlich reduzierter objektrelationaler Mapper (ORM) für eine MSSQL Server-Datenbank. Die [JSON.NET](https://www.newtonsoft.com/json/help/html/LINQtoJSON.htm)-Bibliothek bietet einen effizienten Durchlauf von JSON-Dokumenten über LINQ. Wenn es allerdings keine Bibliothek gibt, die Ihre Anforderungen erfüllt, können Sie auch [Ihren eigenen LINQ-Anbieter schreiben](/previous-versions/visualstudio/visual-studio-2012/bb546158(v=vs.110)).

## <a name="reasons-to-use-the-query-syntax"></a>Gründe für die Verwendung der Abfragesyntax

Warum sollte die Abfragesyntax verwendet werden? Dies ist eine Frage, die häufig gestellt wird. Schließlich ist der folgende Code:

```csharp
var filteredItems = myItems.Where(item => item.Foo);
```

```vb
Dim filteredItems = myItems.Where(Function(item) item.Foo)
```

sehr viel präziser als dies:

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

Ist die API-Syntax nicht nur eine präzisere Methode für die Abfragesyntax?

Nein. Die Abfragesyntax ermöglicht die Verwendung der **let**-Klausel, mit der Sie eine Variable im Bereich des Ausdrucks einführen und binden können, um sie in nachfolgenden Teilen des Ausdrucks zu verwenden. Das Reproduzieren des gleichen Codes nur mit der API-Syntax ist möglich, führt jedoch wahrscheinlich zu Code, der schwer lesbar ist.

Daher stellt sich die folgende Frage: **Sollten Sie einfach die Abfragesyntax verwenden?**

Die Antwort auf diese Frage ist **Ja**, wenn:

- Ihre vorhandene Codebasis bereits die Abfragesyntax verwendet.
- Sie den Gültigkeitsbereich von Variablen in Ihren Abfragen aufgrund der Komplexität festlegen müssen.
- Sie die Abfragesyntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden.

Die Antwort auf diese Frage ist **Nein**, wenn...

- Ihre vorhandene Codebasis die API-Syntax bereits verwendet
- Sie den Bereich von Variablen in Ihren Abfragen nicht festlegen müssen
- Sie die API-Syntax bevorzugen und Sie dadurch nicht von Ihrer Codebasis abgelenkt werden.

## <a name="essential-linq"></a>Grundlegendes zu LINQ

Eine umfassende Liste der LINQ-Beispiele finden Sie unter [101 LINQ Samples](/samples/dotnet/try-samples/101-linq-samples/) (101 LINQ-Beispiele).

Die folgenden Beispiele sind eine kurze Darstellung einiger der grundlegenden Bestandteile von LINQ. Sie ist bei weitem nicht vollständig, da LINQ mehr Funktionen bietet, als hier vorgestellt werden.

### <a name="the-bread-and-butter---where-select-and-aggregate"></a>Die Grundbestandteile sind `Where`, `Select` und `Aggregate`.

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

### <a name="flattening-a-list-of-lists"></a>Reduzieren einer Liste mit Listen

```csharp
// Transforms the list of kennels into a list of all their dogs.
var allDogsFromKennels = kennels.SelectMany(kennel => kennel.Dogs);
```

```vb
' Transforms the list of kennels into a list of all their dogs.
Dim allDogsFromKennels = kennels.SelectMany(Function(kennel) kennel.Dogs)
```

### <a name="union-between-two-sets-with-custom-comparator"></a>Vereinigung von zwei Gruppen (mit benutzerdefiniertem Vergleichsoperator)

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

### <a name="intersection-between-two-sets"></a>Schnittmenge von zwei Mengen

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

### <a name="ordering"></a>Sortieren

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

### <a name="equality-of-instance-properties"></a>Gleichheit von Instanzeigenschaften

Schließlich ein erweitertes Beispiel: Ermitteln, ob die Werte der Eigenschaften von zwei Instanzen desselben Typs gleich sind (aus [diesem StackOverflow-Beitrag](https://stackoverflow.com/a/844855) übernommen und geändert):

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

## <a name="plinq"></a>PLINQ

PLINQ (Parallel LINQ) ist eine Engine für die parallele Ausführung für LINQ-Ausdrücke. Reguläre LINQ-Ausdrücke können also im Grunde ganz einfach über eine beliebige Anzahl von Threads parallelisiert werden. Dies erfolgt über einen Aufruf von `AsParallel()` vor dem Ausdruck.

Beachten Sie Folgendes:

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

Dieser Code partitioniert bei Bedarf `facebookUsers` über Systemthreads, summiert die Gesamtanzahl der „Likes“ parallel für jeden Thread, summiert die von allen Threads berechneten Ergebnisse und bringt das Ergebnis in eine nützliche Zeichenfolge.

In Diagrammform:

![PLINQ-Diagramm](media/index/plinq-diagram.png)

Parallelisierbare CPU-gebundene Aufträge, die problemlos über LINQ ausgedrückt werden können (die also reine Funktionen ohne Nebeneffekte darstellen) sind gute Kandidaten für PLINQ. Für Aufträge, die einen Nebeneffekt _haben_, sollten Sie die [Task Parallel Library](../parallel-programming/task-parallel-library-tpl.md) verwenden.

## <a name="more-resources"></a>Weitere Ressourcen

* [101 LINQ-Beispiele](/samples/dotnet/try-samples/101-linq-samples/)
* [Linqpad](https://www.linqpad.net/), eine Umgebung und eine Datenbankabfrage-Engine für C#/F#/Visual Basic
* [EduLinq](https://codeblog.jonskeet.uk/2011/02/23/reimplementing-linq-to-objects-part-45-conclusion-and-list-of-posts/), ein E-Book, in dem die Implementierung von LINQ to Objects erläutert wird
