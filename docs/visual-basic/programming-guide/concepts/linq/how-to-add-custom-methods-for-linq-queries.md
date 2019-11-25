---
title: 'Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen'
ms.date: 07/20/2015
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 3004a9c9c7abeffd9993b848ad765e7ae2dc8876
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353370"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>How to: Add Custom Methods for LINQ Queries (Visual Basic)

Sie können die Methoden erweitern, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können. Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen, können Sie eine benutzerdefinierte Aggregatmethode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen. Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt. Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.

Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden. Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).

## <a name="adding-an-aggregate-method"></a>Hinzufügen einer Aggregatmethode

Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten. LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>. Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.

Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.

```vb
Imports System.Runtime.CompilerServices

Module LINQExtension

    ' Extension method for the IEnumerable(of T) interface.
    ' The method accepts only values of the Double type.
    <Extension()>
    Function Median(ByVal source As IEnumerable(Of Double)) As Double
        If source.Count = 0 Then
            Throw New InvalidOperationException("Cannot compute median for an empty set.")
        End If

        Dim sortedSource = From number In source
                           Order By number

        Dim itemIndex = sortedSource.Count \ 2

        If sortedSource.Count Mod 2 = 0 Then
            ' Even number of items in list.
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2
        Else
            ' Odd number of items in list.
            Return sortedSource(itemIndex)
        End If
    End Function
End Module
```

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.

> [!NOTE]
> In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause. For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).

Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen

Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert. Die Standardmethode ist die Erstellung einer Überladung für jeden Typ. Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert. Sie können auch beide Methoden kombinieren.

#### <a name="to-create-an-overload-for-each-type"></a>So erstellen Sie eine Überladung für jeden Typ

Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten. Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:

```vb
Dim numbers1() As Double = {1.9, 2, 8, 4, 5.7, 6, 7.2, 0}

Dim query1 = Aggregate num In numbers1 Into Median()

Console.WriteLine("Double: Median = " & query1)
```

```vb
Dim numbers2() As Integer = {1, 2, 3, 4, 5}

Dim query2 = Aggregate num In numbers2 Into Median()

Console.WriteLine("Integer: Median = " & query2)
```

```vb
' This code produces the following output:
'
' Double: Median = 4.85
' Integer: Median = 3
```

#### <a name="to-create-a-generic-overload"></a>So erstellen Sie eine generische Überladung

Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert. Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.

Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert. Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen. Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben. In Visual Basic, you can use a lambda expression for this purpose. Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.

Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird. Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet. Das Beispiel zeigt, wie der Delegatparameter `Median` an die <xref:System.Func%602>-Methode für jeden Fall übergeben wird.

```vb
Dim numbers3() As Integer = {1, 2, 3, 4, 5}

' You can use num as a parameter for the Median method
' so that the compiler will implicitly convert its value to double.
' If there is no implicit conversion, the compiler will
' display an error message.

Dim query3 = Aggregate num In numbers3 Into Median(num)

Console.WriteLine("Integer: Median = " & query3)

Dim numbers4() As String = {"one", "two", "three", "four", "five"}

' With the generic overload, you can also use numeric properties of objects.

Dim query4 = Aggregate str In numbers4 Into Median(str.Length)

Console.WriteLine("String: Median = " & query4)

' This code produces the following output:
'
' Integer: Median = 3
' String: Median = 4
```

## <a name="adding-a-method-that-returns-a-collection"></a>Hinzufügen einer Methode, die eine Auflistung zurückgibt

Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt. In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben. Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.

Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.

```vb
' Extension method for the IEnumerable(of T) interface.
' The method returns every other element of a sequence.

<Extension()>
Function AlternateElements(Of T)(
    ByVal source As IEnumerable(Of T)
    ) As IEnumerable(Of T)

    Dim list As New List(Of T)
    Dim i = 0
    For Each element In source
        If (i Mod 2 = 0) Then
            list.Add(element)
        End If
        i = i + 1
    Next
    Return list
End Function
```

Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:

```vb
Dim strings() As String = {"a", "b", "c", "d", "e"}

Dim query = strings.AlternateElements()

For Each element In query
    Console.WriteLine(element)
Next

' This code produces the following output:
'
' a
' c
' e
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.IEnumerable%601>
- [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
