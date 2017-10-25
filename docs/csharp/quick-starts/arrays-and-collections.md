---
title: "Schnellstart – Sammlungen – C#-Handbuch"
description: Lernen Sie C#, indem Sie die Listensammlung in diesem Schnellstart erforschen.
keywords: C#, Erste Schritte, Tutorial, Sammlungen, Liste
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: 51b190fba32186cb4c52ccd773274d9ae22c8efb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="c-quick-start-collections"></a><span data-ttu-id="bb86d-104">C#-Schnellstart: Sammlungen</span><span class="sxs-lookup"><span data-stu-id="bb86d-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="bb86d-105">Dieses Tutorial bietet eine Einführung in die C#-Sprache und die Grundlagen der <xref:System.Collections.Generic.List%601>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="bb86d-105">This tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

## <a name="a-simple-list-example"></a><span data-ttu-id="bb86d-106">Ein Beispiel für eine einfache Liste.</span><span class="sxs-lookup"><span data-stu-id="bb86d-106">A simple list example.</span></span>

> [!NOTE]
> <span data-ttu-id="bb86d-107">Wenn Sie ausgehend von dem Code beginnen, den Sie in [dot.net](https://dot.net/) geschrieben haben, können Sie den bereits in diesem Abschnitt geschriebenen Code nutzen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-107">If you're starting from the code you wrote in [dot.net](https://dot.net/), you already have the code written in this section.</span></span> <span data-ttu-id="bb86d-108">Fahren Sie mit [Ändern von Listeninhalten](#modify-list-contents) fort.</span><span class="sxs-lookup"><span data-stu-id="bb86d-108">Jump to [Modify list contents](#modify-list-contents).</span></span>

<span data-ttu-id="bb86d-109">In dieser Lektion wird vorausgesetzt, dass Sie die Onlineschnellstarts abgeschlossen und [.NET Core SDK](http://dot.net/core) und [Visual Studio Code](https://code.visualstudio.com/) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="bb86d-109">This lesson assumes you've finished the online quick starts, and you've installed the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span> 

<span data-ttu-id="bb86d-110">Erstellen Sie ein Verzeichnis mit dem Namen **list-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="bb86d-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="bb86d-111">Machen Sie dieses Verzeichnis zum aktuellen Verzeichnis, und führen Sie `dotnet new console` aus.</span><span class="sxs-lookup"><span data-stu-id="bb86d-111">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="bb86d-112">Öffnen Sie **Program.cs** in Ihrem bevorzugten Editor, und ersetzen Sie den vorhandenen Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bb86d-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

<span data-ttu-id="bb86d-113">Ersetzen Sie `<name>` durch Ihren eigenen Namen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="bb86d-114">Speichern Sie **Program.cs**.</span><span class="sxs-lookup"><span data-stu-id="bb86d-114">Save **Program.cs**.</span></span> <span data-ttu-id="bb86d-115">Geben Sie `dotnet run` in Ihrem Konsolenfenster ein, um es zu testen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="bb86d-116">Sie haben gerade eine Liste von Zeichenfolgen erstellt, dieser Liste drei Namen hinzugefügt und die Namen in GROSSBUCHSTABEN ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="bb86d-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="bb86d-117">Sie verwenden Konzepte, die Sie in früheren Schnellstarts gelernt haben, um die Liste zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-117">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="bb86d-118">Der Code zum Anzeigen von Namen nutzt **interpolierte Zeichenfolgen**.</span><span class="sxs-lookup"><span data-stu-id="bb86d-118">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="bb86d-119">Wenn Sie einem `string` ein `$`-Zeichen voranstellen, können Sie C#-Code in die Zeichenfolgendeklaration einbetten.</span><span class="sxs-lookup"><span data-stu-id="bb86d-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="bb86d-120">Der Wert, den dieser C#-Code generiert, ist eine Zeichenfolge, durch die der C#-Code ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="bb86d-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="bb86d-121">In diesem Beispiel wird `{name.ToUpper()}` mit dem jeweiligen in Großbuchstaben konvertierten Namen ersetzt, da Sie die <xref:System.String.ToUpper%2A>-Methode aufgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="bb86d-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="bb86d-122">Setzen wir nun unsere Forschungen fort.</span><span class="sxs-lookup"><span data-stu-id="bb86d-122">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="bb86d-123">Ändern von Listeninhalten</span><span class="sxs-lookup"><span data-stu-id="bb86d-123">Modify list contents</span></span>

<span data-ttu-id="bb86d-124">Die Sammlung, die Sie erstellt haben, nutzt den <xref:System.Collections.Generic.List%601>-Typ.</span><span class="sxs-lookup"><span data-stu-id="bb86d-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="bb86d-125">Dieser Typ speichert Elementsequenzen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-125">This type stores sequences of elements.</span></span> <span data-ttu-id="bb86d-126">Sie geben den Typ der Elemente zwischen den spitzen Klammern an.</span><span class="sxs-lookup"><span data-stu-id="bb86d-126">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="bb86d-127">Ein wichtiger Aspekt dieses <xref:System.Collections.Generic.List%601>-Typs ist, dass er wachsen oder schrumpfen kann, sodass Sie Elemente hinzufügen oder entfernen können.</span><span class="sxs-lookup"><span data-stu-id="bb86d-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="bb86d-128">Fügen Sie diesen Code vor der abschließenden `}` in die `Main`-Methode ein:</span><span class="sxs-lookup"><span data-stu-id="bb86d-128">Add this code before the closing `}` in the `Main` method:</span></span>

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="bb86d-129">Sie haben am Ende der Liste zwei weitere Namen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb86d-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="bb86d-130">Sie haben auch einen entfernt.</span><span class="sxs-lookup"><span data-stu-id="bb86d-130">You've also removed one as well.</span></span> <span data-ttu-id="bb86d-131">Speichern Sie die Datei, und geben Sie `dotnet run` zum Testen ein.</span><span class="sxs-lookup"><span data-stu-id="bb86d-131">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="bb86d-132"><xref:System.Collections.Generic.List%601> ermöglicht Ihnen auch, mithilfe des **Indexes** auf einzelne Elemente zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="bb86d-133">Platzieren Sie den Index hinter dem Listennamen zwischen den Zeichen `[` und `]`.</span><span class="sxs-lookup"><span data-stu-id="bb86d-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="bb86d-134">C# verwendet 0 für den ersten Index.</span><span class="sxs-lookup"><span data-stu-id="bb86d-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="bb86d-135">Fügen Sie diesen Code direkt unterhalb des Codes hinzu, den Sie gerade hinzugefügt haben, und probieren Sie es aus:</span><span class="sxs-lookup"><span data-stu-id="bb86d-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="bb86d-136">Sie können nicht auf einen Index zugreifen, der hinter dem Ende der Liste liegt.</span><span class="sxs-lookup"><span data-stu-id="bb86d-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="bb86d-137">Denken Sie daran, dass die Indizes mit 0 (null) beginnen, sodass der größte gültige Index um eins kleiner ist als die Anzahl der Elemente in der Liste.</span><span class="sxs-lookup"><span data-stu-id="bb86d-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="bb86d-138">Sie können mit der <xref:System.Collections.Generic.List%601.Count%2A>-Eigenschaft überprüfen, wie lang die Liste ist.</span><span class="sxs-lookup"><span data-stu-id="bb86d-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="bb86d-139">Fügen Sie den folgenden Code am Ende der Main-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb86d-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="bb86d-140">Speichern Sie die Datei, und geben Sie `dotnet run` erneut ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-140">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="bb86d-141">Suchen in und Sortieren von Listen</span><span class="sxs-lookup"><span data-stu-id="bb86d-141">Search and sort lists</span></span>
<span data-ttu-id="bb86d-142">In unseren Beispielen werden relativ kleine Listen verwendet, aber Ihre Anwendungen erstellen möglicherweise häufig Listen mit viel mehr Elementen, die manchmal in die Tausende gehen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="bb86d-143">Um in diesen größeren Sammlungen Elemente zu finden, müssen Sie die Liste nach verschiedenen Elementen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="bb86d-144">Die <xref:System.Collections.Generic.List%601.IndexOf%2A>-Methode sucht nach einem Element und gibt den Index des Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="bb86d-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="bb86d-145">Fügen Sie diesen Code am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb86d-145">Add this code to the bottom of your `Main` method:</span></span>

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

<span data-ttu-id="bb86d-146">Die Elemente in der Liste können auch sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb86d-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="bb86d-147">Die <xref:System.Collections.Generic.List%601.Sort%2A>-Methode sortiert alle Elemente in der Liste in der normalen Reihenfolge (Zeichenfolgen alphabetisch).</span><span class="sxs-lookup"><span data-stu-id="bb86d-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="bb86d-148">Fügen Sie diesen Code am Ende der `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb86d-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="bb86d-149">Speichern Sie die Datei, und geben Sie `dotnet run` ein, um diese neueste Version zu testen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="bb86d-150">Bevor Sie mit dem nächsten Abschnitt beginnen, verschieben wir den aktuellen Code in eine separate Methode.</span><span class="sxs-lookup"><span data-stu-id="bb86d-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="bb86d-151">Dies erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bb86d-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="bb86d-152">Benennen Sie Ihre `Main` -Methode in `WorkingWithStrings` um, und schreiben Sie eine neue `Main`-Methode, die `WorkingWithStrings` aufruft.</span><span class="sxs-lookup"><span data-stu-id="bb86d-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="bb86d-153">Anschließend sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bb86d-153">When you have finished, your code should look like this:</span></span>

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a><span data-ttu-id="bb86d-154">Listen mit anderen Typen</span><span class="sxs-lookup"><span data-stu-id="bb86d-154">Lists of other types</span></span>

<span data-ttu-id="bb86d-155">Sie haben bisher den `string`-Typ in Listen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb86d-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="bb86d-156">Nun erstellen wir eine <xref:System.Collections.Generic.List%601> mithilfe eines anderen Typs.</span><span class="sxs-lookup"><span data-stu-id="bb86d-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="bb86d-157">Zunächst erstellen wir einen Satz von Zahlen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-157">Let's build a set of numbers.</span></span> 

<span data-ttu-id="bb86d-158">Fügen Sie Folgendes am Ende Ihrer neuen `Main`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb86d-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="bb86d-159">Damit wird eine Liste von Ganzzahlen erstellt und für die ersten beiden Ganzzahlen der Wert 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bb86d-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="bb86d-160">Dies sind die ersten beiden Werte einer *Fibonacci-Sequenz* – einer Sequenz von Zahlen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="bb86d-161">Jede nächste Fibonacci-Zahl wird ermittelt, indem die Summe der beiden vorherigen Zahlen gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="bb86d-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="bb86d-162">Fügen Sie diesen Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="bb86d-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="bb86d-163">Speichern Sie die Datei, und geben Sie `dotnet run` ein, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-163">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="bb86d-164">Um sich genau auf diesen Abschnitt zu konzentrieren, können Sie den Code auskommentieren, der `WorkingWithStrings();` aufruft.</span><span class="sxs-lookup"><span data-stu-id="bb86d-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="bb86d-165">Setzen Sie einfach zwei `/`-Zeichen wie folgt vor den Aufruf: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="bb86d-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="bb86d-166">Herausforderung</span><span class="sxs-lookup"><span data-stu-id="bb86d-166">Challenge</span></span>
<span data-ttu-id="bb86d-167">Versuchen Sie, einige dieser Lektionen und frühere Lektionen in einen Zusammenhang zu bringen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-167">See if you can put together some of the lessons from this and earlier lessons.</span></span> <span data-ttu-id="bb86d-168">Erweitern Sie das, was Sie bisher bezüglich Fibonacci-Zahlen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bb86d-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="bb86d-169">Versuchen Sie, den Code zum Generieren der ersten 20 Zahlen der Sequenz zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="bb86d-169">Try and write the code to generate the first 20 numbers in the sequence.</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="bb86d-170">Herausforderung erfüllen</span><span class="sxs-lookup"><span data-stu-id="bb86d-170">Complete challenge</span></span>

<span data-ttu-id="bb86d-171">Als Beispiel für eine Lösung finden Sie [fertig gestellten Code auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs).</span><span class="sxs-lookup"><span data-stu-id="bb86d-171">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)</span></span>

<span data-ttu-id="bb86d-172">Mit jeder Iteration der Schleife werden die letzten beiden Ganzzahlen in der Liste summiert, und dieser Wert wird der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bb86d-172">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="bb86d-173">Die Schleife wird wiederholt, bis der Liste 20 Elemente hinzugefügt worden sind.</span><span class="sxs-lookup"><span data-stu-id="bb86d-173">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="bb86d-174">Herzlichen Glückwunsch, Sie haben das Listentutorial abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-174">Congratulations, you've completed the list tutorial.</span></span>

<span data-ttu-id="bb86d-175">Weitere Informationen zum Arbeiten mit dem `List`-Typ finden Sie im [Leitfaden für .NET](../../standard/index.md) im Thema [Sammlungen](../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="bb86d-175">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="bb86d-176">Sie werden auch viele andere Sammlungstypen kennenlernen.</span><span class="sxs-lookup"><span data-stu-id="bb86d-176">You'll also learn about many other collection types.</span></span>
