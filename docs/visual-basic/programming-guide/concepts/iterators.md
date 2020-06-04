---
title: Iterators
ms.date: 07/20/2015
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
ms.openlocfilehash: e638d35aeb86837d91fb14681d300772e3c2375a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410928"
---
# <a name="iterators-visual-basic"></a>Iteratoren (Visual Basic)

Ein *Iterator* kann verwendet werden, um Auflistungen wie Listen und Arrays schrittweise durchzugehen.

Eine Iteratormethode oder eine `get`-Zugriffsmethode führt eine benutzerdefinierte Iteration einer Auflistung durch. Eine Iteratormethode verwendet die [Yield](../../language-reference/statements/yield-statement.md) -Anweisung, um jedes Element einzeln zurückzugeben. Wenn eine `Yield`-Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Sie verwenden einen Iterator aus Client Code, indem Sie [für jede... Next](../../language-reference/statements/for-each-next-statement.md) -Anweisung oder mithilfe einer LINQ-Abfrage.

In folgendem Beispiel führt die erste Iteration der `For Each`-Schleife dazu, dass die Ausführung solange in der Iteratormethode `SomeNumbers` fortschreitet, bis der ersten `Yield`-Anweisung erreicht wird. Diese Iteration gibt den Wert 3 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten. In der nächsten Iteration der Schleife wird die Ausführung in der Iteratormethode da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einem `Yield`-Ausdruck. Diese Iteration gibt den Wert 5 zurück, und die aktuelle Postion in der Iteratormethode wird beibehalten. Die Schleife wird beendet, wenn das Ende der Iteratormethode erreicht wird.

```vb
Sub Main()
    For Each number As Integer In SomeNumbers()
        Console.Write(number & " ")
    Next
    ' Output: 3 5 8
    Console.ReadKey()
End Sub

Private Iterator Function SomeNumbers() As System.Collections.IEnumerable
    Yield 3
    Yield 5
    Yield 8
End Function
```

Der Rückgabetyp einer Iteratormethode oder einer `get`-Zugriffsmethode kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.

Sie können eine- `Exit Function` oder- `Return` Anweisung verwenden, um die Iterationen zu beenden.

Eine Visual Basic Iteratorfunktion oder `get` Accessor-Deklaration enthält einen [iteratormodifizierer](../../language-reference/modifiers/iterator.md) .

Iteratoren wurden in Visual Basic in Visual Studio 2012 eingeführt.

**Inhalt**

