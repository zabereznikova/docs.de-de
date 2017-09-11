---
title: Iteratoren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c38609878c10ff3234b5a33ec44d678d24c11d7f
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="iterators-visual-basic"></a><span data-ttu-id="d27ac-102">Iteratoren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d27ac-102">Iterators (Visual Basic)</span></span>
<span data-ttu-id="d27ac-103">Ein *Iterator* Sammlungen schrittweise, wie z. B. aufgelistet und arrays verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d27ac-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="d27ac-104">Ein Iterator-Methode oder `get` Accessor führt eine benutzerdefinierte Iteration durch eine Auflistung.</span><span class="sxs-lookup"><span data-stu-id="d27ac-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="d27ac-105">Eine Iterator-Methode verwendet die [ergeben](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="d27ac-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="d27ac-106">Wenn eine `Yield` -Anweisung erreicht ist, wird die aktuelle Position im Code gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d27ac-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="d27ac-107">Die Ausführung wird von diesem Speicherort das nächste Mal neu gestartet, wenn, das die Iteratorfunktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="d27ac-108">Sie erzeugen einen Iterator aus dem Clientcode, indem eine [für jeden... Nächste](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisung oder mithilfe einer LINQ-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="d27ac-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="d27ac-109">Im folgenden Beispiel wird die erste Iteration des der `For Each` Schleife wird die Ausführung fortsetzen der `SomeNumbers` Iterator-Methode, bis die erste `Yield` -Anweisung erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="d27ac-110">Diese Iteration gibt einen Wert von 3 zurück, und die aktuelle Position in der Iteratormethode beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="d27ac-111">Bei der nächsten Iteration der Schleife, in der Iteratormethode Ausführung fortgesetzt, wo er unterbrochen wurde, erneut angehalten werden, wenn er erreicht eine `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d27ac-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="d27ac-112">Diese Iteration gibt den Wert 5 zurück, und die aktuelle Position in der Iteratormethode ist erneut beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d27ac-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="d27ac-113">Die Schleife abgeschlossen wird, wenn das Ende der Iteratormethode erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="d27ac-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
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
  
 <span data-ttu-id="d27ac-114">Der Rückgabetyp einer Methode Iterator oder `get` Accessor kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="d27ac-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="d27ac-115">Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d27ac-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="d27ac-116">Eine Visual Basic-Iterator-Funktion oder `get` Accessor-Deklaration enthält ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="d27ac-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
 <span data-ttu-id="d27ac-117">Iteratoren wurden in Visual Basic in Visual Studio 2012 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d27ac-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="d27ac-118">**Inhalt**</span><span class="sxs-lookup"><span data-stu-id="d27ac-118">**In this topic**</span></span>  
  
-   [<span data-ttu-id="d27ac-119">Einfacher Iterator</span><span class="sxs-lookup"><span data-stu-id="d27ac-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="d27ac-120">Erstellen einer Auflistungsklasse</span><span class="sxs-lookup"><span data-stu-id="d27ac-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="d27ac-121">Try-Blöcke</span><span class="sxs-lookup"><span data-stu-id="d27ac-121">Try Blocks</span></span>](#BKMK_TryBlocks)  
  
-   [<span data-ttu-id="d27ac-122">Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="d27ac-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)  
  
-   [<span data-ttu-id="d27ac-123">Verwenden von Iteratoren mit einer generischen Liste</span><span class="sxs-lookup"><span data-stu-id="d27ac-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="d27ac-124">Informationen zur Syntax</span><span class="sxs-lookup"><span data-stu-id="d27ac-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="d27ac-125">Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="d27ac-125">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="d27ac-126">Verwendung von Iteratoren</span><span class="sxs-lookup"><span data-stu-id="d27ac-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="d27ac-127">Bei allen Beispielen in diesem Thema außer der einfachen Iterator Beispiel gehören [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisungen für die `System.Collections` und `System.Collections.Generic` Namespaces.</span><span class="sxs-lookup"><span data-stu-id="d27ac-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="d27ac-128"><a name="BKMK_SimpleIterator"></a>Einfacher Iterator</span><span class="sxs-lookup"><span data-stu-id="d27ac-128"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="d27ac-129">Im folgende Beispiel verfügt über ein einzelnes `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife.</span><span class="sxs-lookup"><span data-stu-id="d27ac-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="d27ac-130">In `Main`, jede Iteration der `For Each` Anweisungstext erstellt einen Aufruf an die Iteratorfunktion, der auf die nächste übergeht `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d27ac-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>  
  
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
  
##  <span data-ttu-id="d27ac-131"><a name="BKMK_CollectionClass"></a>Erstellen einer Auflistungsklasse</span><span class="sxs-lookup"><span data-stu-id="d27ac-131"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="d27ac-132">Im folgenden Beispiel die `DaysOfTheWeek` -Klasse implementiert die <xref:System.Collections.IEnumerable>Schnittstelle, erfordert eine <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="d27ac-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="d27ac-133">Der Compiler ruft implizit die `GetEnumerator` -Methode, die eine <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator> zurückgibt</span><span class="sxs-lookup"><span data-stu-id="d27ac-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="d27ac-134">Die `GetEnumerator` -Methode gibt jede Zeichenfolge eine gleichzeitig mit der `Yield` -Anweisung und eine `Iterator` -Modifizierer ist in der Funktionsdeklaration.</span><span class="sxs-lookup"><span data-stu-id="d27ac-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>  
  
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
  
 <span data-ttu-id="d27ac-135">Das folgende Beispiel erstellt eine `Zoo` -Klasse, die eine Auflistung von Elementen enthält.</span><span class="sxs-lookup"><span data-stu-id="d27ac-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="d27ac-136">Die `For Each` -Anweisung, um die Klasseninstanz verweist (`theZoo`) ruft implizit die `GetEnumerator` Methode.</span><span class="sxs-lookup"><span data-stu-id="d27ac-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="d27ac-137">Die `For Each` -Anweisungen, die auf die `Birds` und `Mammals` Eigenschaften verwenden die `AnimalsForType` mit dem Namen Iterator-Methode.</span><span class="sxs-lookup"><span data-stu-id="d27ac-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
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
  
##  <span data-ttu-id="d27ac-138"><a name="BKMK_TryBlocks"></a>Try-Blöcke</span><span class="sxs-lookup"><span data-stu-id="d27ac-138"><a name="BKMK_TryBlocks"></a> Try Blocks</span></span>  
 <span data-ttu-id="d27ac-139">Visual Basic ermöglicht eine `Yield` -Anweisung in der `Try` -Block eine [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d27ac-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="d27ac-140">Ein `Try` blockieren, die eine `Yield` -Anweisung kann verfügen `Catch` blockiert, und kann einen `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="d27ac-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="d27ac-141">Das folgende Beispiel schließt `Try`, `Catch`, und `Finally` eines Iterator-Funktion blockiert.</span><span class="sxs-lookup"><span data-stu-id="d27ac-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="d27ac-142">Die `Finally` Block in der Iteratorfunktion ausgeführt wird, bevor die `For Each` Iteration abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d27ac-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>  
  
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
  
 <span data-ttu-id="d27ac-143">Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="d27ac-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="d27ac-144">Wenn die `For Each` Text (anstelle der Iteratormethode) eine Ausnahme auslöst, ein `Catch` -Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="d27ac-145">Ein `Catch` Block innerhalb einer Iteratorfunktion nur Ausnahmen abzufangen, die innerhalb der Iteratorfunktion auftreten.</span><span class="sxs-lookup"><span data-stu-id="d27ac-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
##  <span data-ttu-id="d27ac-146"><a name="BKMK_AnonymousMethods"></a>Anonyme Methoden</span><span class="sxs-lookup"><span data-stu-id="d27ac-146"><a name="BKMK_AnonymousMethods"></a> Anonymous Methods</span></span>  
 <span data-ttu-id="d27ac-147">In Visual Basic kann eine anonyme Funktion ein Iteratorfunktion.</span><span class="sxs-lookup"><span data-stu-id="d27ac-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="d27ac-148">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="d27ac-148">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="d27ac-149">Das folgende Beispiel enthält eine nicht-Iterator-Methode, die die Argumente überprüft.</span><span class="sxs-lookup"><span data-stu-id="d27ac-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="d27ac-150">Die Methode gibt das Ergebnis eines anonymen Iterators, der die Elemente der Auflistung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="d27ac-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>  
  
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
  
 <span data-ttu-id="d27ac-151">Wenn Überprüfung stattdessen innerhalb der Iteratorfunktion ist, kann nicht die Überprüfung ausgeführt werden, bis zum Beginn der ersten Iteration der der `For Each` Text.</span><span class="sxs-lookup"><span data-stu-id="d27ac-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>  
  
##  <span data-ttu-id="d27ac-152"><a name="BKMK_GenericList"></a>Verwenden von Iteratoren mit einer generischen Liste</span><span class="sxs-lookup"><span data-stu-id="d27ac-152"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="d27ac-153">Im folgenden Beispiel die `Stack(Of T)` generische Klasse implementiert die <xref:System.Collections.Generic.IEnumerable%601>generische Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d27ac-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="d27ac-154">Die `Push` Methode weist Werte in ein Array vom Typ `T`.</span><span class="sxs-lookup"><span data-stu-id="d27ac-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="d27ac-155">Die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode gibt die Array von Werten mit der `Yield` Anweisung.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="d27ac-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>  
  
 <span data-ttu-id="d27ac-156">Zusätzlich zu den generischen <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode, die nicht generische <xref:System.Collections.IEnumerable.GetEnumerator%2A>Methode muss auch implementiert werden.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="d27ac-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="d27ac-157">Grund hierfür ist, <xref:System.Collections.Generic.IEnumerable%601>erbt von <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d27ac-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="d27ac-158">Die nicht generische Implementierung orientiert sich an die generische Implementierung.</span><span class="sxs-lookup"><span data-stu-id="d27ac-158">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="d27ac-159">Im Beispiel wird die benannte Iteratoren unterstützen verschiedene Methoden, die gleiche Sammlung von Daten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d27ac-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="d27ac-160">Diese Iteratoren benannten sind die `TopToBottom` und `BottomToTop` Eigenschaften, und die `TopN` Methode.</span><span class="sxs-lookup"><span data-stu-id="d27ac-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="d27ac-161">Die `BottomToTop` Eigenschaftendeklaration enthält die `Iterator` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="d27ac-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>  
  
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
  
##  <span data-ttu-id="d27ac-162"><a name="BKMK_SyntaxInformation"></a>Informationen zur Syntax</span><span class="sxs-lookup"><span data-stu-id="d27ac-162"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="d27ac-163">Ein Iterator kann als Methode auftreten oder `get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="d27ac-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="d27ac-164">Ein Iterator kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.</span><span class="sxs-lookup"><span data-stu-id="d27ac-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="d27ac-165">Eine implizite Konvertierung muss vorhanden sein, über den Typ des Ausdrucks in der `Yield` Anweisung in den Rückgabetyp des Iterators.</span><span class="sxs-lookup"><span data-stu-id="d27ac-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="d27ac-166">In Visual Basic eine Iteratormethode keine `ByRef` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d27ac-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="d27ac-167">In Visual Basic "Yield" ist ein reserviertes Wort und hat eine besondere Bedeutung nur bei Verwendung in einem `Iterator` Methode oder `get` Accessor.</span><span class="sxs-lookup"><span data-stu-id="d27ac-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>  
  
##  <span data-ttu-id="d27ac-168"><a name="BKMK_Technical"></a>Technische Implementierung</span><span class="sxs-lookup"><span data-stu-id="d27ac-168"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="d27ac-169">Obwohl einen Iterator als Methode geschrieben wird, übersetzt der Compiler es in einer geschachtelten Klasse, tatsächlich einen Zustandsautomaten.</span><span class="sxs-lookup"><span data-stu-id="d27ac-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="d27ac-170">Diese Klasse verfolgt des die Position des Iterators, wie lange der `For Each...Next` -Schleife im Clientcode fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="d27ac-171">Um zu sehen, was geschieht, können Sie das Tool Ildasm.exe verwenden, um die Microsoft intermediate Language-Code anzuzeigen, der für eine Iteratormethode generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d27ac-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="d27ac-172">Beim Erstellen eines Iterators für eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md), Sie müssen nicht die gesamte Implementierung <xref:System.Collections.IEnumerator>Schnittstelle.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="d27ac-172">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="d27ac-173">Wenn der Compiler den Iterator erkennt, generiert er automatisch die `Current`, `MoveNext`, und `Dispose` Methoden der <xref:System.Collections.IEnumerator>oder <xref:System.Collections.Generic.IEnumerator%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="d27ac-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="d27ac-174">Bei jedem Durchlauf von der `For Each…Next` Schleife (oder dem direkten Aufruf von `IEnumerator.MoveNext`), der nächste Iterator Codetext wird fortgesetzt, nach der vorherigen `Yield` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d27ac-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="d27ac-175">Es setzt zur nächsten `Yield` Anweisung, bis das Ende des Iterators erreicht ist, oder bis ein `Exit Function` oder `Return` -Anweisung auftritt.</span><span class="sxs-lookup"><span data-stu-id="d27ac-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>  
  
 <span data-ttu-id="d27ac-176">Iteratoren unterstützen nicht die <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>Methode.</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d27ac-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="d27ac-177">Zum erneuten durchlaufen ab dem Anfang müssen Sie einen neuen Iterator abrufen.</span><span class="sxs-lookup"><span data-stu-id="d27ac-177">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="d27ac-178">Weitere Informationen finden Sie unter der [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span><span class="sxs-lookup"><span data-stu-id="d27ac-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
##  <span data-ttu-id="d27ac-179"><a name="BKMK_UseOfIterators"></a>Verwendung von Iteratoren</span><span class="sxs-lookup"><span data-stu-id="d27ac-179"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="d27ac-180">Iteratoren ermöglichen es Ihnen, die Einfachheit der Verwaltung einer `For Each` auf, wenn Sie komplexen Code zum Auffüllen einer Liste Sequenz verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="d27ac-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="d27ac-181">Dies kann nützlich sein, wenn Sie Folgendes tun möchten:</span><span class="sxs-lookup"><span data-stu-id="d27ac-181">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="d27ac-182">Ändern der Reihenfolge nach dem ersten `For Each` Schleifeniteration.</span><span class="sxs-lookup"><span data-stu-id="d27ac-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>  
  
-   <span data-ttu-id="d27ac-183">Laden eine umfangreiche Liste vor der ersten Iteration der vollständig zu verhindern eine `For Each` Schleife.</span><span class="sxs-lookup"><span data-stu-id="d27ac-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="d27ac-184">Ein Beispiel ist die ausgelagerten Fetch einen Batch von Zeilen der Tabelle zu laden.</span><span class="sxs-lookup"><span data-stu-id="d27ac-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="d27ac-185">Ein weiteres Beispiel ist die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die Iteratoren in .NET Framework implementiert.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A></span><span class="sxs-lookup"><span data-stu-id="d27ac-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="d27ac-186">Erstellen der Liste im Iterator zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="d27ac-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="d27ac-187">In der Iteratormethode Sie erstellen die Liste und führt dann jedes Ergebnis in einer Schleife.</span><span class="sxs-lookup"><span data-stu-id="d27ac-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d27ac-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d27ac-188">See Also</span></span>  
 <span data-ttu-id="d27ac-189"><xref:System.Collections.Generic></xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="d27ac-189"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="d27ac-190"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d27ac-190"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="d27ac-191"> [Für jede... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d27ac-191"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="d27ac-192"> [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d27ac-192"> [Yield Statement](../../../visual-basic/language-reference/statements/yield-statement.md) </span></span>  
<span data-ttu-id="d27ac-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span><span class="sxs-lookup"><span data-stu-id="d27ac-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span></span>
