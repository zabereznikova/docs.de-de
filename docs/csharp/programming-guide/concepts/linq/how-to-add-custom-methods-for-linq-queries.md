---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)'
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: e16175d3332b6ce36458eaa78af093e4f8772723
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141473"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="37822-102">Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="37822-102">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="37822-103">Sie können die Methoden erweitern, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="37822-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="37822-104">Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen, können Sie eine benutzerdefinierte Aggregatmethode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="37822-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="37822-105">Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="37822-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="37822-106">Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="37822-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="37822-107">Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden.</span><span class="sxs-lookup"><span data-stu-id="37822-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="37822-108">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="37822-108">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="37822-109">Hinzufügen einer Aggregatmethode</span><span class="sxs-lookup"><span data-stu-id="37822-109">Adding an Aggregate Method</span></span>

<span data-ttu-id="37822-110">Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten.</span><span class="sxs-lookup"><span data-stu-id="37822-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="37822-111">LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="37822-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="37822-112">Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37822-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="37822-113">Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="37822-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        if (source.Count() == 0)
        {
            throw new InvalidOperationException("Cannot compute median for an empty set.");
        }

        var sortedList = from number in source
                         orderby number
                         select number;

        int itemIndex = (int)sortedList.Count() / 2;

        if (sortedList.Count() % 2 == 0)
        {
            // Even number of items.
            return (sortedList.ElementAt(itemIndex) + sortedList.ElementAt(itemIndex - 1)) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList.ElementAt(itemIndex);
        }
    }
}
```

<span data-ttu-id="37822-114">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="37822-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="37822-115">Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="37822-115">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
*/
```

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="37822-116">Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen</span><span class="sxs-lookup"><span data-stu-id="37822-116">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="37822-117">Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="37822-117">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="37822-118">Die Standardmethode ist die Erstellung einer Überladung für jeden Typ.</span><span class="sxs-lookup"><span data-stu-id="37822-118">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="37822-119">Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="37822-119">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="37822-120">Sie können auch beide Methoden kombinieren.</span><span class="sxs-lookup"><span data-stu-id="37822-120">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="37822-121">So erstellen Sie eine Überladung für jeden Typ</span><span class="sxs-lookup"><span data-stu-id="37822-121">To create an overload for each type</span></span>

<span data-ttu-id="37822-122">Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="37822-122">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="37822-123">Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="37822-123">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

<span data-ttu-id="37822-124">Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="37822-124">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

```csharp
double[] numbers1 = { 1.9, 2, 8, 4, 5.7, 6, 7.2, 0 };

var query1 = numbers1.Median();

Console.WriteLine("double: Median = " + query1);
```

```csharp
int[] numbers2 = { 1, 2, 3, 4, 5 };

var query2 = numbers2.Median();

Console.WriteLine("int: Median = " + query2);
```

```csharp
/*
 This code produces the following output:

 Double: Median = 4.85
 Integer: Median = 3
*/
```

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="37822-125">So erstellen Sie eine generische Überladung</span><span class="sxs-lookup"><span data-stu-id="37822-125">To create a generic overload</span></span>

<span data-ttu-id="37822-126">Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="37822-126">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="37822-127">Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="37822-127">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="37822-128">Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="37822-128">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="37822-129">Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.</span><span class="sxs-lookup"><span data-stu-id="37822-129">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

<span data-ttu-id="37822-130">Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen.</span><span class="sxs-lookup"><span data-stu-id="37822-130">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="37822-131">Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="37822-131">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="37822-132">In C# können Sie zu diesem Zweck einen Lambdaausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="37822-132">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="37822-133">Wenn Sie die `Aggregate`- oder `Group By`-Klausel anstatt des Methodenaufrufs verwenden, können Sie auch einen beliebigen Wert oder Ausdruck übergeben, der im Bereich dieser Klausel vorhanden ist. Diese Methode ist nur in Visual Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="37822-133">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="37822-134">Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="37822-134">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="37822-135">Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet.</span><span class="sxs-lookup"><span data-stu-id="37822-135">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="37822-136">Das Beispiel zeigt, wie der Delegatparameter `Median` an die <xref:System.Func%602>-Methode für jeden Fall übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="37822-136">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

```csharp
int[] numbers3 = { 1, 2, 3, 4, 5 };

/*
  You can use the num=>num lambda expression as a parameter for the Median method
  so that the compiler will implicitly convert its value to double.
  If there is no implicit conversion, the compiler will display an error message.
*/

var query3 = numbers3.Median(num => num);

Console.WriteLine("int: Median = " + query3);

string[] numbers4 = { "one", "two", "three", "four", "five" };

// With the generic overload, you can also use numeric properties of objects.

var query4 = numbers4.Median(str => str.Length);

Console.WriteLine("String: Median = " + query4);

/*
 This code produces the following output:

 Integer: Median = 3
 String: Median = 4
*/
```

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="37822-137">Hinzufügen einer Methode, die eine Auflistung zurückgibt</span><span class="sxs-lookup"><span data-stu-id="37822-137">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="37822-138">Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="37822-138">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="37822-139">In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="37822-139">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="37822-140">Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="37822-140">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="37822-141">Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.</span><span class="sxs-lookup"><span data-stu-id="37822-141">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

```csharp
// Extension method for the IEnumerable<T> interface.
// The method returns every other element of a sequence.

public static IEnumerable<T> AlternateElements<T>(this IEnumerable<T> source)
{
    List<T> list = new List<T>();

    int i = 0;

    foreach (var element in source)
    {
        if (i % 2 == 0)
        {
            list.Add(element);
        }

        i++;
    }

    return list;
}
```

<span data-ttu-id="37822-142">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="37822-142">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

```csharp
string[] strings = { "a", "b", "c", "d", "e" };

var query = strings.AlternateElements();

foreach (var element in query)
{
    Console.WriteLine(element);
}
/*
 This code produces the following output:

 a
 c
 e
*/
```

## <a name="see-also"></a><span data-ttu-id="37822-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37822-143">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="37822-144">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="37822-144">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
