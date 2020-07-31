---
title: 'Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)'
description: Hier erfahren Sie mehr über die Erweiterung der Methoden, die Sie durch Hinzufügen von Erweiterungsmethoden zur IEnumerable<T>-Schnittstelle in C# verwenden können.
ms.date: 07/20/2015
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: fac0eb4e14eb3bb36313232a7d7fa3060c0ac171
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103597"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="69399-103">Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="69399-103">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="69399-104">Sie können die Methoden erweitern, die Sie für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="69399-104">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="69399-105">Zusätzlich zu den durchschnittlichen oder maximalen Standardvorgängen, können Sie eine benutzerdefinierte Aggregatmethode erstellen, um einen einzelnen Wert aus einer Sequenz von Werten zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="69399-105">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="69399-106">Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten agiert und eine neue Sequenz zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="69399-106">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="69399-107">Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Reverse%2A>.</span><span class="sxs-lookup"><span data-stu-id="69399-107">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="69399-108">Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden.</span><span class="sxs-lookup"><span data-stu-id="69399-108">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="69399-109">Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="69399-109">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="69399-110">Hinzufügen einer Aggregatmethode</span><span class="sxs-lookup"><span data-stu-id="69399-110">Adding an Aggregate Method</span></span>

<span data-ttu-id="69399-111">Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten.</span><span class="sxs-lookup"><span data-stu-id="69399-111">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="69399-112">LINQ stellt mehrere Aggregatmethoden bereit, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> und <xref:System.Linq.Enumerable.Max%2A>.</span><span class="sxs-lookup"><span data-stu-id="69399-112">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="69399-113">Sie können Ihre eigene Aggregatmethode erstellen, indem Sie der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle eine Erweiterungsmethode hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="69399-113">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="69399-114">Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens `Median` erstellt wird, um einen Median für eine Zahlensequenz des Typs `double` zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="69399-114">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

```csharp
public static class LINQExtension
{
    public static double Median(this IEnumerable<double> source)
    {
        var countOfElementsInTheSet = source?.Count() ?? 0;

        if (countOfElementsInTheSet == 0)
        {
            throw new InvalidOperationException("Cannot compute median for a null or empty set.");
        }

        var sortedList = (from number in source
                         orderby number
                         select number).ToList();

        int itemIndex = countOfElementsInTheSet / 2;

        if (countOfElementsInTheSet % 2 == 0)
        {
            // Even number of items.
            return (sortedList[itemIndex] + sortedList[itemIndex - 1]) / 2;
        }
        else
        {
            // Odd number of items.
            return sortedList[itemIndex];
        }
    }
}
```

<span data-ttu-id="69399-115">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Aggregatmethoden aus der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="69399-115">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="69399-116">Im folgenden Codebeispiel wird die Verwendung der `Median`-Methode für ein Array des Typs `double` veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="69399-116">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

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

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="69399-117">Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen</span><span class="sxs-lookup"><span data-stu-id="69399-117">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="69399-118">Sie können die Aggregatmethode überladen, sodass diese Sequenzen verschiedener Typen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="69399-118">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="69399-119">Die Standardmethode ist die Erstellung einer Überladung für jeden Typ.</span><span class="sxs-lookup"><span data-stu-id="69399-119">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="69399-120">Ein anderer Ansatz ist das Erstellen einer Überladung, die einen generischen Typ annimmt und diesen mit einem Delegaten in einen bestimmten Typ konvertiert.</span><span class="sxs-lookup"><span data-stu-id="69399-120">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="69399-121">Sie können auch beide Methoden kombinieren.</span><span class="sxs-lookup"><span data-stu-id="69399-121">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="69399-122">So erstellen Sie eine Überladung für jeden Typ</span><span class="sxs-lookup"><span data-stu-id="69399-122">To create an overload for each type</span></span>

<span data-ttu-id="69399-123">Sie können eine bestimmte Überladung für jeden Typ erstellen, den Sie unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="69399-123">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="69399-124">Im folgenden Codebeispiel wird eine Überladung der `Median`-Methode für den `integer`-Typ veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="69399-124">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

```csharp
//int overload

public static double Median(this IEnumerable<int> source)
{
    return (from num in source select (double)num).Median();
}
```

<span data-ttu-id="69399-125">Sie können nun die `Median`-Überladungen für die `integer`- und `double`-Typen aufrufen, so wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="69399-125">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

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

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="69399-126">So erstellen Sie eine generische Überladung</span><span class="sxs-lookup"><span data-stu-id="69399-126">To create a generic overload</span></span>

<span data-ttu-id="69399-127">Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="69399-127">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="69399-128">Diese Überladung nimmt einen Delegaten als Parameter und verwendet ihn, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="69399-128">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="69399-129">Der folgende Code zeigt eine Überladung der `Median`-Methode, die den <xref:System.Func%602>-Delegaten als Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="69399-129">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="69399-130">Dieser Delegat übernimmt ein Objekt des generischen Typs „T“ und gibt ein Objekt vom Typ `double` zurück.</span><span class="sxs-lookup"><span data-stu-id="69399-130">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

```csharp
// Generic overload.

public static double Median<T>(this IEnumerable<T> numbers,
                       Func<T, double> selector)
{
    return (from num in numbers select selector(num)).Median();
}
```

<span data-ttu-id="69399-131">Sie können nun die `Median`-Methode für eine Sequenz von Objekten beliebigen Typs aufrufen.</span><span class="sxs-lookup"><span data-stu-id="69399-131">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="69399-132">Wenn der Typ nicht über eine eigene Methodenüberladung verfügt, müssen sie einen Delegatenparameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="69399-132">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="69399-133">In C# können Sie zu diesem Zweck einen Lambdaausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="69399-133">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="69399-134">Wenn Sie die `Aggregate`- oder `Group By`-Klausel anstatt des Methodenaufrufs verwenden, können Sie auch einen beliebigen Wert oder Ausdruck übergeben, der im Bereich dieser Klausel vorhanden ist. Diese Methode ist nur in Visual Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69399-134">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="69399-135">Der folgende Beispielcode veranschaulicht, wie eine `Median`-Methode für ein Array aus ganzen Zahlen und ein Array aus Zeichenfolgen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="69399-135">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="69399-136">Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet.</span><span class="sxs-lookup"><span data-stu-id="69399-136">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="69399-137">Das Beispiel zeigt, wie der Delegatparameter `Median` an die <xref:System.Func%602>-Methode für jeden Fall übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="69399-137">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

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

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="69399-138">Hinzufügen einer Methode, die eine Auflistung zurückgibt</span><span class="sxs-lookup"><span data-stu-id="69399-138">Adding a Method That Returns a Collection</span></span>

<span data-ttu-id="69399-139">Sie können die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> mit einer benutzerdefinierten Abfragemethode erweitern, die eine Sequenz von Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="69399-139">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="69399-140">In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601> zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="69399-140">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="69399-141">Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="69399-141">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="69399-142">Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen `AlternateElements` erstellt wird, die jedes andere Element in einer Auflistung zurückgibt, beginnend mit dem ersten Element.</span><span class="sxs-lookup"><span data-stu-id="69399-142">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

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

<span data-ttu-id="69399-143">Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung genau so aufrufen, wie Sie andere Methoden aus der Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> aufrufen, so wie im folgenden Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="69399-143">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="69399-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69399-144">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="69399-145">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="69399-145">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
