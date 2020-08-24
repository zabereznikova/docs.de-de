---
title: Iterators
description: Erfahren Sie, wie integrierte C#-Iteratoren verwendet werden und wie Sie eigene benutzerdefinierte Iteratormethoden erstellen können.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 5cf36f45-f91a-4fca-a0b7-87f233e108e9
ms.openlocfilehash: ee72331cb85ba1a03d48e2f58526ad432c7fe6d4
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656097"
---
# <a name="iterators"></a><span data-ttu-id="299c0-103">Iterators</span><span class="sxs-lookup"><span data-stu-id="299c0-103">Iterators</span></span>

<span data-ttu-id="299c0-104">Bei fast jedem Programm, das Sie schreiben, muss eine Auflistung durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="299c0-104">Almost every program you write will have some need to iterate over a collection.</span></span> <span data-ttu-id="299c0-105">Sie schreiben Code, der jedes Element in einer Auflistung überprüft.</span><span class="sxs-lookup"><span data-stu-id="299c0-105">You'll write code that examines every item in a collection.</span></span>

<span data-ttu-id="299c0-106">Sie erstellen auch Iteratormethoden, die einen Iterator (ein Objekt, das Container und insbesondere Listen durchläuft) für die Elemente dieser Klasse erzeugen.</span><span class="sxs-lookup"><span data-stu-id="299c0-106">You'll also create iterator methods which are methods that produces an iterator (which is an object that traverses a container, particularly lists) for the elements of that class.</span></span> <span data-ttu-id="299c0-107">Diese können für Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="299c0-107">These can be used for:</span></span>

+ <span data-ttu-id="299c0-108">Ausführen einer Aktion für jedes Element in einer Auflistung</span><span class="sxs-lookup"><span data-stu-id="299c0-108">Performing an action on each item in a collection.</span></span>
+ <span data-ttu-id="299c0-109">Enumerieren einer benutzerdefinierten Auflistung</span><span class="sxs-lookup"><span data-stu-id="299c0-109">Enumerating a custom collection.</span></span>
+ <span data-ttu-id="299c0-110">Erweitern von [LINQ](linq/index.md) oder anderen Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="299c0-110">Extending [LINQ](linq/index.md) or other libraries.</span></span>
+ <span data-ttu-id="299c0-111">Erstellen einer Datenpipeline, in der Daten Iteratormethoden effizient durchlaufen</span><span class="sxs-lookup"><span data-stu-id="299c0-111">Creating a data pipeline where data flows efficiently through iterator methods.</span></span>

<span data-ttu-id="299c0-112">Die Programmiersprache C# bietet Funktionen für diese beiden Szenarien.</span><span class="sxs-lookup"><span data-stu-id="299c0-112">The C# language provides features for both these scenarios.</span></span> <span data-ttu-id="299c0-113">Dieser Artikel enthält eine Übersicht über diese Funktionen.</span><span class="sxs-lookup"><span data-stu-id="299c0-113">This article provides an overview of those features.</span></span>

