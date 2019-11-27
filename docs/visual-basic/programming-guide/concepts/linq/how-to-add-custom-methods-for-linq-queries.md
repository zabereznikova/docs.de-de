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
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="88686-102">Gewusst wie: Hinzufügen von benutzerdefinierten Methoden für LINQ-Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88686-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>

<span data-ttu-id="88686-103">Sie können die Methoden erweitern, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="88686-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="88686-104">Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen, können Sie eine benutzerdefinierte Aggregatmethode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="88686-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="88686-105">Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="88686-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="88686-106">Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="88686-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="88686-107">Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden.</span><span class="sxs-lookup"><span data-stu-id="88686-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="88686-108">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="88686-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="88686-109">Hinzufügen einer Aggregatmethode</span><span class="sxs-lookup"><span data-stu-id="88686-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="88686-110">Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten.</span><span class="sxs-lookup"><span data-stu-id="88686-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="88686-111">LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="88686-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="88686-112">Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="88686-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="88686-113">Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="88686-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

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

<span data-ttu-id="88686-114">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="88686-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

> [!NOTE]
> <span data-ttu-id="88686-115">In Visual Basic können Sie entweder einen Methoden aufrufoder eine Standard Abfrage Syntax für die `Aggregate`-oder `Group By`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="88686-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="88686-116">Weitere Informationen finden Sie unter [Aggregat Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="88686-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>

<span data-ttu-id="88686-117">Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="88686-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="88686-118">Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen</span><span class="sxs-lookup"><span data-stu-id="88686-118">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="88686-119">Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="88686-119">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="88686-120">Die Standardmethode ist die Erstellung einer Überladung für jeden Typ.</span><span class="sxs-lookup"><span data-stu-id="88686-120">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="88686-121">Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="88686-121">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="88686-122">Sie können auch beide Methoden kombinieren.</span><span class="sxs-lookup"><span data-stu-id="88686-122">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="88686-123">So erstellen Sie eine Überladung für jeden Typ</span><span class="sxs-lookup"><span data-stu-id="88686-123">To create an overload for each type</span></span>

<span data-ttu-id="88686-124">Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="88686-124">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="88686-125">Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="88686-125">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```vb
' Integer overload

<Extension()>
Function Median(ByVal source As IEnumerable(Of Integer)) As Double
    Return Aggregate num In source Select CDbl(num) Into med = Median()
End Function
```

<span data-ttu-id="88686-126">Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="88686-126">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

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

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="88686-127">So erstellen Sie eine generische Überladung</span><span class="sxs-lookup"><span data-stu-id="88686-127">To create a generic overload</span></span>

<span data-ttu-id="88686-128">Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="88686-128">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="88686-129">Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="88686-129">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="88686-130">Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="88686-130">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="88686-131">Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.</span><span class="sxs-lookup"><span data-stu-id="88686-131">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```vb
' Generic overload.

<Extension()>
Function Median(Of T)(ByVal source As IEnumerable(Of T),
                      ByVal selector As Func(Of T, Double)) As Double
    Return Aggregate num In source Select selector(num) Into med = Median()
End Function
```

<span data-ttu-id="88686-132">Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen.</span><span class="sxs-lookup"><span data-stu-id="88686-132">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="88686-133">Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="88686-133">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="88686-134">In Visual Basic können Sie einen Lambda Ausdruck zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="88686-134">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="88686-135">Wenn Sie die `Aggregate`-oder `Group By`-Klausel anstelle des-Methoden Aufrufes verwenden, können Sie auch einen beliebigen Wert oder Ausdruck übergeben, der im Gültigkeitsbereich dieser Klausel enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="88686-135">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="88686-136">Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="88686-136">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="88686-137">Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet.</span><span class="sxs-lookup"><span data-stu-id="88686-137">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="88686-138">Das Beispiel zeigt, wie der Delegatparameter <xref:System.Func%602> an die `Median`-Methode für jeden Fall übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="88686-138">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

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

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="88686-139">Hinzufügen einer Methode, die eine Auflistung zurückgibt</span><span class="sxs-lookup"><span data-stu-id="88686-139">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="88686-140">Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="88686-140">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="88686-141">In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="88686-141">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="88686-142">Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="88686-142">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="88686-143">Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.</span><span class="sxs-lookup"><span data-stu-id="88686-143">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

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

<span data-ttu-id="88686-144">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="88686-144">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="88686-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88686-145">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="88686-146">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="88686-146">Extension Methods</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