- [Einfacher Iterator](#BKMK_SimpleIterator)

- [Erstellen einer Auflistungsklasse](#BKMK_CollectionClass)

- [Try-Blöcke](#BKMK_TryBlocks)

- [Anonyme Methoden](#BKMK_AnonymousMethods)

- [Verwenden von Iteratoren mit einer generischen Liste](#BKMK_GenericList)

- [Syntaxinformationen](#BKMK_SyntaxInformation)

- [Technische Implementierung](#BKMK_Technical)

- [Verwendung von Iteratoren](#BKMK_UseOfIterators)

> [!NOTE]
> Fügen Sie für alle Beispiele im Thema mit Ausnahme des einfachen iteratorbeispiels [Import](../../language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisungen für `System.Collections` die `System.Collections.Generic` Namespaces und hinzu.

## <a name="simple-iterator"></a><a name="BKMK_SimpleIterator"></a>Einfacher Iterator

Im folgenden Beispiel wird eine einzelne- `Yield` Anweisung in einer [for... Nächste](../../language-reference/statements/for-next-statement.md) Schleife. In der `Main`-Methode erstellt jede Iteration des `For Each`-Anweisungstexts einen Aufruf der Iteratorfunktion, die zur nächsten `Yield`-Anweisung übergeht.

```vb
Sub Main()
    For Each number As Integer In EvenSequence(5, 18)
        Console.Write(number & " ")
    Next
    ' Output: 6 8 10 12 14 16 18
    Console.ReadKey()
End Sub

Private Iterator Function EvenSequence(
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _
As System.Collections.Generic.IEnumerable(Of Integer)

    ' Yield even numbers in the range.
    For number As Integer = firstNumber To lastNumber
        If number Mod 2 = 0 Then
            Yield number
        End If
    Next
End Function
```

## <a name="creating-a-collection-class"></a><a name="BKMK_CollectionClass"></a>Erstellen einer Sammlungsklasse

In folgendem Beispiel implementiert die `DaysOfTheWeek`-Klasse die <xref:System.Collections.IEnumerable>-Schnittstelle, die eine <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode erfordert. Der Compiler ruft die Methode `GetEnumerator` implizit auf, die <xref:System.Collections.IEnumerator> zurückgibt.

Die `GetEnumerator` -Methode gibt jede Zeichenfolge einzeln mithilfe der `Yield` -Anweisung zurück, und ein- `Iterator` Modifizierer ist in der Funktionsdeklaration.

```vb
Sub Main()
    Dim days As New DaysOfTheWeek()
    For Each day As String In days
        Console.Write(day & " ")
    Next
    ' Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey()
End Sub

Private Class DaysOfTheWeek
    Implements IEnumerable

    Public days =
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        ' Yield each day of the week.
        For i As Integer = 0 To days.Length - 1
            Yield days(i)
        Next
    End Function
End Class
```

Im folgenden Beispiel wird eine `Zoo`-Klasse erstellt, die eine Auflistung von Tieren enthält.

Die Anweisung `For Each`, die auf die Instanz der Klasse verweist (`theZoo`), ruft die Methode `GetEnumerator` implizit auf. Die Anweisung `For Each`, die auf die Eigenschaften `Birds` und `Mammals` verweist, verwenden die Iteratormethode `AnimalsForType`.

```vb
Sub Main()
    Dim theZoo As New Zoo()

    theZoo.AddMammal("Whale")
    theZoo.AddMammal("Rhinoceros")
    theZoo.AddBird("Penguin")
    theZoo.AddBird("Warbler")

    For Each name As String In theZoo
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros Penguin Warbler

    For Each name As String In theZoo.Birds
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Penguin Warbler

    For Each name As String In theZoo.Mammals
        Console.Write(name & " ")
    Next
    Console.WriteLine()
    ' Output: Whale Rhinoceros

    Console.ReadKey()
End Sub

Public Class Zoo
    Implements IEnumerable

    ' Private members.
    Private animals As New List(Of Animal)

    ' Public methods.
    Public Sub AddMammal(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})
    End Sub

    Public Sub AddBird(ByVal name As String)
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})
    End Sub

    Public Iterator Function GetEnumerator() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        For Each theAnimal As Animal In animals
            Yield theAnimal.Name
        Next
    End Function

    ' Public members.
    Public ReadOnly Property Mammals As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Mammal)
        End Get
    End Property

    Public ReadOnly Property Birds As IEnumerable
        Get
            Return AnimalsForType(Animal.TypeEnum.Bird)
        End Get
    End Property

    ' Private methods.
    Private Iterator Function AnimalsForType( _
    ByVal type As Animal.TypeEnum) As IEnumerable
        For Each theAnimal As Animal In animals
            If (theAnimal.Type = type) Then
                Yield theAnimal.Name
            End If
        Next
    End Function

    ' Private class.
    Private Class Animal
        Public Enum TypeEnum
            Bird
            Mammal
        End Enum

        Public Property Name As String
        Public Property Type As TypeEnum
    End Class
End Class
```

## <a name="try-blocks"></a><a name="BKMK_TryBlocks"></a>Try-Blöcke

Visual Basic lässt eine- `Yield` Anweisung im- `Try` Block eines [try... Catch... Abschließend-Anweisung](../../language-reference/statements/try-catch-finally-statement.md). Ein `Try` -Block, der über eine `Yield` -Anweisung verfügt `Catch` , kann-Blöcke aufweisen und kann über einen- `Finally` Block verfügen.

Das folgende Beispiel enthält `Try` die `Catch` Blöcke, und `Finally` in einer Iteratorfunktion. Der- `Finally` Block in der Iteratorfunktion wird ausgeführt, bevor die `For Each` Iteration beendet wird.

```vb
Sub Main()
    For Each number As Integer In Test()
        Console.WriteLine(number)
    Next
    Console.WriteLine("For Each is done.")

    ' Output:
    '  3
    '  4
    '  Something happened. Yields are done.
    '  Finally is called.
    '  For Each is done.
    Console.ReadKey()
End Sub

Private Iterator Function Test() As IEnumerable(Of Integer)
    Try
        Yield 3
        Yield 4
        Throw New Exception("Something happened. Yields are done.")
        Yield 5
        Yield 6
    Catch ex As Exception
        Console.WriteLine(ex.Message)
    Finally
        Console.WriteLine("Finally is called.")
    End Try
End Function
```

Eine- `Yield` Anweisung darf sich nicht in einem- `Catch` Block oder einem- `Finally` Block befinden.

Wenn der `For Each` Text (anstelle der Iteratormethode) eine Ausnahme auslöst, wird ein- `Catch` Block in der Iteratorfunktion nicht ausgeführt, aber ein- `Finally` Block in der Iteratorfunktion wird ausgeführt. Ein `Catch` Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die innerhalb der Iteratorfunktion auftreten.

## <a name="anonymous-methods"></a><a name="BKMK_AnonymousMethods"></a>Anonyme Methoden

In Visual Basic kann eine anonyme Funktion eine Iteratorfunktion sein. Dies wird anhand des folgenden Beispiels veranschaulicht.

```vb
Dim iterateSequence = Iterator Function() _
                      As IEnumerable(Of Integer)
                          Yield 1
                          Yield 2
                      End Function

For Each number As Integer In iterateSequence()
    Console.Write(number & " ")
Next
' Output: 1 2
Console.ReadKey()
```

Das folgende Beispiel enthält eine nicht-Iteratormethode, mit der die Argumente überprüft werden. Die-Methode gibt das Ergebnis eines anonymen Iterators zurück, der die Auflistungs Elemente beschreibt.

```vb
Sub Main()
    For Each number As Integer In GetSequence(5, 10)
        Console.Write(number & " ")
    Next
    ' Output: 5 6 7 8 9 10
    Console.ReadKey()
End Sub

Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _
As IEnumerable
    ' Validate the arguments.
    If low < 1 Then
        Throw New ArgumentException("low is too low")
    End If
    If high > 140 Then
        Throw New ArgumentException("high is too high")
    End If

    ' Return an anonymous iterator function.
    Dim iterateSequence = Iterator Function() As IEnumerable
                              For index = low To high
                                  Yield index
                              Next
                          End Function
    Return iterateSequence()
End Function
```

Wenn die Validierung stattdessen innerhalb der Iteratorfunktion erfolgt, kann die Überprüfung bis zum Anfang der ersten Iterationen des Texts nicht ausgeführt werden `For Each` .

## <a name="using-iterators-with-a-generic-list"></a><a name="BKMK_GenericList"></a> Verwenden von Iteratoren mit einer generischen Liste

In folgendem Beispiel implementiert die generische Klasse `Stack(Of T)` die generische Schnittstelle <xref:System.Collections.Generic.IEnumerable%601>. Die Methode `Push` weist Werte an Arrays des Typs `T` zu. Die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode gibt die Arraywerte mit der `Yield`-Anweisung zurück.

Zusätzlich zur generischen Methode <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> muss auch die nicht generische Methode <xref:System.Collections.IEnumerable.GetEnumerator%2A> implementiert werden. Dies liegt daran, dass <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Collections.IEnumerable> erbt. Die nicht generische Implementierung verzögert die generische Implementierung.

In diesem Beispiel werden benannte Iteratoren verwendet, um verschiedene Arten der Iteration in der selben Datenauflistung zu unterstützen. Diese benannten Iteratoren sind die Eigenschaften `TopToBottom` und `BottomToTop` und die Methode `TopN`.

Die `BottomToTop` Eigenschaften Deklaration enthält das- `Iterator` Schlüsselwort.

```vb
Sub Main()
    Dim theStack As New Stack(Of Integer)

    ' Add items to the stack.
    For number As Integer = 0 To 9
        theStack.Push(number)
    Next

    ' Retrieve items from the stack.
    ' For Each is allowed because theStack implements
    ' IEnumerable(Of Integer).
    For Each number As Integer In theStack
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    ' For Each is allowed, because theStack.TopToBottom
    ' returns IEnumerable(Of Integer).
    For Each number As Integer In theStack.TopToBottom
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3 2 1 0

    For Each number As Integer In theStack.BottomToTop
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 0 1 2 3 4 5 6 7 8 9

    For Each number As Integer In theStack.TopN(7)
        Console.Write("{0} ", number)
    Next
    Console.WriteLine()
    ' Output: 9 8 7 6 5 4 3

    Console.ReadKey()
End Sub

Public Class Stack(Of T)
    Implements IEnumerable(Of T)

    Private values As T() = New T(99) {}
    Private top As Integer = 0

    Public Sub Push(ByVal t As T)
        values(top) = t
        top = top + 1
    End Sub

    Public Function Pop() As T
        top = top - 1
        Return values(top)
    End Function

    ' This function implements the GetEnumerator method. It allows
    ' an instance of the class to be used in a For Each statement.
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _
        Implements IEnumerable(Of T).GetEnumerator

        For index As Integer = top - 1 To 0 Step -1
            Yield values(index)
        Next
    End Function

    Public Iterator Function GetEnumerator1() As IEnumerator _
        Implements IEnumerable.GetEnumerator

        Yield GetEnumerator()
    End Function

    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)
        Get
            Return Me
        End Get
    End Property

    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)
        Get
            For index As Integer = 0 To top - 1
                Yield values(index)
            Next
        End Get
    End Property

    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _
        As IEnumerable(Of T)

        ' Return less than itemsFromTop if necessary.
        Dim startIndex As Integer =
            If(itemsFromTop >= top, 0, top - itemsFromTop)

        For index As Integer = top - 1 To startIndex Step -1
            Yield values(index)
        Next
    End Function
End Class
```

## <a name="syntax-information"></a><a name="BKMK_SyntaxInformation"></a>Syntax Informationen

Ein Iterator kann als Methode oder als `get`-Zugriffsmethode vorkommen. Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.

Es muss eine implizite Konvertierung vom Typ des Ausdrucks in der `Yield`-Anweisung in den Rückgabetyp des Iterators vorhanden sein.

In Visual Basic kann eine Iteratormethode keine Parameter aufweisen `ByRef` .

In Visual Basic ist "yield" kein reserviertes Wort und hat nur dann eine besondere Bedeutung, wenn es in einer `Iterator` Methode oder einem `get` Accessor verwendet wird.

## <a name="technical-implementation"></a><a name="BKMK_Technical"></a>Technische Implementierung

Auch wenn Sie einen Iterator als Methode schreiben, führt der Compiler für diesen eine Translation in eine geschachtelte Klasse durch, die tatsächlich ein Zustandsautomat ist. Diese Klasse überwacht die Position des Iterators solange, wie die `For Each...Next`-Schleife im Clientcode weiter ausgeführt wird.

Um zu sehen, was der Compiler macht, können Sie das Tool Ildasm.exe verwenden, um den Intermediate Language-Code von Microsoft anzuzeigen, der für eine Iteratormethode generiert wird.

Wenn Sie einen Iterator für eine [Klasse](../../language-reference/statements/class-statement.md) oder [Struktur](../../language-reference/statements/structure-statement.md)erstellen, müssen Sie nicht die gesamte <xref:System.Collections.IEnumerator> Schnittstelle implementieren. Wenn der Compiler einer Iterator erkennt, generiert er automatisch die Methoden `Current`, `MoveNext` und `Dispose` der <xref:System.Collections.IEnumerator>- und <xref:System.Collections.Generic.IEnumerator%601>-Schnittstelle.

In jeder aufeinanderfolgenden Iteration der `For Each…Next`-Schleife (oder im direkten Aufruf von `IEnumerator.MoveNext`) setzt der nächste Iteratorcodetext den Prozess nach der letzten `Yield`-Anweisung fort. Anschließend wird die nächste Anweisung fortgesetzt `Yield` , bis das Ende des iteratortexts erreicht ist, oder bis eine- `Exit Function` oder-Anweisung gefunden `Return` wird.

Iteratoren unterstützen die- <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> Methode nicht. Um den Prozess erneut von Anfang an zu durchlaufen, müssen Sie einen neuen Iterator erstellen.

Weitere Informationen finden Sie in der [Visual Basic-Sprachspezifikation](../../reference/language-specification/index.md).

## <a name="use-of-iterators"></a><a name="BKMK_UseOfIterators"></a>Verwendung von Iteratoren

Mit Iteratoren können Sie die Einfachheit einer `For Each`-Schleife beibehalten, wenn Sie komplexen Code verwenden müssen, um eine Listensequenz aufzufüllen. Das kann für Folgende Aktionen nützlich sein:

- Das Modifizieren der Listensequenz nach der ersten Iteration einer `For Each`-Schleife.

- Das Vermeiden des kompletten Ladens einer großen Liste vor der ersten Iteration einer `For Each`-Schleife. Ein Beispiel dafür ist das ausgelagerte Abrufen, um einen Batch von Tabellenzeilen zu laden. Ein anderes Beispiel ist die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die Iteratoren im .NET Framework implementiert.

- Das Einschließen des Erstellens der Liste im Iterator. In der Iteratormethode können Sie die Liste erstellen und anschließend jedes Ergebnis in eine Schleife liefern.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [For Each...Next-Anweisung](../../language-reference/statements/for-each-next-statement.md)
- [Yield-Anweisung](../../language-reference/statements/yield-statement.md)
- [Iterator](../../language-reference/modifiers/iterator.md)