<span data-ttu-id="299c0-114">Dieses Tutorial besteht aus vielen Schritten.</span><span class="sxs-lookup"><span data-stu-id="299c0-114">This tutorial has multiple steps.</span></span> <span data-ttu-id="299c0-115">Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="299c0-115">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="299c0-116">[Hier](https://github.com/dotnet/samples/blob/master/csharp/iterators) können Sie das vollständige Beispiel für dieses Thema anzeigen oder herunterladen.</span><span class="sxs-lookup"><span data-stu-id="299c0-116">You can also [view or download the completed sample](https://github.com/dotnet/samples/blob/master/csharp/iterators) for this topic.</span></span> <span data-ttu-id="299c0-117">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="299c0-117">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="iterating-with-foreach"></a><span data-ttu-id="299c0-118">Durchlaufen mit foreach</span><span class="sxs-lookup"><span data-stu-id="299c0-118">Iterating with foreach</span></span>

<span data-ttu-id="299c0-119">Das Enumerieren einer Auflistung ist einfach: Das `foreach`-Schlüsselwort enumeriert eine Auflistung und führt die eingebettete Anweisung einmal für jedes Element in der Auflistung aus:</span><span class="sxs-lookup"><span data-stu-id="299c0-119">Enumerating a collection is simple: The `foreach` keyword enumerates a collection, executing the embedded statement once for each element in the collection:</span></span>

```csharp
foreach (var item in collection)
{
   Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="299c0-120">Das ist auch schon alles.</span><span class="sxs-lookup"><span data-stu-id="299c0-120">That's all there is to it.</span></span> <span data-ttu-id="299c0-121">Für das Durchlaufen aller Inhalte einer Auflistung benötigen Sie nur die `foreach`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="299c0-121">To iterate over all the contents of a collection, the `foreach` statement is all you need.</span></span> <span data-ttu-id="299c0-122">Die `foreach`-Anweisung ist jedoch nicht magisch.</span><span class="sxs-lookup"><span data-stu-id="299c0-122">The `foreach` statement isn't magic, though.</span></span> <span data-ttu-id="299c0-123">Sie beruht auf zwei generischen Schnittstellen, die in der .NET Core-Bibliothek definiert sind, um den Code für das Durchlaufen einer Auflistung zu generieren: `IEnumerable<T>` und `IEnumerator<T>`.</span><span class="sxs-lookup"><span data-stu-id="299c0-123">It relies on two generic interfaces defined in the .NET core library in order to generate the code necessary to iterate a collection: `IEnumerable<T>` and `IEnumerator<T>`.</span></span> <span data-ttu-id="299c0-124">Dieser Mechanismus wird unten ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="299c0-124">This mechanism is explained in more detail below.</span></span>

<span data-ttu-id="299c0-125">Für diese beiden Schnittstellen gibt es auch nicht generische Entsprechungen: `IEnumerable` und `IEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="299c0-125">Both of these interfaces also have non-generic counterparts: `IEnumerable` and `IEnumerator`.</span></span> <span data-ttu-id="299c0-126">Die [generischen](programming-guide/generics/index.md) Versionen werden für modernen Code bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="299c0-126">The [generic](programming-guide/generics/index.md) versions are preferred for modern code.</span></span>

## <a name="enumeration-sources-with-iterator-methods"></a><span data-ttu-id="299c0-127">Enumerationsquellen mit Iteratormethoden</span><span class="sxs-lookup"><span data-stu-id="299c0-127">Enumeration sources with iterator methods</span></span>

<span data-ttu-id="299c0-128">Mit einer weiteren großartigen Funktion der Programmiersprache C# können Sie Methoden konstruieren, die eine Quelle für eine Enumeration erstellen.</span><span class="sxs-lookup"><span data-stu-id="299c0-128">Another great feature of the C# language enables you to build methods that create a source for an enumeration.</span></span> <span data-ttu-id="299c0-129">Diese werden als *Iteratormethoden* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="299c0-129">These are referred to as *iterator methods*.</span></span> <span data-ttu-id="299c0-130">Eine Iteratormethode definiert, wie die Objekte in einer Sequenz bei Anforderung generiert werden.</span><span class="sxs-lookup"><span data-stu-id="299c0-130">An iterator method defines how to generate the objects in a sequence when requested.</span></span> <span data-ttu-id="299c0-131">Sie verwenden die `yield return`-Kontextschlüsselwörter, um eine Iteratormethode zu definieren.</span><span class="sxs-lookup"><span data-stu-id="299c0-131">You use the `yield return` contextual keywords to define an iterator method.</span></span>

<span data-ttu-id="299c0-132">Sie könnten diese Methode schreiben, um die Sequenz von ganzen Zahlen von 0 bis 9 zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="299c0-132">You could write this method to produce the sequence of integers from 0 through 9:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    yield return 0;
    yield return 1;
    yield return 2;
    yield return 3;
    yield return 4;
    yield return 5;
    yield return 6;
    yield return 7;
    yield return 8;
    yield return 9;
}
```

<span data-ttu-id="299c0-133">Der obige Code zeigt verschiedene `yield return`-Anweisungen, die verdeutlichen, dass Sie mehrere diskrete `yield return`-Anweisungen in einer Iteratormethode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="299c0-133">The code above shows distinct `yield return` statements to highlight the fact that you can use multiple discrete `yield return` statements in an iterator method.</span></span>
<span data-ttu-id="299c0-134">Sie können (und werden auch oft) andere Sprachkonstrukte zur Vereinfachung des Codes einer Iteratormethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="299c0-134">You can (and often do) use other language constructs to simplify the code of an iterator method.</span></span> <span data-ttu-id="299c0-135">Die folgende Methodendefinition erzeugt genau dieselbe Sequenz von Zahlen:</span><span class="sxs-lookup"><span data-stu-id="299c0-135">The method definition below produces the exact same sequence of numbers:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;
}
```

