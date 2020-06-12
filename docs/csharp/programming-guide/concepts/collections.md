---
title: Auflistungen (C#)
ms.date: 07/20/2015
ms.assetid: 317d7dc3-8587-4873-8b3e-556f86497939
ms.openlocfilehash: ecab30d50be58f810246e58e637b331d492e4a47
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241395"
---
# <a name="collections-c"></a>Auflistungen (C#)

Für eine Vielzahl von Anwendungen sollten Sie Gruppen von miteinander verwandten Objekten erstellen und verwalten. Zum Gruppieren von Objekten gibt es zwei Möglichkeiten: das Erstellen von Objektarrays und das Erstellen von Auflistungen von Objekten.

Arrays eignen sich bestens zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ. Weitere Informationen zu Arrays finden Sie unter [Arrays](../arrays/index.md).

Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Im Gegensatz zu Arrays kann sich die Gruppe von Objekten, mit denen Sie arbeiten, in Abhängigkeit von den sich ändernden Anforderungen der Anwendung dynamisch vergrößern bzw. verkleinern. Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.

Eine Auflistung ist eine Klasse. Daher müssen Sie eine Instanzen der Klasse deklarieren, bevor Sie dieser Auflistung Elemente hinzufügen können.

Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace verwenden. Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann. Wenn Sie ein Element aus einer generischen Auflistung abrufen, brauchen Sie dessen Datentyp nicht zu bestimmen oder zu konvertieren.

> [!NOTE]
> Schließen Sie bei den Beispielen in diesem Thema [using](../../language-reference/keywords/using-directive.md)-Anweisungen für die `System.Collections.Generic`- und `System.Linq`-Namespaces ein.

 **Inhalt**

- [Verwenden einer einfachen Auflistung](#BKMK_SimpleCollection)

- [Arten von Auflistungen](#BKMK_KindsOfCollections)

  - [System.Collections.Generic-Klassen](#BKMK_Generic)

  - [System.Collections.Concurrent-Klassen](#BKMK_Concurrent)

  - [System.Collections-Klassen](#BKMK_Collections)

- [Implementieren einer Auflistung von Schlüssel-Wert-Paaren](#BKMK_KeyValuePairs)

- [Verwenden von LINQ zum Zugriff auf eine Auflistung](#BKMK_LINQ)

- [Sortieren einer Auflistung](#BKMK_Sorting)

- [Definieren einer benutzerdefinierten Auflistung](#BKMK_CustomCollection)

- [Iteratoren](#BKMK_Iterators)

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Verwenden einer einfachen Auflistung

In den Beispielen in diesem Abschnitt wird die generische Klasse <xref:System.Collections.Generic.List%601> verwendet, die es Ihnen ermöglicht, mit einer stark typisierten Liste von Objekten zu arbeiten.

Im folgenden Beispiel wird eine Liste von Zeichenfolgen erstellt, und die Zeichenfolgen werden unter Verwendung einer [foreach](../../language-reference/keywords/foreach-in.md)-Anweisung durchlaufen.

```csharp
// Create a list of strings.
var salmons = new List<string>();
salmons.Add("chinook");
salmons.Add("coho");
salmons.Add("pink");
salmons.Add("sockeye");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

Wenn der Inhalt einer Auflistung im Voraus bekannt ist, können Sie einen *Auflistungsinitialisierer* verwenden, um die Auflistung zu initialisieren. Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../classes-and-structs/object-and-collection-initializers.md).

Das folgende Beispiel entspricht dem vorherigen Beispiel, außer dass ein Auflistungsinitialisierer verwendet wird, um der Auflistung Elemente hinzuzufügen.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook coho pink sockeye
```

Sie können anstelle einer [for](../../language-reference/keywords/for.md)-Anweisung eine `foreach`-Anweisung verwenden, um eine Auflistung zu durchlaufen. Sie erreichen dies, indem Sie durch die Indexposition auf die Auflistungselemente zugreifen. Der Index der Elemente beginnt mit 0 und endet an der Elementanzahl minus 1.

Im folgenden Beispiel werden die Elemente einer Auflistung unter Verwendung von `for` anstelle von `foreach` durchlaufen.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

for (var index = 0; index < salmons.Count; index++)
{
    Console.Write(salmons[index] + " ");
}
// Output: chinook coho pink sockeye
```

Im folgenden Beispiel wird ein Element aus der Auflistung entfernt, indem das zu entfernende Objekt angegeben wird.

```csharp
// Create a list of strings by using a
// collection initializer.
var salmons = new List<string> { "chinook", "coho", "pink", "sockeye" };

// Remove an element from the list by specifying
// the object.
salmons.Remove("coho");

// Iterate through the list.
foreach (var salmon in salmons)
{
    Console.Write(salmon + " ");
}
// Output: chinook pink sockeye
```

Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Anstelle einer `foreach`-Anweisung wird eine [for](../../language-reference/keywords/for.md)-Anweisung verwendet, die die Elemente in absteigender Reihenfolge durchläuft. Dies liegt daran, dass die <xref:System.Collections.Generic.List%601.RemoveAt%2A>-Methode dazu führt, dass Elemente nach einem entfernten Element einen niedrigeren Indexwert haben.

```csharp
var numbers = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

// Remove odd numbers.
for (var index = numbers.Count - 1; index >= 0; index--)
{
    if (numbers[index] % 2 == 1)
    {
        // Remove the element by specifying
        // the zero-based index in the list.
        numbers.RemoveAt(index);
    }
}

// Iterate through the list.
// A lambda expression is placed in the ForEach method
// of the List(T) object.
numbers.ForEach(
    number => Console.Write(number + " "));
// Output: 0 2 4 6 8
```

Für den Typ der Elemente in <xref:System.Collections.Generic.List%601> können Sie auch eine eigene Klasse definieren. Im folgenden Beispiel wird die `Galaxy`-Klasse, die von <xref:System.Collections.Generic.List%601> verwendet wird, im Code definiert.

```csharp
private static void IterateThroughList()
{
    var theGalaxies = new List<Galaxy>
        {
            new Galaxy() { Name="Tadpole", MegaLightYears=400},
            new Galaxy() { Name="Pinwheel", MegaLightYears=25},
            new Galaxy() { Name="Milky Way", MegaLightYears=0},
            new Galaxy() { Name="Andromeda", MegaLightYears=3}
        };

    foreach (Galaxy theGalaxy in theGalaxies)
    {
        Console.WriteLine(theGalaxy.Name + "  " + theGalaxy.MegaLightYears);
    }

    // Output:
    //  Tadpole  400
    //  Pinwheel  25
    //  Milky Way  0
    //  Andromeda  3
}

public class Galaxy
{
    public string Name { get; set; }
    public int MegaLightYears { get; set; }
}
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a>Arten von Auflistungen

Viele häufig verwendete Sammlungen werden von .NET bereitgestellt. Jeder Auflistungstyp ist für einen speziellen Zweck ausgelegt.

Einige der häufig verwendeten Auflistungsklassen werden in diesem Abschnitt beschrieben:

- <xref:System.Collections.Generic>-Klassen

- <xref:System.Collections.Concurrent>-Klassen

- <xref:System.Collections>-Klassen

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>System.Collections.Generic-Klassen

Zum Erstellen einer generischen Auflistung verwenden Sie eine der Klassen im <xref:System.Collections.Generic>-Namespace. Eine generische Auflistung ist sinnvoll, wenn jedes Element der Auflistung zum gleichen Datentyp gehört. Eine generische Auflistung erzwingt eine starke Typisierung, da ihr nur Elemente des gewünschten Datentyps hinzugefügt werden können.

In der folgenden Tabelle werden einige der häufig verwendeten Klassen des <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace aufgelistet:

|Klasse|Beschreibung|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, deren Reihenfolge anhand des Schlüssels bestimmt wird.|
|<xref:System.Collections.Generic.List%601>|Stellt eine Liste von Objekten dar, auf die über einen Index zugegriffen werden kann. Stellt Methoden zum Durchsuchen, Sortieren und Bearbeiten von Listen bereit.|
|<xref:System.Collections.Generic.Queue%601>|Stellt eine FIFO-Auflistung (First In, First Out) von Objekten dar.|
|<xref:System.Collections.Generic.SortedList%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, die auf Grundlage der zugeordneten <xref:System.Collections.Generic.IComparer%601>-Implementierung nach den Schlüsseln sortiert sind.|
|<xref:System.Collections.Generic.Stack%601>|Stellt eine LIFO-Auflistung (Last In, First Out) von Objekten dar.|

Weitere Informationen finden Sie unter [Häufig verwendete Auflistungstypen](../../../standard/collections/commonly-used-collection-types.md), [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md) und <xref:System.Collections.Generic>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>System.Collections.Concurrent-Klassen

In .NET Framework 4 oder höher stellen die Sammlungen im Namespace <xref:System.Collections.Concurrent> effiziente, threadsichere Vorgänge für den Zugriff auf Sammlungselemente über mehrere Threads bereit.

Die Klassen im <xref:System.Collections.Concurrent>-Namespace sollten anstelle von entsprechenden Typen in <xref:System.Collections.Generic?displayProperty=nameWithType>- und <xref:System.Collections?displayProperty=nameWithType>-Namespaces verwendet werden, wenn mehrere Threads gleichzeitig auf die Auflistung zugreifen. Weitere Informationen finden Sie unter [Threadsichere Auflistungen](../../../standard/collections/thread-safe/index.md) und <xref:System.Collections.Concurrent>.

Einige der in die <xref:System.Collections.Concurrent>-Namespaces aufgenommenen Klassen sind <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a>System.Collections-Klassen

Bei den Klassen im <xref:System.Collections?displayProperty=nameWithType>-Namespace werden Elemente nicht als speziell typisierte Objekte, sondern als Objekte vom Typ `Object` gespeichert.

Sofern möglich sollten die generischen Auflistungen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace oder <xref:System.Collections.Concurrent>-Namespace anstelle der älteren Typen im `System.Collections`-Namespace verwendet werden.

In der folgenden Tabelle werden einige der häufig verwendeten Klassen im `System.Collections`-Namespace aufgelistet:

|Klasse|Beschreibung|
|---|---|
|<xref:System.Collections.ArrayList>|Stellt ein Array von Objekten dar, das je nach Bedarf dynamisch vergrößert wird.|
|<xref:System.Collections.Hashtable>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, die auf Grundlage des Hashcodes des Schlüssels geordnet sind.|
|<xref:System.Collections.Queue>|Stellt eine FIFO-Auflistung (First In, First Out) von Objekten dar.|
|<xref:System.Collections.Stack>|Stellt eine LIFO-Auflistung (Last In, First Out) von Objekten dar.|

Der <xref:System.Collections.Specialized>-Namespace bietet spezialisierte und stark typisierte Auflistungsklassen, beispielsweise für Zeichenfolgenauflistungen sowie für Wörterbücher mit verketteten Listen und Hybridwörterbücher.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementieren einer Auflistung von Schlüssel/Wert-Paaren

Die generische Auflistung <xref:System.Collections.Generic.Dictionary%602> ermöglicht es Ihnen, unter Verwendung des Schlüssels der einzelnen Elemente auf die Elemente einer Auflistung zuzugreifen. Jede Hinzufügung zum Wörterbuch besteht aus einem Wert und dem zugeordneten Schlüssel. Ein Wert kann anhand des zugehörigen Schlüssels schnell abgerufen werden, da die `Dictionary`-Klasse in Form einer Hashtabelle implementiert ist.

Das folgende Beispiel erstellt eine `Dictionary`-Auflistung und durchläuft das Wörterbuch unter Verwendung einer `foreach`-Anweisung.

```csharp
private static void IterateThruDictionary()
{
    Dictionary<string, Element> elements = BuildDictionary();

    foreach (KeyValuePair<string, Element> kvp in elements)
    {
        Element theElement = kvp.Value;

        Console.WriteLine("key: " + kvp.Key);
        Console.WriteLine("values: " + theElement.Symbol + " " +
            theElement.Name + " " + theElement.AtomicNumber);
    }
}

private static Dictionary<string, Element> BuildDictionary()
{
    var elements = new Dictionary<string, Element>();

    AddToDictionary(elements, "K", "Potassium", 19);
    AddToDictionary(elements, "Ca", "Calcium", 20);
    AddToDictionary(elements, "Sc", "Scandium", 21);
    AddToDictionary(elements, "Ti", "Titanium", 22);

    return elements;
}

private static void AddToDictionary(Dictionary<string, Element> elements,
    string symbol, string name, int atomicNumber)
{
    Element theElement = new Element();

    theElement.Symbol = symbol;
    theElement.Name = name;
    theElement.AtomicNumber = atomicNumber;

    elements.Add(key: theElement.Symbol, value: theElement);
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

Wenn stattdessen ein Auflistungsinitialisierer zum Erstellen der `Dictionary`-Auflistung verwendet werden soll, können Sie die `BuildDictionary`- und `AddToDictionary`-Methoden durch die folgende Methode ersetzen.

```csharp
private static Dictionary<string, Element> BuildDictionary2()
{
    return new Dictionary<string, Element>
    {
        {"K",
            new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        {"Ca",
            new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        {"Sc",
            new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        {"Ti",
            new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}
```

Im folgenden Beispiel werden die <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>-Methode und die <xref:System.Collections.Generic.Dictionary%602.Item%2A>-Eigenschaft von `Dictionary` verwendet, um anhand des Schlüssels schnell nach einem Element zu suchen. Die `Item`-Eigenschaft ermöglicht den Zugriff auf ein Element in der `elements`-Auflistung unter Verwendung des `elements[symbol]`-Codes in C#.

```csharp
private static void FindInDictionary(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    if (elements.ContainsKey(symbol) == false)
    {
        Console.WriteLine(symbol + " not found");
    }
    else
    {
        Element theElement = elements[symbol];
        Console.WriteLine("found: " + theElement.Name);
    }
}
```

Im folgenden Beispiel wird stattdessen die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode verwendet, um anhand des Schlüssels schnell nach einem Element zu suchen.

```csharp
private static void FindInDictionary2(string symbol)
{
    Dictionary<string, Element> elements = BuildDictionary();

    Element theElement = null;
    if (elements.TryGetValue(symbol, out theElement) == false)
        Console.WriteLine(symbol + " not found");
    else
        Console.WriteLine("found: " + theElement.Name);
}
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a>Verwenden von LINQ zum Zugriff auf eine Auflistung

LINQ (Language-Integrated Query) kann verwendet werden, um auf Auflistungen zuzugreifen. LINQ-Abfragen stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. Weitere Informationen finden Sie unter [Erste Schritte mit LINQ in C#](linq/index.md).

Im folgenden Beispiel wird eine LINQ-Abfrage für eine generische `List` ausgeführt. Die LINQ-Abfrage gibt eine andere Auflistung zurück, die die Ergebnisse enthält.

```csharp
private static void ShowLINQ()
{
    List<Element> elements = BuildList();

    // LINQ Query.
    var subset = from theElement in elements
                 where theElement.AtomicNumber < 22
                 orderby theElement.Name
                 select theElement;

    foreach (Element theElement in subset)
    {
        Console.WriteLine(theElement.Name + " " + theElement.AtomicNumber);
    }

    // Output:
    //  Calcium 20
    //  Potassium 19
    //  Scandium 21
}

private static List<Element> BuildList()
{
    return new List<Element>
    {
        { new Element() { Symbol="K", Name="Potassium", AtomicNumber=19}},
        { new Element() { Symbol="Ca", Name="Calcium", AtomicNumber=20}},
        { new Element() { Symbol="Sc", Name="Scandium", AtomicNumber=21}},
        { new Element() { Symbol="Ti", Name="Titanium", AtomicNumber=22}}
    };
}

public class Element
{
    public string Symbol { get; set; }
    public string Name { get; set; }
    public int AtomicNumber { get; set; }
}
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a>Sortieren einer Auflistung

Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. In dem Beispiel werden Instanzen der `Car`-Klasse sortiert, die in <xref:System.Collections.Generic.List%601> gespeichert sind. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.

Jeder Aufruf der <xref:System.IComparable%601.CompareTo%2A>-Methode führt einen einzelnen Vergleich aus, der für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.

In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>-Methode von <xref:System.Collections.Generic.List%601> führt dazu, dass die `CompareTo`-Methode für die `Car`-Objekte in der `List` automatisch aufgerufen wird.

```csharp
private static void ListCars()
{
    var cars = new List<Car>
    {
        { new Car() { Name = "car1", Color = "blue", Speed = 20}},
        { new Car() { Name = "car2", Color = "red", Speed = 50}},
        { new Car() { Name = "car3", Color = "green", Speed = 10}},
        { new Car() { Name = "car4", Color = "blue", Speed = 50}},
        { new Car() { Name = "car5", Color = "blue", Speed = 30}},
        { new Car() { Name = "car6", Color = "red", Speed = 60}},
        { new Car() { Name = "car7", Color = "green", Speed = 50}}
    };

    // Sort the cars by color alphabetically, and then by speed
    // in descending order.
    cars.Sort();

    // View all of the cars.
    foreach (Car thisCar in cars)
    {
        Console.Write(thisCar.Color.PadRight(5) + " ");
        Console.Write(thisCar.Speed.ToString() + " ");
        Console.Write(thisCar.Name);
        Console.WriteLine();
    }

    // Output:
    //  blue  50 car4
    //  blue  30 car5
    //  blue  20 car1
    //  green 50 car7
    //  green 10 car3
    //  red   60 car6
    //  red   50 car2
}

public class Car : IComparable<Car>
{
    public string Name { get; set; }
    public int Speed { get; set; }
    public string Color { get; set; }

    public int CompareTo(Car other)
    {
        // A call to this method makes a single comparison that is
        // used for sorting.

        // Determine the relative order of the objects being compared.
        // Sort by color alphabetically, and then by speed in
        // descending order.

        // Compare the colors.
        int compare;
        compare = String.Compare(this.Color, other.Color, true);

        // If the colors are the same, compare the speeds.
        if (compare == 0)
        {
            compare = this.Speed.CompareTo(other.Speed);

            // Use descending order for speed.
            compare = -compare;
        }

        return compare;
    }
}
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a>Definieren einer benutzerdefinierten Auflistung

Sie können eine Auflistung definieren, indem Sie die <xref:System.Collections.Generic.IEnumerable%601>- oder <xref:System.Collections.IEnumerable>-Schnittstelle implementieren.

Sie können zwar eine benutzerdefinierte Sammlung definieren, in der Regel ist es aber besser, die in .NET enthaltenen Sammlungen zu verwenden. Diese werden weiter oben unter [Arten von Sammlungen](#BKMK_KindsOfCollections) beschrieben.

Im folgenden Beispiel wird die benutzerdefinierte Auflistungsklasse `AllColors` definiert. Diese Klasse implementiert die <xref:System.Collections.IEnumerable>-Schnittstelle, die die Implementierung der <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode erfordert.

Die `GetEnumerator`-Methode gibt eine Instanz der `ColorEnumerator`-Klasse zurück. `ColorEnumerator` implementiert die <xref:System.Collections.IEnumerator>-Schnittstelle, die die Implementierung der <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft, der <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode und der <xref:System.Collections.IEnumerator.Reset%2A>-Methode erfordert.

```csharp
private static void ListColors()
{
    var colors = new AllColors();

    foreach (Color theColor in colors)
    {
        Console.Write(theColor.Name + " ");
    }
    Console.WriteLine();
    // Output: red blue green
}

// Collection class.
public class AllColors : System.Collections.IEnumerable
{
    Color[] _colors =
    {
        new Color() { Name = "red" },
        new Color() { Name = "blue" },
        new Color() { Name = "green" }
    };

    public System.Collections.IEnumerator GetEnumerator()
    {
        return new ColorEnumerator(_colors);

        // Instead of creating a custom enumerator, you could
        // use the GetEnumerator of the array.
        //return _colors.GetEnumerator();
    }

    // Custom enumerator.
    private class ColorEnumerator : System.Collections.IEnumerator
    {
        private Color[] _colors;
        private int _position = -1;

        public ColorEnumerator(Color[] colors)
        {
            _colors = colors;
        }

        object System.Collections.IEnumerator.Current
        {
            get
            {
                return _colors[_position];
            }
        }

        bool System.Collections.IEnumerator.MoveNext()
        {
            _position++;
            return (_position < _colors.Length);
        }

        void System.Collections.IEnumerator.Reset()
        {
            _position = -1;
        }
    }
}

// Element class.
public class Color
{
    public string Name { get; set; }
}
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a>Iterators

Ein *Iterator* wird verwendet, um eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Methode oder ein `get`-Accessor sein. Ein Iterator verwendet eine [yield return](../../language-reference/keywords/yield.md)-Anweisung, um jedes Element der Auflistung separat zurückzugeben.

Sie rufen einen Iterator mithilfe einer [foreach](../../language-reference/keywords/foreach-in.md)-Anweisung auf. Jede Iteration der `foreach`-Schleife ruft den Iterator auf. Wenn eine `yield return`-Anweisung im Iterator erreicht ist, wird ein Ausdruck zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Weitere Informationen finden Sie unter [Iteratoren (C#)](./iterators.md).

Im folgenden Beispiel wird eine Iteratormethode verwendet. Die Iteratormethode verfügt über eine `yield return`-Anweisung, die sich innerhalb einer [for](../../language-reference/keywords/for.md)-Schleife befindet. In der `ListEvenNumbers`-Methode erstellt jede Iteration des `foreach`-Anweisungstexts einen Aufruf der Iteratormethode, der zur nächsten `yield return`-Anweisung übergeht.

```csharp
private static void ListEvenNumbers()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    Console.WriteLine();
    // Output: 6 8 10 12 14 16 18
}

private static IEnumerable<int> EvenSequence(
    int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (var number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="see-also"></a>Siehe auch

- [Objekt- und Auflistungsinitialisierer](../classes-and-structs/object-and-collection-initializers.md)
- [Programmierkonzepte (C#)](./index.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (C#)](./linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../standard/parallel-programming/introduction-to-plinq.md)
- [Sammlungen und Datenstrukturen](../../../standard/collections/index.md)
- [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md)
- [Vergleiche und Sortierungen innerhalb von Auflistungen](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Verwenden von generischen Auflistungen](../../../standard/collections/when-to-use-generic-collections.md)
