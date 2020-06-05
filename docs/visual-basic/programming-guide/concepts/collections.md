---
title: Sammlungen
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: f264a0f9ee15707daf4bece5651b9f5f07ebbc39
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400654"
---
# <a name="collections-visual-basic"></a>Auflistungen (Visual Basic)

Für eine Vielzahl von Anwendungen sollten Sie Gruppen von miteinander verwandten Objekten erstellen und verwalten. Zum Gruppieren von Objekten gibt es zwei Möglichkeiten: das Erstellen von Objektarrays und das Erstellen von Auflistungen von Objekten.

Arrays eignen sich bestens zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ. Weitere Informationen zu Arrays finden Sie unter [Arrays](../language-features/arrays/index.md).

Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Im Gegensatz zu Arrays kann sich die Gruppe von Objekten, mit denen Sie arbeiten, in Abhängigkeit von den sich ändernden Anforderungen der Anwendung dynamisch vergrößern bzw. verkleinern. Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.

Eine Auflistung ist eine Klasse. Daher müssen Sie eine Instanzen der Klasse deklarieren, bevor Sie dieser Auflistung Elemente hinzufügen können.

Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace verwenden. Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann. Wenn Sie ein Element aus einer generischen Auflistung abrufen, brauchen Sie dessen Datentyp nicht zu bestimmen oder zu konvertieren.