<span data-ttu-id="299c0-136">Sie müssen sich nicht für eine davon entscheiden.</span><span class="sxs-lookup"><span data-stu-id="299c0-136">You don't have to decide one or the other.</span></span> <span data-ttu-id="299c0-137">Sie können so viele `yield return`-Anweisungen verwenden wie für Ihre Methode erforderlich:</span><span class="sxs-lookup"><span data-stu-id="299c0-137">You can have as many `yield return` statements as necessary to meet the needs of your method:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    index = 100;
    while (index < 110)
        yield return index++;
}
```

<span data-ttu-id="299c0-138">Das ist die grundlegende Syntax.</span><span class="sxs-lookup"><span data-stu-id="299c0-138">That's the basic syntax.</span></span> <span data-ttu-id="299c0-139">Betrachten wir einen realen Beispielfall, in dem Sie eine Iteratormethode schreiben würden.</span><span class="sxs-lookup"><span data-stu-id="299c0-139">Let's consider a real world example where you would write an iterator method.</span></span> <span data-ttu-id="299c0-140">Angenommen, Sie arbeiten an einem IoT-Projekt und die Gerätesensoren generieren einen sehr großen Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="299c0-140">Imagine you're on an IoT project and the device sensors generate a very large stream of data.</span></span> <span data-ttu-id="299c0-141">Um ein Gefühl für die Daten zu bekommen, können Sie eine Methode schreiben, die bei jedem n-ten Datenelement eine Stichprobe durchführt.</span><span class="sxs-lookup"><span data-stu-id="299c0-141">To get a feel for the data, you might write a method that samples every Nth data element.</span></span> <span data-ttu-id="299c0-142">Diese kleine Iteratormethode ist der Trick dabei:</span><span class="sxs-lookup"><span data-stu-id="299c0-142">This small iterator method does the trick:</span></span>

```csharp
public static IEnumerable<T> Sample(this IEnumerable<T> sourceSequence, int interval)
{
    int index = 0;
    foreach (T item in sourceSequence)
    {
        if (index++ % interval == 0)
            yield return item;
    }
}
```

<span data-ttu-id="299c0-143">Es gibt eine wichtige Einschränkung bei Iteratormethoden: Eine `return`-Anweisung und eine `yield return`-Anweisung können nicht in derselben Methode enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="299c0-143">There is one important restriction on iterator methods: you can't have both a `return` statement and a `yield return` statement in the same method.</span></span> <span data-ttu-id="299c0-144">Folgendes wird nicht kompiliert:</span><span class="sxs-lookup"><span data-stu-id="299c0-144">The following will not compile:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    // generates a compile time error:
    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    return items;
}
```

<span data-ttu-id="299c0-145">Diese Einschränkung ist normalerweise kein Problem.</span><span class="sxs-lookup"><span data-stu-id="299c0-145">This restriction normally isn't a problem.</span></span> <span data-ttu-id="299c0-146">Sie können in der Methode entweder durchgehend `yield return` verwenden oder die ursprüngliche Methode in mehrere Methoden aufteilen, von denen einige `return` und einige `yield return` verwenden.</span><span class="sxs-lookup"><span data-stu-id="299c0-146">You have a choice of either using `yield return` throughout the method, or separating the original method into multiple methods, some using `return`, and some using `yield return`.</span></span>

