---
title: "Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="0aaa2-102">Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aaa2-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>
<span data-ttu-id="0aaa2-103">Sie können den Satz von Methoden, mit denen Sie für die LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zum Erweitern der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="0aaa2-104">Zusätzlich zu den standardmäßigen Mittel- oder Höchstwerte, können Sie z. B. eine benutzerdefinierte aggregate-Methode, um einen einzelnen Wert aus einer Sequenz von Werten berechnen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="0aaa2-105">Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten und eine neue Sequenz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="0aaa2-106">Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, und <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="0aaa2-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="0aaa2-107">Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="0aaa2-108">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0aaa2-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="0aaa2-109">Hinzufügen einer Aggregate-Methode</span><span class="sxs-lookup"><span data-stu-id="0aaa2-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="0aaa2-110">Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="0aaa2-111">LINQ stellt mehrere Aggregatmethoden, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, und <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="0aaa2-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="0aaa2-112">Sie können eigene aggregate-Methode erstellen, indem Sie eine Erweiterungsmethode zum Hinzufügen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="0aaa2-113">Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens erstellen `Median` berechnet ein Wendepunkt für eine Sequenz von Zahlen vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
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
  
 <span data-ttu-id="0aaa2-114">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung aufrufen, auf die gleiche Weise, die Sie andere aggregate Methoden aus Aufrufen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0aaa2-115">In Visual Basic können Sie entweder einen Methodenaufruf oder die Standardabfragesyntax für verwenden die `Aggregate` oder `Group By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="0aaa2-116">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0aaa2-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="0aaa2-117">Im folgenden Codebeispiel wird veranschaulicht, wie Sie die `Median` Methode für ein Array vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
<span data-ttu-id="0aaa2-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="0aaa2-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="0aaa2-120">Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen</span><span class="sxs-lookup"><span data-stu-id="0aaa2-120">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="0aaa2-121">Aggregate-Methode können überladen werden, sodass diese Sequenzen verschiedener Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-121">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="0aaa2-122">Die Standardmethode ist eine Überladung für jeden Typ erstellen.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-122">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="0aaa2-123">Ein anderer Ansatz ist das Erstellen eine Überladung, die einen generischen Typ annimmt und mit einem Delegaten in einen bestimmten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-123">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="0aaa2-124">Sie können auch beide Methoden kombinieren.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-124">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="0aaa2-125">So erstellen Sie eine Überladung für jeden Typ</span><span class="sxs-lookup"><span data-stu-id="0aaa2-125">To create an overload for each type</span></span>  
 <span data-ttu-id="0aaa2-126">Sie können eine bestimmte Überladung für jeden Typ erstellen, die Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-126">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="0aaa2-127">Das folgende Codebeispiel zeigt eine Überladung von der `Median` Methode für die `integer` Typ.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-127">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
<span data-ttu-id="0aaa2-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="0aaa2-129">Sie können nun Aufrufe der `Median` Überladungen für beide `integer` und `double` Typen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="0aaa2-129">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
<span data-ttu-id="0aaa2-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="0aaa2-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="0aaa2-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="0aaa2-133">So erstellen Sie eine generische Überladung</span><span class="sxs-lookup"><span data-stu-id="0aaa2-133">To create a generic overload</span></span>  
 <span data-ttu-id="0aaa2-134">Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-134">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="0aaa2-135">Diese Überladung nimmt einen Delegaten als Parameter und verwendet, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-135">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="0aaa2-136">Der folgende Code zeigt eine Überladung von der `Median` Methode, die die <xref:System.Func%602>-Delegaten als Parameter.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="0aaa2-136">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="0aaa2-137">Dieser Delegat nimmt ein Objekt des generischen Typs T und gibt ein Objekt vom Typ `double`.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-137">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 <span data-ttu-id="0aaa2-138">Sie können jetzt Aufrufen der `Median` -Methode für eine Sequenz von Objekten eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-138">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="0aaa2-139">Wenn der Typ keinen eigenen Überladung, müssen Sie einen Delegatparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-139">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="0aaa2-140">In Visual Basic können Sie zu diesem Zweck einen Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-140">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="0aaa2-141">Auch bei Verwendung der `Aggregate` oder `Group By` -Klausel anstelle der Methodenaufruf, können Sie jeder Wert oder Ausdruck, der im Gültigkeitsbereich dieser Klausel übergeben.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-141">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="0aaa2-142">Im folgenden Beispielcode veranschaulicht das Aufrufen der `Median` -Methode für ein Array von ganzen Zahlen und ein Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-142">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="0aaa2-143">Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-143">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="0aaa2-144">Das Beispiel zeigt, wie übergeben der <xref:System.Func%602>Delegieren Parameter, um die `Median` Methode für jeden Fall.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="0aaa2-144">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
<span data-ttu-id="0aaa2-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="0aaa2-146">Hinzufügen einer Methode, die eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-146">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="0aaa2-147">Sie können erweitern die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle mit einer benutzerdefinierten Abfrage-Methode, die eine Sequenz von Werten zurückgibt.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-147">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="0aaa2-148">In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> zurückgeben</span><span class="sxs-lookup"><span data-stu-id="0aaa2-148">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="0aaa2-149">Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-149">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="0aaa2-150">Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen erstellt `AlternateElements` jedes andere Element in einer Auflistung, beginnend mit dem ersten Element zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0aaa2-150">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
<span data-ttu-id="0aaa2-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="0aaa2-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="0aaa2-152">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung aufrufen, wie Sie auch andere Methoden Aufrufen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle, wie im folgenden Code gezeigt:</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-152">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0aaa2-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aaa2-153">See Also</span></span>  
 <span data-ttu-id="0aaa2-154"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="0aaa2-154"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="0aaa2-155"> [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="0aaa2-155"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