> [!NOTE]
> Schließen Sie für die Beispiele in diesem Thema [Imports](../../language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisungen für `System.Collections.Generic` die `System.Linq` Namespaces und ein.

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a>Verwenden einer einfachen Auflistung

In den Beispielen in diesem Abschnitt wird die generische Klasse <xref:System.Collections.Generic.List%601> verwendet, die es Ihnen ermöglicht, mit einer stark typisierten Liste von Objekten zu arbeiten.

Im folgenden Beispiel wird eine Liste von Zeichen folgen erstellt und dann Durchlaufen der Zeichen folgen mithilfe eines [for each... Next](../../language-reference/statements/for-each-next-statement.md) -Anweisung.

```vb
' Create a list of strings.
Dim salmons As New List(Of String)
salmons.Add("chinook")
salmons.Add("coho")
salmons.Add("pink")
salmons.Add("sockeye")

' Iterate through the list.
For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

Wenn der Inhalt einer Auflistung im Voraus bekannt ist, können Sie einen *Auflistungsinitialisierer* verwenden, um die Auflistung zu initialisieren. Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../language-features/collection-initializers/index.md).

Das folgende Beispiel entspricht dem vorherigen Beispiel, außer dass ein Auflistungsinitialisierer verwendet wird, um der Auflistung Elemente hinzuzufügen.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook coho pink sockeye
```

Sie können eine [for... Next](../../language-reference/statements/for-next-statement.md) -Anweisung anstelle einer- `For Each` Anweisung, um eine Auflistung zu durchlaufen. Sie erreichen dies, indem Sie durch die Indexposition auf die Auflistungselemente zugreifen. Der Index der Elemente beginnt mit 0 und endet an der Elementanzahl minus 1.

Im folgenden Beispiel werden die Elemente einer Auflistung unter Verwendung von `For…Next` anstelle von `For Each` durchlaufen.

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

Im folgenden Beispiel wird ein Element aus der Auflistung entfernt, indem das zu entfernende Objekt angegeben wird.

```vb
' Create a list of strings by using a
' collection initializer.
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

' Remove an element in the list by specifying
' the object.
salmons.Remove("coho")

For Each salmon As String In salmons
    Console.Write(salmon & " ")
Next
'Output: chinook pink sockeye
```

Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Anstelle einer- `For Each` Anweisung, a [für... Die nächste](../../language-reference/statements/for-next-statement.md) Anweisung, die in absteigender Reihenfolge iteriert, wird verwendet. Dies liegt daran, dass die <xref:System.Collections.Generic.List%601.RemoveAt%2A>-Methode dazu führt, dass Elemente nach einem entfernten Element einen niedrigeren Indexwert haben.

```vb
Dim numbers As New List(Of Integer) From
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

' Remove odd numbers.
For index As Integer = numbers.Count - 1 To 0 Step -1
    If numbers(index) Mod 2 = 1 Then
        ' Remove the element by specifying
        ' the zero-based index in the list.
        numbers.RemoveAt(index)
    End If
Next

' Iterate through the list.
' A lambda expression is placed in the ForEach method
' of the List(T) object.
numbers.ForEach(
    Sub(number) Console.Write(number & " "))
' Output: 0 2 4 6 8
```

Für den Typ der Elemente in <xref:System.Collections.Generic.List%601> können Sie auch eine eigene Klasse definieren. Im folgenden Beispiel wird die `Galaxy`-Klasse, die von <xref:System.Collections.Generic.List%601> verwendet wird, im Code definiert.

```vb
Private Sub IterateThroughList()
    Dim theGalaxies As New List(Of Galaxy) From
        {
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}
        }

    For Each theGalaxy In theGalaxies
        With theGalaxy
            Console.WriteLine(.Name & "  " & .MegaLightYears)
        End With
    Next

    ' Output:
    '  Tadpole  400
    '  Pinwheel  25
    '  Milky Way  0
    '  Andromeda  3
End Sub

Public Class Galaxy
    Public Property Name As String
    Public Property MegaLightYears As Integer
End Class
```

<a name="BKMK_KindsOfCollections"></a>

## <a name="kinds-of-collections"></a>Arten von Auflistungen

Viele allgemeine Auflistungen werden von .NET Framework bereitgestellt. Jeder Auflistungstyp ist für einen speziellen Zweck ausgelegt.

Einige der häufig verwendeten Auflistungsklassen werden in diesem Abschnitt beschrieben:

- <xref:System.Collections.Generic>-Klassen

- <xref:System.Collections.Concurrent>-Klassen

- <xref:System.Collections>-Klassen

- Visual Basic-`Collection`sklasse

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a>System.Collections.Generic-Klassen

Zum Erstellen einer generischen Auflistung verwenden Sie eine der Klassen im <xref:System.Collections.Generic>-Namespace. Eine generische Auflistung ist sinnvoll, wenn jedes Element der Auflistung zum gleichen Datentyp gehört. Eine generische Auflistung erzwingt eine starke Typisierung, da ihr nur Elemente des gewünschten Datentyps hinzugefügt werden können.

In der folgenden Tabelle werden einige der häufig verwendeten Klassen des <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace aufgelistet:

|Klasse|BESCHREIBUNG|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, deren Reihenfolge anhand des Schlüssels bestimmt wird.|
|<xref:System.Collections.Generic.List%601>|Stellt eine Liste von Objekten dar, auf die über einen Index zugegriffen werden kann. Stellt Methoden zum Durchsuchen, Sortieren und Bearbeiten von Listen bereit.|
|<xref:System.Collections.Generic.Queue%601>|Stellt eine FIFO-Auflistung (First In, First Out) von Objekten dar.|
|<xref:System.Collections.Generic.SortedList%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, die auf Grundlage der zugeordneten <xref:System.Collections.Generic.IComparer%601>-Implementierung nach den Schlüsseln sortiert sind.|
|<xref:System.Collections.Generic.Stack%601>|Stellt eine LIFO-Auflistung (Last In, First Out) von Objekten dar.|

Weitere Informationen finden Sie unter [Häufig verwendete Auflistungstypen](../../../standard/collections/commonly-used-collection-types.md), [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md) und <xref:System.Collections.Generic?displayProperty=nameWithType>.

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a>System.Collections.Concurrent-Klassen

In .NET Framework 4 oder höher stellen die Auflistungen im Namespace <xref:System.Collections.Concurrent> effiziente threadsichere Vorgänge für den Zugriff auf Auflistungselemente aus mehreren Threads bereit.

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

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a>Visual Basic-Auflistungsklasse

Sie können die Visual Basic-Klasse <xref:Microsoft.VisualBasic.Collection> verwenden, um auf ein Auflistungselement zuzugreifen, indem Sie entweder einen numerischen Index oder einen `String`schlüssel verwenden. Sie können einem Auflistungsobjekt Elemente entweder mit oder ohne Angabe eines Schlüssels hinzufügen. Wenn Sie ein Element ohne einen Schlüssel hinzufügen, müssen Sie seinen numerischen Index verwenden, um darauf zuzugreifen.

Die Visual Basic-Klasse `Collection` speichert alle Elemente als `Object`-Typ, damit Elemente eines beliebigen Datentyps hinzugefügt werden können. Es gibt keine Vorkehrung, die das Hinzufügen ungeeigneter Datentypen verhindert.

Wenn Sie die Visual Basic-Klasse `Collection` verwenden, hat das erste Element in einer Auflistung einen Index von 1. Dies unterscheidet sich von den .NET Framework-Auflistungsklassen, deren Startindex 0 ist.

Sofern möglich sollten die generischen Auflistungen im <xref:System.Collections.Generic?displayProperty=nameWithType>-Namespace oder im <xref:System.Collections.Concurrent>-Namespace anstelle der Visual Basic-Klasse `Collection` verwendet werden.

Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Collection>.

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementieren einer Auflistung von Schlüssel/Wert-Paaren

Die generische Auflistung <xref:System.Collections.Generic.Dictionary%602> ermöglicht es Ihnen, unter Verwendung des Schlüssels der einzelnen Elemente auf die Elemente einer Auflistung zuzugreifen. Jede Hinzufügung zum Wörterbuch besteht aus einem Wert und dem zugeordneten Schlüssel. Ein Wert kann anhand des zugehörigen Schlüssels schnell abgerufen werden, da die `Dictionary`-Klasse in Form einer Hashtabelle implementiert ist.

Das folgende Beispiel erstellt eine `Dictionary`-Auflistung und durchläuft das Wörterbuch unter Verwendung einer `For Each`-Anweisung.

```vb
Private Sub IterateThroughDictionary()
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    For Each kvp As KeyValuePair(Of String, Element) In elements
        Dim theElement As Element = kvp.Value

        Console.WriteLine("key: " & kvp.Key)
        With theElement
            Console.WriteLine("values: " & .Symbol & " " &
                .Name & " " & .AtomicNumber)
        End With
    Next
End Sub

Private Function BuildDictionary() As Dictionary(Of String, Element)
    Dim elements As New Dictionary(Of String, Element)

    AddToDictionary(elements, "K", "Potassium", 19)
    AddToDictionary(elements, "Ca", "Calcium", 20)
    AddToDictionary(elements, "Sc", "Scandium", 21)
    AddToDictionary(elements, "Ti", "Titanium", 22)

    Return elements
End Function

Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)
    Dim theElement As New Element

    theElement.Symbol = symbol
    theElement.Name = name
    theElement.AtomicNumber = atomicNumber

    elements.Add(Key:=theElement.Symbol, value:=theElement)
End Sub

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

Wenn stattdessen ein Auflistungsinitialisierer zum Erstellen der `Dictionary`-Auflistung verwendet werden soll, können Sie die `BuildDictionary`- und `AddToDictionary`-Methoden durch die folgende Methode ersetzen.

```vb
Private Function BuildDictionary2() As Dictionary(Of String, Element)
    Return New Dictionary(Of String, Element) From
        {
            {"K", New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {"Ca", New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {"Sc", New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {"Ti", New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function
```

Im folgenden Beispiel werden die <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>-Methode und die <xref:System.Collections.Generic.Dictionary%602.Item%2A>-Eigenschaft von `Dictionary` verwendet, um anhand des Schlüssels schnell nach einem Element zu suchen. Mit der- `Item` Eigenschaft können Sie auf ein Element in der Auflistung zugreifen, `elements` indem Sie den `elements(symbol)` Code in Visual Basic verwenden.

```vb
Private Sub FindInDictionary(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    If elements.ContainsKey(symbol) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Dim theElement = elements(symbol)
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

Im folgenden Beispiel wird stattdessen die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode verwendet, um anhand des Schlüssels schnell nach einem Element zu suchen.

```vb
Private Sub FindInDictionary2(ByVal symbol As String)
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()

    Dim theElement As Element = Nothing
    If elements.TryGetValue(symbol, theElement) = False Then
        Console.WriteLine(symbol & " not found")
    Else
        Console.WriteLine("found: " & theElement.Name)
    End If
End Sub
```

<a name="BKMK_LINQ"></a>

## <a name="using-linq-to-access-a-collection"></a>Verwenden von LINQ zum Zugriff auf eine Auflistung

LINQ (Language-Integrated Query) kann verwendet werden, um auf Auflistungen zuzugreifen. LINQ-Abfragen stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. Weitere Informationen finden Sie unter [Getting Started with LINQ in Visual Basic](linq/getting-started-with-linq.md).

Im folgenden Beispiel wird eine LINQ-Abfrage für eine generische `List` ausgeführt. Die LINQ-Abfrage gibt eine andere Auflistung zurück, die die Ergebnisse enthält.

```vb
Private Sub ShowLINQ()
    Dim elements As List(Of Element) = BuildList()

    ' LINQ Query.
    Dim subset = From theElement In elements
                  Where theElement.AtomicNumber < 22
                  Order By theElement.Name

    For Each theElement In subset
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)
    Next

    ' Output:
    '  Calcium 20
    '  Potassium 19
    '  Scandium 21
End Sub

Private Function BuildList() As List(Of Element)
    Return New List(Of Element) From
        {
            {New Element With
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},
            {New Element With
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},
            {New Element With
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},
            {New Element With
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}
        }
End Function

Public Class Element
    Public Property Symbol As String
    Public Property Name As String
    Public Property AtomicNumber As Integer
End Class
```

<a name="BKMK_Sorting"></a>

## <a name="sorting-a-collection"></a>Sortieren einer Auflistung

Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. In dem Beispiel werden Instanzen der `Car`-Klasse sortiert, die in <xref:System.Collections.Generic.List%601> gespeichert sind. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.

Jeder Aufruf der <xref:System.IComparable%601.CompareTo%2A>-Methode führt einen einzelnen Vergleich aus, der für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.

In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>-Methode von <xref:System.Collections.Generic.List%601> führt dazu, dass die `CompareTo`-Methode für die `Car`-Objekte in der `List` automatisch aufgerufen wird.

```vb
Public Sub ListCars()

    ' Create some new cars.
    Dim cars As New List(Of Car) From
    {
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}
    }

    ' Sort the cars by color alphabetically, and then by speed
    ' in descending order.
    cars.Sort()

    ' View all of the cars.
    For Each thisCar As Car In cars
        Console.Write(thisCar.Color.PadRight(5) & " ")
        Console.Write(thisCar.Speed.ToString & " ")
        Console.Write(thisCar.Name)
        Console.WriteLine()
    Next

    ' Output:
    '  blue  50 car4
    '  blue  30 car5
    '  blue  20 car1
    '  green 50 car7
    '  green 10 car3
    '  red   60 car6
    '  red   50 car2
End Sub

Public Class Car
    Implements IComparable(Of Car)

    Public Property Name As String
    Public Property Speed As Integer
    Public Property Color As String

    Public Function CompareTo(ByVal other As Car) As Integer _
        Implements System.IComparable(Of Car).CompareTo
        ' A call to this method makes a single comparison that is
        ' used for sorting.

        ' Determine the relative order of the objects being compared.
        ' Sort by color alphabetically, and then by speed in
        ' descending order.

        ' Compare the colors.
        Dim compare As Integer
        compare = String.Compare(Me.Color, other.Color, True)

        ' If the colors are the same, compare the speeds.
        If compare = 0 Then
            compare = Me.Speed.CompareTo(other.Speed)

            ' Use descending order for speed.
            compare = -compare
        End If

        Return compare
    End Function
End Class
```

<a name="BKMK_CustomCollection"></a>

## <a name="defining-a-custom-collection"></a>Definieren einer benutzerdefinierten Auflistung

Sie können eine Auflistung definieren, indem Sie die <xref:System.Collections.Generic.IEnumerable%601>- oder <xref:System.Collections.IEnumerable>-Schnittstelle implementieren. Weitere Informationen finden Sie unter Auflisten [einer Auflistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).

Sie können zwar eine benutzerdefinierte Auflistung definieren, in der Regel ist es aber besser, die in .NET Framework enthaltenen Auflistungen zu verwenden. Diese werden unter [Arten von Auflistungen](#kinds-of-collections) weiter oben in diesem Thema beschrieben.

Im folgenden Beispiel wird die benutzerdefinierte Auflistungsklasse `AllColors` definiert. Diese Klasse implementiert die <xref:System.Collections.IEnumerable>-Schnittstelle, die die Implementierung der <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode erfordert.

Die `GetEnumerator`-Methode gibt eine Instanz der `ColorEnumerator`-Klasse zurück. `ColorEnumerator` implementiert die <xref:System.Collections.IEnumerator>-Schnittstelle, die die Implementierung der <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft, der <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode und der <xref:System.Collections.IEnumerator.Reset%2A>-Methode erfordert.

```vb
Public Sub ListColors()
    Dim colors As New AllColors()

    For Each theColor As Color In colors
        Console.Write(theColor.Name & " ")
    Next
    Console.WriteLine()
    ' Output: red blue green
End Sub

' Collection class.
Public Class AllColors
    Implements System.Collections.IEnumerable

    Private _colors() As Color =
    {
        New Color With {.Name = "red"},
        New Color With {.Name = "blue"},
        New Color With {.Name = "green"}
    }

    Public Function GetEnumerator() As System.Collections.IEnumerator _
        Implements System.Collections.IEnumerable.GetEnumerator

        Return New ColorEnumerator(_colors)

        ' Instead of creating a custom enumerator, you could
        ' use the GetEnumerator of the array.
        'Return _colors.GetEnumerator
    End Function

    ' Custom enumerator.
    Private Class ColorEnumerator
        Implements System.Collections.IEnumerator

        Private _colors() As Color
        Private _position As Integer = -1

        Public Sub New(ByVal colors() As Color)
            _colors = colors
        End Sub

        Public ReadOnly Property Current() As Object _
            Implements System.Collections.IEnumerator.Current
            Get
                Return _colors(_position)
            End Get
        End Property

        Public Function MoveNext() As Boolean _
            Implements System.Collections.IEnumerator.MoveNext
            _position += 1
            Return (_position < _colors.Length)
        End Function

        Public Sub Reset() Implements System.Collections.IEnumerator.Reset
            _position = -1
        End Sub
    End Class
End Class

' Element class.
Public Class Color
    Public Property Name As String
End Class
```

<a name="BKMK_Iterators"></a>

## <a name="iterators"></a>Iterators

Ein *Iterator* wird verwendet, um eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Methode oder ein `get`-Accessor sein. Ein Iterator verwendet eine [Yield](../../language-reference/statements/yield-statement.md) -Anweisung, um jedes Element der Auflistung einzeln zurückzugeben.

Sie nennen einen Iterator mithilfe eines [for each-... Next](../../language-reference/statements/for-each-next-statement.md) -Anweisung. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield`-Anweisung im Iterator erreicht ist, wird ein Ausdruck zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Weitere Informationen finden Sie unter [Iteratoren (Visual Basic)](iterators.md).

Im folgenden Beispiel wird eine Iteratormethode verwendet. Die Iteratormethode verfügt über eine- `Yield` Anweisung, die sich innerhalb einer [for... Nächste](../../language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers`-Methode erstellt jede Iteration des `For Each`-Anweisungstexts einen Aufruf der Iteratormethode, der zur nächsten `Yield`-Anweisung übergeht.

```vb
Public Sub ListEvenNumbers()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    Console.WriteLine()
    ' Output: 6 8 10 12 14 16 18
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As IEnumerable(Of Integer)

' Yield even numbers in the range.
    For number = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="see-also"></a>Siehe auch

- [Sammlungsinitialisierer](../language-features/collection-initializers/index.md)
- [Programmier Konzepte (Visual Basic)](index.md)
- [Option Strict-Anweisung](../../language-reference/statements/option-strict-statement.md)
- [LINQ to Objects (Visual Basic)](linq/linq-to-objects.md)
- [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../standard/parallel-programming/introduction-to-plinq.md)
- [Sammlungen und Datenstrukturen](../../../standard/collections/index.md)
- [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md)
- [Vergleiche und Sortierungen innerhalb von Auflistungen](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [Verwenden von generischen Auflistungen](../../../standard/collections/when-to-use-generic-collections.md)