<span data-ttu-id="299c0-147">Sie können die letzte Methode leicht ändern und so `yield return` überall verwenden:</span><span class="sxs-lookup"><span data-stu-id="299c0-147">You can modify the last method slightly to use `yield return` everywhere:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitNumbers()
{
    int index = 0;
    while (index < 10)
        yield return index++;

    yield return 50;

    var items = new int[] {100, 101, 102, 103, 104, 105, 106, 107, 108, 109 };
    foreach (var item in items)
        yield return item;
}
```

<span data-ttu-id="299c0-148">Manchmal ist die beste Lösung, eine Iteratormethode in zwei verschiedene Methoden aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="299c0-148">Sometimes, the right answer is to split an iterator method into two different methods.</span></span> <span data-ttu-id="299c0-149">Die eine verwendet dann `return` und die zweite verwendet `yield return`.</span><span class="sxs-lookup"><span data-stu-id="299c0-149">One that uses `return`, and a second that uses `yield return`.</span></span> <span data-ttu-id="299c0-150">Betrachten Sie eine Situation, in der Sie eine leere Auflistung oder die ersten 5 ungeraden Zahlen basierend auf einem booleschen Argument zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="299c0-150">Consider a situation where you might want to return an empty collection, or the first 5 odd numbers, based on a boolean argument.</span></span> <span data-ttu-id="299c0-151">Sie können das mit diesen zwei Methoden schreiben:</span><span class="sxs-lookup"><span data-stu-id="299c0-151">You could write that as these two methods:</span></span>

```csharp
public IEnumerable<int> GetSingleDigitOddNumbers(bool getCollection)
{
    if (getCollection == false)
        return new int[0];
    else
        return IteratorMethod();
}

