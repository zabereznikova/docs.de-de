---
title: 'Schnellstart - Sammlungen: C#-Handbuch'
description: Erlernen von c# durch Untersuchen der listenauflistung in diesem Schnellstart.
keywords: C#-, erste Schritte, Tutorial, Auflistungen, Liste
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
# <a name="c-quick-start-collections"></a><span data-ttu-id="f493a-104">C#-Schnellstart: Sammlungen</span><span class="sxs-lookup"><span data-stu-id="f493a-104">C# Quick start: Collections</span></span> #

<span data-ttu-id="f493a-105">Dieses Lernprogramm bietet eine Einführung in die C#-Sprache und die Grundlagen der <xref:System.Collections.Generic.List%601> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f493a-105">This tutorial provides an introduction to the C# language and the basics of the <xref:System.Collections.Generic.List%601> class.</span></span>

## <a name="a-simple-list-example"></a><span data-ttu-id="f493a-106">Ein Beispiel für eine einfache Liste.</span><span class="sxs-lookup"><span data-stu-id="f493a-106">A simple list example.</span></span>

> [!NOTE]
> <span data-ttu-id="f493a-107">Wenn Sie aus dem Code starten schrieb [dot.net](https://dot.net/), Sie haben bereits den Code in diesem Abschnitt geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f493a-107">If you're starting from the code you wrote in [dot.net](https://dot.net/), you already have the code written in this section.</span></span> <span data-ttu-id="f493a-108">Springen zu [ändern Listeninhalte](#modify-list-contents).</span><span class="sxs-lookup"><span data-stu-id="f493a-108">Jump to [Modify list contents](#modify-list-contents).</span></span>

<span data-ttu-id="f493a-109">In dieser Lektion wird davon ausgegangen, die online-Schnellstarts ist abgeschlossen, und installiert haben die [.NET Core SDK](http://dot.net/core) und [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="f493a-109">This lesson assumes you've finished the online quick starts, and you've installed the [.NET Core SDK](http://dot.net/core) and [Visual Studio Code](https://code.visualstudio.com/).</span></span> 

<span data-ttu-id="f493a-110">Erstellen Sie ein Verzeichnis mit dem Namen **Liste Schnellstart**.</span><span class="sxs-lookup"><span data-stu-id="f493a-110">Create a directory named **list-quickstart**.</span></span> <span data-ttu-id="f493a-111">Stellen, dass das aktuelle Verzeichnis, und führen `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="f493a-111">Make that the current directory and run `dotnet new console`.</span></span>

<span data-ttu-id="f493a-112">Open **"Program.cs"** in Ihrem bevorzugten Editor, und Ersetzen Sie den vorhandenen Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f493a-112">Open **Program.cs** in your favorite editor, and replace the existing code with the following:</span></span>

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

<span data-ttu-id="f493a-113">Ersetzen Sie `<name>` durch den Namen Ihres.</span><span class="sxs-lookup"><span data-stu-id="f493a-113">Replace `<name>` with your name.</span></span> <span data-ttu-id="f493a-114">Speichern Sie **"Program.cs"**.</span><span class="sxs-lookup"><span data-stu-id="f493a-114">Save **Program.cs**.</span></span> <span data-ttu-id="f493a-115">Typ `dotnet run` in Ihrem Konsolenfenster ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="f493a-115">Type `dotnet run` in your console window to try it.</span></span>

<span data-ttu-id="f493a-116">Sie haben gerade erstellte eine Liste von Zeichenfolgen, drei Namen dieser Liste hinzugefügt, und die Namen in Großbuchstaben ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f493a-116">You've just created a list of strings, added three names to that list, and printed out the names in all CAPS.</span></span> <span data-ttu-id="f493a-117">Sie verwenden Konzepte, die Sie haben gelernt in zuvor Schnellstarts so durchlaufen Sie die Liste.</span><span class="sxs-lookup"><span data-stu-id="f493a-117">You're using concepts that you've learned in earlier quick starts to loop through the list.</span></span>

<span data-ttu-id="f493a-118">Der Code zum Anzeigen der Namen nutzt **interpoliert Zeichenfolgen**.</span><span class="sxs-lookup"><span data-stu-id="f493a-118">The code to display names makes use of **interpolated strings**.</span></span>  <span data-ttu-id="f493a-119">Wenn Sie voranstellen eine `string` mit der `$` Zeichen ist, können Sie C#-Code in der Deklaration Zeichenfolge einbetten.</span><span class="sxs-lookup"><span data-stu-id="f493a-119">When you precede a `string` with the `$` character, you can embed C# code in the string declaration.</span></span> <span data-ttu-id="f493a-120">Die tatsächliche Zeichenfolge ersetzt dieses C#-Code mit dem Wert, den er generiert wird.</span><span class="sxs-lookup"><span data-stu-id="f493a-120">The actual string replaces that C# code with the value it generates.</span></span> <span data-ttu-id="f493a-121">In diesem Beispiel ersetzt die `{name.ToUpper()}` jeder Name konvertiert, Großbuchstaben, da Sie wird aufgerufen, die <xref:System.String.ToUpper%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="f493a-121">In this example, it replaces the `{name.ToUpper()}` with each name, converted to capital letters, because you called the <xref:System.String.ToUpper%2A> method.</span></span>

<span data-ttu-id="f493a-122">Wir untersuchen zu halten.</span><span class="sxs-lookup"><span data-stu-id="f493a-122">Let's keep exploring.</span></span>
    
## <a name="modify-list-contents"></a><span data-ttu-id="f493a-123">Ändern der Ordnerinhalt auflisten</span><span class="sxs-lookup"><span data-stu-id="f493a-123">Modify list contents</span></span>

<span data-ttu-id="f493a-124">Die Auflistung, die Sie erstellt mithilfe der <xref:System.Collections.Generic.List%601> Typ.</span><span class="sxs-lookup"><span data-stu-id="f493a-124">The collection you created uses the <xref:System.Collections.Generic.List%601> type.</span></span> <span data-ttu-id="f493a-125">Dieser Typ speichert Elementsequenzen.</span><span class="sxs-lookup"><span data-stu-id="f493a-125">This type stores sequences of elements.</span></span> <span data-ttu-id="f493a-126">Sie geben den Typ der Elemente zwischen den spitzen Klammern.</span><span class="sxs-lookup"><span data-stu-id="f493a-126">You specify the type of the elements between the angle brackets.</span></span>
    
<span data-ttu-id="f493a-127">Ein wichtiger Aspekt dieses <xref:System.Collections.Generic.List%601> Typ ist, dass es vergrößert oder verkleinert werden, können Sie zum Hinzufügen oder Entfernen von Elementen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f493a-127">One important aspect of this <xref:System.Collections.Generic.List%601> type is that it can grow or shrink, enabling you to add or remove elements.</span></span> <span data-ttu-id="f493a-128">Fügen Sie diesen Code vor dem abschließenden `}` in die `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="f493a-128">Add this code before the closing `}` in the `Main` method:</span></span>

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

<span data-ttu-id="f493a-129">Sie haben zwei weitere Namen bis zum Ende der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f493a-129">You've added two more names to the end of the list.</span></span> <span data-ttu-id="f493a-130">Sie haben eine auch ebenfalls entfernt.</span><span class="sxs-lookup"><span data-stu-id="f493a-130">You've also removed one as well.</span></span> <span data-ttu-id="f493a-131">Speichern der Datei, und geben `dotnet run` ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="f493a-131">Save the file, and type `dotnet run` to try it.</span></span>
    
<span data-ttu-id="f493a-132">Die <xref:System.Collections.Generic.List%601> ermöglicht es Ihnen, einzelne Elemente von verweisen **Index** ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="f493a-132">The <xref:System.Collections.Generic.List%601> enables you to reference individual items by **index** as well.</span></span> <span data-ttu-id="f493a-133">Platzieren Sie den Index zwischen `[` und `]` Token, die nach dem Listennamen.</span><span class="sxs-lookup"><span data-stu-id="f493a-133">You place the index between `[` and `]` tokens following the list name.</span></span> <span data-ttu-id="f493a-134">C# für den ersten Index wird 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="f493a-134">C# uses 0 for the first index.</span></span> <span data-ttu-id="f493a-135">Fügen Sie diesen Code direkt unterhalb der Code, den Sie gerade hinzugefügt haben, und versuchen Sie es:</span><span class="sxs-lookup"><span data-stu-id="f493a-135">Add this code directly below the code you just added and try it:</span></span>

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

<span data-ttu-id="f493a-136">Sie können nicht auf einen Index hinter dem Ende der Liste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f493a-136">You cannot access an index beyond the end of the list.</span></span> <span data-ttu-id="f493a-137">Denken Sie daran, dass Indizes auf 0 (null) starten, damit der größte gültige Index eine ist kleiner als die Anzahl der Elemente in der Liste.</span><span class="sxs-lookup"><span data-stu-id="f493a-137">Remember that indices start at 0, so the largest valid index is one less than the number of items in the list.</span></span> <span data-ttu-id="f493a-138">Sie können überprüfen, wie lange die Liste verwendet die <xref:System.Collections.Generic.List%601.Count%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f493a-138">You can check how long the list is using the <xref:System.Collections.Generic.List%601.Count%2A> property.</span></span> <span data-ttu-id="f493a-139">Fügen Sie den folgenden Code am Ende der Main-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="f493a-139">Add the following code at the end of the Main method:</span></span>

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

<span data-ttu-id="f493a-140">Speichern der Datei, und geben `dotnet run` erneut aus, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f493a-140">Save the file, and type `dotnet run` again to see the results.</span></span>    

## <a name="search-and-sort-lists"></a><span data-ttu-id="f493a-141">Suchen und sortieren Listen</span><span class="sxs-lookup"><span data-stu-id="f493a-141">Search and sort lists</span></span>
<span data-ttu-id="f493a-142">Unsere Beispiele relativ kleine Listen werden verwendet, aber Ihre Anwendungen möglicherweise häufig Listen mit viele weitere Elemente, manchmal in Tausenden Nummerierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="f493a-142">Our samples use relatively small lists, but your applications may often create lists with many more elements, sometimes numbering in the thousands.</span></span> <span data-ttu-id="f493a-143">In diesen größere Sammlungen nach Elementen suchen möchten, müssen Sie die Liste der für verschiedene Elemente durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f493a-143">To find elements in these larger collections, you need to search the list for different items.</span></span> <span data-ttu-id="f493a-144">Die <xref:System.Collections.Generic.List%601.IndexOf%2A> Methode sucht nach einem Element und gibt den Index des Elements zurück.</span><span class="sxs-lookup"><span data-stu-id="f493a-144">The <xref:System.Collections.Generic.List%601.IndexOf%2A> method searches for an item and returns the index of the item.</span></span> <span data-ttu-id="f493a-145">Fügen Sie diesen Code am Ende Ihrer `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="f493a-145">Add this code to the bottom of your `Main` method:</span></span>

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

<span data-ttu-id="f493a-146">Die Elemente in der Liste können auch sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="f493a-146">The items in your list can be sorted as well.</span></span> <span data-ttu-id="f493a-147">Die <xref:System.Collections.Generic.List%601.Sort%2A> Methode werden alle Elemente in der Liste in der normalen Reihenfolge (in alphabetischer Reihenfolge im Fall von Zeichenfolgen).</span><span class="sxs-lookup"><span data-stu-id="f493a-147">The <xref:System.Collections.Generic.List%601.Sort%2A> method sorts all the items in the list in their normal order (alphabetically in the case of strings).</span></span> <span data-ttu-id="f493a-148">Fügen Sie diesen Code am Ende unserer `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="f493a-148">Add this code to the bottom of our `Main` method:</span></span>

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

<span data-ttu-id="f493a-149">Speichern Sie die Datei und den Typ `dotnet run` versucht, diese neueste Version.</span><span class="sxs-lookup"><span data-stu-id="f493a-149">Save the file and type `dotnet run` to try this latest version.</span></span>

<span data-ttu-id="f493a-150">Bevor Sie im nächsten Abschnitt beginnen, fahren wir den aktuellen Code in eine separate Methode ein.</span><span class="sxs-lookup"><span data-stu-id="f493a-150">Before you start the next section, let's move the current code into a separate method.</span></span> <span data-ttu-id="f493a-151">Die erleichtert das Arbeiten mit einem neuen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="f493a-151">That makes it easier to start working with a new example.</span></span> <span data-ttu-id="f493a-152">Benennen Sie Ihre `Main` aufzurufende Methode `WorkingWithStrings` und Schreiben Sie ein neues `Main` Methode, die aufgerufen `WorkingWithStrings`.</span><span class="sxs-lookup"><span data-stu-id="f493a-152">Rename your `Main` method to `WorkingWithStrings` and write a new `Main` method that calls `WorkingWithStrings`.</span></span> <span data-ttu-id="f493a-153">Wenn Sie fertig sind, sollte der Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f493a-153">When you have finished, your code should look like this:</span></span>

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

## <a name="lists-of-other-types"></a><span data-ttu-id="f493a-154">Listen mit anderen Typen</span><span class="sxs-lookup"><span data-stu-id="f493a-154">Lists of other types</span></span>

<span data-ttu-id="f493a-155">Haben Sie verwendet wurden die `string` Typ in Listen bisher.</span><span class="sxs-lookup"><span data-stu-id="f493a-155">You've been using the `string` type in lists so far.</span></span> <span data-ttu-id="f493a-156">Wir stellen eine <xref:System.Collections.Generic.List%601> mithilfe eines anderen Typs.</span><span class="sxs-lookup"><span data-stu-id="f493a-156">Let's make a <xref:System.Collections.Generic.List%601> using a different type.</span></span> <span data-ttu-id="f493a-157">Erstellen Sie eine Menge von Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f493a-157">Let's build a set of numbers.</span></span> 

<span data-ttu-id="f493a-158">Fügen Sie Folgendes am Ende Ihrer neuen `Main` Methode:</span><span class="sxs-lookup"><span data-stu-id="f493a-158">Add the following to the bottom of your new `Main` method:</span></span>

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

<span data-ttu-id="f493a-159">Die eine Liste mit ganzen Zahlen erstellt, und legt die ersten beiden Ganzzahlen auf den Wert 1 fest.</span><span class="sxs-lookup"><span data-stu-id="f493a-159">That creates a list of integers, and sets the first two integers to the value 1.</span></span> <span data-ttu-id="f493a-160">Dies sind die ersten beiden Werte, der eine *Fibonacci-Sequenz*, eine Sequenz von Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f493a-160">These are the first two values of a *Fibonacci Sequence*, a sequence of numbers.</span></span> <span data-ttu-id="f493a-161">Jede nächste Fibonacci-Zahl wird ermittelt, indem die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f493a-161">Each next Fibonacci number is found by taking the sum of the previous two numbers.</span></span> <span data-ttu-id="f493a-162">Fügen Sie diesen Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="f493a-162">Add this code:</span></span>

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

<span data-ttu-id="f493a-163">Speichern Sie die Datei und den Typ `dotnet run` um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f493a-163">Save the file and type `dotnet run` to see the results.</span></span> 

> [!TIP]
> <span data-ttu-id="f493a-164">Um auf die nur in diesem Abschnitt zu konzentrieren, können Sie Auskommentieren der aufrufende Code `WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="f493a-164">To concentrate on just this section, you can comment out the code that calls `WorkingWithStrings();`.</span></span> <span data-ttu-id="f493a-165">Einfach zwei `/` Zeichen vor dem Aufruf wie folgt: `// WorkingWithStrings();`.</span><span class="sxs-lookup"><span data-stu-id="f493a-165">Just put two `/` characters in front of the call like this:  `// WorkingWithStrings();`.</span></span> 

## <a name="challenge"></a><span data-ttu-id="f493a-166">Herausforderung</span><span class="sxs-lookup"><span data-stu-id="f493a-166">Challenge</span></span>
<span data-ttu-id="f493a-167">Überprüfen, ob Sie zusammen platzieren können einige der in den Lektionen aus dieser und früheren Lektionen.</span><span class="sxs-lookup"><span data-stu-id="f493a-167">See if you can put together some of the lessons from this and earlier lessons.</span></span> <span data-ttu-id="f493a-168">Erweitern Sie auf, was Sie bisher mit Fibonacci-Zahlen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="f493a-168">Expand on what you've built so far with Fibonacci Numbers.</span></span> <span data-ttu-id="f493a-169">Versuchen Sie es, und Schreiben Sie den Code, um die ersten 20 Zahlen in der Sequenz zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f493a-169">Try and write the code to generate the first 20 numbers in the sequence.</span></span>

## <a name="complete-challenge"></a><span data-ttu-id="f493a-170">Vollständige Herausforderung</span><span class="sxs-lookup"><span data-stu-id="f493a-170">Complete challenge</span></span>

<span data-ttu-id="f493a-171">Sehen Sie eine beispiellösung von [Betrachtung der fertig gestellten Beispiel-Codes auf GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)</span><span class="sxs-lookup"><span data-stu-id="f493a-171">You can see an example solution by [looking at the finished sample code on GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs)</span></span>

<span data-ttu-id="f493a-172">Bei jeder Iteration der Schleife weitergeleitet Sie die letzten beiden Ganzzahlen in der Liste, und diesen Wert zur Liste hinzufügen, summiert werden.</span><span class="sxs-lookup"><span data-stu-id="f493a-172">With each iteration of the loop, you're taking the last two integers in the list, summing them, and adding that value to the list.</span></span> <span data-ttu-id="f493a-173">Die Schleife wird wiederholt, bis Sie die Liste 20 Elemente hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="f493a-173">The loop repeats until you've added 20 items to the list.</span></span>

<span data-ttu-id="f493a-174">Herzlichen Glückwunsch, Sie haben das Lernprogramm Liste abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f493a-174">Congratulations, you've completed the list tutorial.</span></span>

<span data-ttu-id="f493a-175">Weitere Informationen finden Sie Informationen zum Arbeiten mit der `List` Geben Sie in der [Handbuch für die .NET](../../standard/index.md) Thema auf [Sammlungen](../../standard/collections/index.md).</span><span class="sxs-lookup"><span data-stu-id="f493a-175">You can learn more about working with the `List` type in the [.NET Guide](../../standard/index.md) topic on [collections](../../standard/collections/index.md).</span></span> <span data-ttu-id="f493a-176">Sie erfahren auch über viele andere Sammlungstypen.</span><span class="sxs-lookup"><span data-stu-id="f493a-176">You'll also learn about many other collection types.</span></span>