private IEnumerable<int> IteratorMethod()
{
    int index = 0;
    while (index < 10)
    {
        if (index % 2 == 1)
            yield return index;
        index++;
    }
}
```

<span data-ttu-id="299c0-152">Betrachten Sie die oben genannten Methoden.</span><span class="sxs-lookup"><span data-stu-id="299c0-152">Look at the methods above.</span></span> <span data-ttu-id="299c0-153">Die erste Methode verwendet die `return`-Standardanweisung, um entweder eine leere Auflistung oder den Iterator, der durch die zweite Methode erstellt wurde, zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="299c0-153">The first uses the standard `return` statement to return either an empty collection, or the iterator created by the second method.</span></span> <span data-ttu-id="299c0-154">Die zweite Methode verwendet die `yield return`-Anweisung, um die angeforderte Reihenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="299c0-154">The second method uses the `yield return` statement to create the requested sequence.</span></span>

## <a name="deeper-dive-into-foreach"></a><span data-ttu-id="299c0-155">Tieferer Einblick in `foreach`</span><span class="sxs-lookup"><span data-stu-id="299c0-155">Deeper Dive into `foreach`</span></span>

<span data-ttu-id="299c0-156">Die `foreach`-Anweisung wird in einen Standardausdruck erweitert, der die Schnittstellen `IEnumerable<T>` und `IEnumerator<T>` für das Durchlaufen aller Elemente einer Auflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="299c0-156">The `foreach` statement expands into a standard idiom that uses the `IEnumerable<T>` and `IEnumerator<T>` interfaces to iterate across all elements of a collection.</span></span> <span data-ttu-id="299c0-157">Außerdem werden Fehler minimiert, die Entwickler durch falsche Ressourcenverwaltung verursachen.</span><span class="sxs-lookup"><span data-stu-id="299c0-157">It also  minimizes errors developers make by not properly managing resources.</span></span>

<span data-ttu-id="299c0-158">Der Compiler übersetzt die im ersten Beispiel gezeigte `foreach`-Schleife in etwas wie dieses Konstrukt:</span><span class="sxs-lookup"><span data-stu-id="299c0-158">The compiler translates the `foreach` loop shown in the first example into something similar to this construct:</span></span>

```csharp
IEnumerator<int> enumerator = collection.GetEnumerator();
while (enumerator.MoveNext())
{
    var item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="299c0-159">Das obige Konstrukt stellt den Code dar, der durch den C#-Compiler ab Version 5 und höher generiert wird.</span><span class="sxs-lookup"><span data-stu-id="299c0-159">The construct above represents the code generated by the C# compiler as of version 5 and above.</span></span> <span data-ttu-id="299c0-160">Vor Version 5 hatte die `item`-Variable einen anderen Bereich:</span><span class="sxs-lookup"><span data-stu-id="299c0-160">Prior to version 5, the `item` variable had a different scope:</span></span>

```csharp
// C# versions 1 through 4:
IEnumerator<int> enumerator = collection.GetEnumerator();
int item = default(int);
while (enumerator.MoveNext())
{
    item = enumerator.Current;
    Console.WriteLine(item.ToString());
}
```

<span data-ttu-id="299c0-161">Dies wurde geändert, da das frühere Verhalten zu kleinen und schwierig zu diagnostizierenden Fehlern im Zusammenhang mit Lambdaausdrücken führen konnte.</span><span class="sxs-lookup"><span data-stu-id="299c0-161">This was changed because the earlier behavior could lead to subtle and hard to diagnose bugs involving lambda expressions.</span></span> <span data-ttu-id="299c0-162">Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambdaausdrücke](language-reference/operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="299c0-162">For more information about lambda expressions, see [Lambda expressions](language-reference/operators/lambda-expressions.md).</span></span>

<span data-ttu-id="299c0-163">Der genaue, vom Compiler generierte Code ist etwas komplizierter und behandelt Situationen, in denen das von `GetEnumerator()` zurückgegebene Objekt die `IDisposable`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="299c0-163">The exact code generated by the compiler is somewhat more complicated, and handles situations where the object returned by `GetEnumerator()` implements the `IDisposable` interface.</span></span> <span data-ttu-id="299c0-164">Der durch vollständige Erweiterung generierte Code sieht eher wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="299c0-164">The full expansion generates code more like this:</span></span>

```csharp
{
    var enumerator = collection.GetEnumerator();
    try
    {
        while (enumerator.MoveNext())
        {
            var item = enumerator.Current;
            Console.WriteLine(item.ToString());
        }
    } finally
    {
        // dispose of enumerator.
    }
}
```

<span data-ttu-id="299c0-165">Die Art und Weise, wie der Enumerator verworfen wird, hängt von den Merkmalen des Typs von `enumerator` ab.</span><span class="sxs-lookup"><span data-stu-id="299c0-165">The manner in which the enumerator is disposed of depends on the characteristics of the type of `enumerator`.</span></span> <span data-ttu-id="299c0-166">Im Allgemeinen wird die `finally`-Klausel wie folgt erweitert:</span><span class="sxs-lookup"><span data-stu-id="299c0-166">In the general case, the `finally` clause expands to:</span></span>

```csharp
finally
{
   (enumerator as IDisposable)?.Dispose();
}
```

<span data-ttu-id="299c0-167">Wenn es sich bei dem Typ von `enumerator` jedoch um einen versiegelten Typ handelt und es keine implizite Konvertierung vom Typ von `enumerator` zu `IDisposable` gibt, wird die `finally`-Klausel zu einem leeren Block erweitert:</span><span class="sxs-lookup"><span data-stu-id="299c0-167">However, if the type of `enumerator` is a sealed type and there is no implicit conversion from the type of `enumerator` to `IDisposable`, the `finally` clause expands to an empty block:</span></span>

```csharp
finally
{
}
```

<span data-ttu-id="299c0-168">Wenn es eine implizite Konvertierung vom Typ von `enumerator` zu `IDisposable` gibt und `enumerator` keine NULL-Werte zulässt, wird die `finally`-Klausel wie folgt erweitert:</span><span class="sxs-lookup"><span data-stu-id="299c0-168">If there is an implicit conversion from the type of `enumerator` to `IDisposable`, and `enumerator` is a non-nullable value type, the `finally` clause expands to:</span></span>

```csharp
finally
{
   ((IDisposable)enumerator).Dispose();
}
```

<span data-ttu-id="299c0-169">Glücklicherweise müssen Sie sich nicht alle diese Details merken.</span><span class="sxs-lookup"><span data-stu-id="299c0-169">Thankfully, you don't need to remember all these details.</span></span> <span data-ttu-id="299c0-170">Die `foreach`-Anweisung kümmert sich für Sie um alle diese Nuancen.</span><span class="sxs-lookup"><span data-stu-id="299c0-170">The `foreach` statement handles all those nuances for you.</span></span> <span data-ttu-id="299c0-171">Der Compiler generiert den korrekten Code für jedes dieser Konstrukte.</span><span class="sxs-lookup"><span data-stu-id="299c0-171">The compiler will generate the correct code for any of these constructs.</span></span>
