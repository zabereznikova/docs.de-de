---
title: Arbeiten mit LINQ
description: In diesem Tutorial erfahren Sie, wie Sie Sequenzen mit LINQ generieren, Methoden zur Verwendung in LINQ-Abfragen schreiben und zwischen strikter Auswertung (Eager Evaluation) und verzögerter Auswertung (Lazy Evaluation) unterscheiden.
ms.date: 10/29/2018
ms.technology: csharp-linq
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: ece001e82c0aa44a91999bea78d2fd695ff9362b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240014"
---
# <a name="work-with-language-integrated-query-linq"></a><span data-ttu-id="c205a-103">Arbeiten mit LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c205a-103">Work with Language-Integrated Query (LINQ)</span></span>

## <a name="introduction"></a><span data-ttu-id="c205a-104">Einführung</span><span class="sxs-lookup"><span data-stu-id="c205a-104">Introduction</span></span>

<span data-ttu-id="c205a-105">In diesem Tutorial lernen Sie Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="c205a-105">This tutorial teaches you features in .NET Core and the C# language.</span></span> <span data-ttu-id="c205a-106">Sie lernen, die folgende Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c205a-106">You’ll learn how to:</span></span>

- <span data-ttu-id="c205a-107">Generieren von Sequenzen mit LINQ.</span><span class="sxs-lookup"><span data-stu-id="c205a-107">Generate sequences with LINQ.</span></span>
- <span data-ttu-id="c205a-108">Schreiben von Methoden, die sich problemlos in LINQ-Abfragen verwenden lassen.</span><span class="sxs-lookup"><span data-stu-id="c205a-108">Write methods that can be easily used in LINQ queries.</span></span>
- <span data-ttu-id="c205a-109">Unterscheiden zwischen strenger und verzögerter Auswertung.</span><span class="sxs-lookup"><span data-stu-id="c205a-109">Distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="c205a-110">Sie lernen diese Techniken durch Erstellen einer Anwendung, die eine der grundlegenden Fertigkeiten jedes Zauberkünstlers demonstriert: den [Faro-Shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="c205a-110">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="c205a-111">Ein Faro-Shuffle ist eine Kartenmischtechnik, bei der zwei Kartenpäckchen exakt so ineinander gefächert werden, dass auf eine Karte des einen Stapels stets eine Karte des anderen Stapels folgt.</span><span class="sxs-lookup"><span data-stu-id="c205a-111">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="c205a-112">Zauberer verwenden diese Technik, weil sie damit nach jedem Mischen genau wissen, welche Karte sich wo befindet, und die Reihenfolge ein sich wiederholendes Muster ist.</span><span class="sxs-lookup"><span data-stu-id="c205a-112">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span>

<span data-ttu-id="c205a-113">Im vorliegenden Artikel dient die Technik dazu, das Manipulieren von Datensequenzen mit einem anschaulichen Beispiel zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="c205a-113">For your purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="c205a-114">Die von Ihnen erstellte Anwendung stellt einen Kartenstapel zusammen und führt dann eine Sequenz aus Mischvorgängen aus, wobei die Sequenz jedes Mal ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-114">The application you'll build constructs a card deck and then performs a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="c205a-115">Sie werden auch die aktualisierte mit der ursprünglichen Reihenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c205a-115">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="c205a-116">Dieses Tutorial besteht aus vielen Schritten.</span><span class="sxs-lookup"><span data-stu-id="c205a-116">This tutorial has multiple steps.</span></span> <span data-ttu-id="c205a-117">Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="c205a-117">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="c205a-118">Sie können sich auch das [abgeschlossene Beispiel](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in unserem Repository „dotnet/samples“ auf GitHub ansehen.</span><span class="sxs-lookup"><span data-stu-id="c205a-118">You can also see the [completed sample](https://github.com/dotnet/samples/blob/master/csharp/getting-started/console-linq) in the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="c205a-119">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="c205a-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c205a-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c205a-120">Prerequisites</span></span>

<span data-ttu-id="c205a-121">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="c205a-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="c205a-122">Die Installationsanweisungen finden Sie auf der Downloadseite für [.NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="c205a-122">You can find the installation instructions on the [.NET Core Download](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="c205a-123">Sie können diese Anwendung unter Windows, Ubuntu Linux, OS X oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="c205a-123">You can run this application on Windows, Ubuntu Linux, or OS X, or in a Docker container.</span></span> <span data-ttu-id="c205a-124">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="c205a-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="c205a-125">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open-Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="c205a-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross-platform editor.</span></span> <span data-ttu-id="c205a-126">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="c205a-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="c205a-127">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="c205a-127">Create the Application</span></span>

<span data-ttu-id="c205a-128">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="c205a-128">The first step is to create a new application.</span></span> <span data-ttu-id="c205a-129">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c205a-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="c205a-130">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="c205a-130">Make that the current directory.</span></span> <span data-ttu-id="c205a-131">Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="c205a-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="c205a-132">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="c205a-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="c205a-133">Wenn Sie C# noch nie verwendet haben, erläutert [dieses Tutorial](console-teleprompter.md) die Struktur eines C#-Programms.</span><span class="sxs-lookup"><span data-stu-id="c205a-133">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="c205a-134">Sie können dieses Tutorial lesen und dann zu diesem Artikel zurückkehren, um mehr über LINQ zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="c205a-134">You can read that and then return here to learn more about LINQ.</span></span>

## <a name="create-the-data-set"></a><span data-ttu-id="c205a-135">Erstellen des Datasets</span><span class="sxs-lookup"><span data-stu-id="c205a-135">Create the Data Set</span></span>

<span data-ttu-id="c205a-136">Bevor Sie beginnen, stellen Sie sicher, dass die folgenden Zeilen am Anfang der Datei `Program.cs` stehen, die von `dotnet new console` generiert wurde:</span><span class="sxs-lookup"><span data-stu-id="c205a-136">Before you begin, make sure that the following lines are at the top of the `Program.cs` file generated by `dotnet new console`:</span></span>

```csharp
// Program.cs
using System;
using System.Collections.Generic;
using System.Linq;
```

<span data-ttu-id="c205a-137">Wenn diese drei Zeilen (`using`-Anweisungen) nicht am Anfang der Datei stehen, wird unser Programm nicht kompiliert.</span><span class="sxs-lookup"><span data-stu-id="c205a-137">If these three lines (`using` statements) aren't at the top of the file, our program will not compile.</span></span>

<span data-ttu-id="c205a-138">Jetzt haben Sie alle nötigen Referenzen und können die Struktur eines Spielkartenstapels berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="c205a-138">Now that you have all of the references that you'll need, consider what constitutes a deck of cards.</span></span> <span data-ttu-id="c205a-139">In der Regel besteht ein Spielkartenstapel aus vier Farben, und jede hat dreizehn Werte.</span><span class="sxs-lookup"><span data-stu-id="c205a-139">Commonly, a deck of playing cards has four suits, and each suit has thirteen values.</span></span> <span data-ttu-id="c205a-140">In der Regel würden Sie wohl direkt eine `Card`-Klasse erstellen und eine Sammlung von `Card`-Objekten manuell füllen.</span><span class="sxs-lookup"><span data-stu-id="c205a-140">Normally, you might consider creating a `Card` class right off the bat and populating a collection of `Card` objects by hand.</span></span> <span data-ttu-id="c205a-141">Mit LINQ können Sie einen Spielkartenstapel präziser als üblich erstellen.</span><span class="sxs-lookup"><span data-stu-id="c205a-141">With LINQ, you can be more concise than the usual way of dealing with creating a deck of cards.</span></span> <span data-ttu-id="c205a-142">Statt eine `Card`-Klasse zu erstellen, können Sie zwei Sequenzen zur Darstellung von Farben und Rängen erstellen.</span><span class="sxs-lookup"><span data-stu-id="c205a-142">Instead of creating a `Card` class, you can create two sequences to represent suits and ranks, respectively.</span></span> <span data-ttu-id="c205a-143">Sie erstellen ein einfaches Paar von [*Iteratormethoden*](../iterators.md#enumeration-sources-with-iterator-methods), das die Ränge und Farben als <xref:System.Collections.Generic.IEnumerable%601>s von Zeichenfolgen generiert:</span><span class="sxs-lookup"><span data-stu-id="c205a-143">You'll create a really simple pair of [*iterator methods*](../iterators.md#enumeration-sources-with-iterator-methods) that will generate the ranks and suits as <xref:System.Collections.Generic.IEnumerable%601>s of strings:</span></span>

```csharp
// Program.cs
// The Main() method

static IEnumerable<string> Suits()
{
    yield return "clubs";
    yield return "diamonds";
    yield return "hearts";
    yield return "spades";
}

static IEnumerable<string> Ranks()
{
    yield return "two";
    yield return "three";
    yield return "four";
    yield return "five";
    yield return "six";
    yield return "seven";
    yield return "eight";
    yield return "nine";
    yield return "ten";
    yield return "jack";
    yield return "queen";
    yield return "king";
    yield return "ace";
}
```

<span data-ttu-id="c205a-144">Platzieren Sie diese unterhalb der `Main`-Methode in Ihrer `Program.cs`-Datei.</span><span class="sxs-lookup"><span data-stu-id="c205a-144">Place these underneath the `Main` method in your `Program.cs` file.</span></span> <span data-ttu-id="c205a-145">Diese Methoden nutzen beide die `yield return`-Syntax, um während der Ausführung eine Sequenz zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="c205a-145">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="c205a-146">Der Compiler erstellt ein Objekt, das <xref:System.Collections.Generic.IEnumerable%601>implementiert und die Sequenz aus Zeichenfolgen erst dann generiert, wenn diese angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-146">The compiler builds an object that implements <xref:System.Collections.Generic.IEnumerable%601> and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="c205a-147">Verwenden Sie nun diese Iteratormethoden, um den Spielkartenstapel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c205a-147">Now, use these iterator methods to create the deck of cards.</span></span> <span data-ttu-id="c205a-148">Sie platzieren die LINQ-Abfrage in unserer `Main`-Methode.</span><span class="sxs-lookup"><span data-stu-id="c205a-148">You'll place the LINQ query in our `Main` method.</span></span> <span data-ttu-id="c205a-149">Sie sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="c205a-149">Here's a look at it:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    // Display each card that we've generated and placed in startingDeck in the console
    foreach (var card in startingDeck)
    {
        Console.WriteLine(card);
    }
}
```

<span data-ttu-id="c205a-150">Die verschiedenen `from`-Klauseln erzeugen <xref:System.Linq.Enumerable.SelectMany%2A>, wodurch aus der Kombination jedes Elements in der ersten Sequenz mit jedem Element in der zweiten Sequenz eine einzige Sequenz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-150">The multiple `from` clauses produce a <xref:System.Linq.Enumerable.SelectMany%2A>, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="c205a-151">Für unsere Zwecke ist die Reihenfolge wichtig.</span><span class="sxs-lookup"><span data-stu-id="c205a-151">The order is important for our purposes.</span></span> <span data-ttu-id="c205a-152">Das erste Element in der ersten Quellsequenz (Farben) wird mit jedem Element in der zweiten Sequenz (Ränge) kombiniert.</span><span class="sxs-lookup"><span data-stu-id="c205a-152">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Ranks).</span></span> <span data-ttu-id="c205a-153">Dadurch werden alle dreizehn Karten der ersten Farbe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="c205a-153">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="c205a-154">Dieser Vorgang wird mit jedem Element in der ersten Sequenz (Farben) wiederholt.</span><span class="sxs-lookup"><span data-stu-id="c205a-154">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="c205a-155">Das Ergebnis ist ein Kartenstapel, der erst nach Farben und innerhalb der Farben nach Werten sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="c205a-155">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="c205a-156">Beachten Sie unbedingt Folgendes: Ob Sie LINQ-Anweisungen in der oben verwendeten Abfragesyntax schreiben oder stattdessen die Methodensyntax verwenden, Sie können immer von einer Form der Syntax zur anderen wechseln.</span><span class="sxs-lookup"><span data-stu-id="c205a-156">It's important to keep in mind that whether you choose to write your LINQ in the query syntax used above or use method syntax instead, it's always possible to go from one form of syntax to the other.</span></span> <span data-ttu-id="c205a-157">Die obige, in der Abfragesyntax geschriebene Abfrage kann in der Methodensyntax geschrieben werden als:</span><span class="sxs-lookup"><span data-stu-id="c205a-157">The above query written in query syntax can be written in method syntax as:</span></span>

```csharp
var startingDeck = Suits().SelectMany(suit => Ranks().Select(rank => new { Suit = suit, Rank = rank }));
```

<span data-ttu-id="c205a-158">Der Compiler übersetzt mit der Abfragesyntax geschriebene LINQ-Anweisungen in die entsprechende Methodenaufrufsyntax.</span><span class="sxs-lookup"><span data-stu-id="c205a-158">The compiler translates LINQ statements written with query syntax into the equivalent method call syntax.</span></span> <span data-ttu-id="c205a-159">Aus diesem Grund erzielen unabhängig von Ihrer Syntaxwahl die beiden Versionen der Abfrage das gleiche Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="c205a-159">Therefore, regardless of your syntax choice, the two versions of the query produce the same result.</span></span> <span data-ttu-id="c205a-160">Wählen Sie die beste Syntax für Ihre Situation aus: Wenn Sie z.B. in einem Team arbeiten, in dem einige Mitglieder mit der Methodensyntax Schwierigkeiten haben, versuchen Sie, die Abfragesyntax zu bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="c205a-160">Choose which syntax works best for your situation: for instance, if you're working in a team where some of the members have difficulty with method syntax, try to prefer using query syntax.</span></span>

<span data-ttu-id="c205a-161">Führen Sie jetzt das erstellte Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="c205a-161">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="c205a-162">Es werden alle 52 Karten des Kartenstapels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c205a-162">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="c205a-163">Es kann sehr hilfreich sein, dieses Beispiel mit einem Debugger auszuführen, um zu beobachten, wie die Methoden `Suits()` und `Ranks()` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-163">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Ranks()` methods execute.</span></span> <span data-ttu-id="c205a-164">Sie können deutlich erkennen, dass jede Zeichenfolge in jeder Sequenz erst dann erstellt wird, wenn sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-164">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Ein Konsolenfenster, das die App zeigt, die 52 Karten schreibt.](./media/working-with-linq/console-52-card-application.png)

## <a name="manipulate-the-order"></a><span data-ttu-id="c205a-166">Ändern der Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="c205a-166">Manipulate the Order</span></span>

<span data-ttu-id="c205a-167">Konzentrieren Sie sich nun darauf, wie die Karten im Kartenstapel gemischt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c205a-167">Next, focus on how you're going to shuffle the cards in the deck.</span></span> <span data-ttu-id="c205a-168">Der erste Schritt bei jedem guten Mischen ist das Aufteilen des Kartenstapels in zwei Hälften.</span><span class="sxs-lookup"><span data-stu-id="c205a-168">The first step in any good shuffle is to split the deck in two.</span></span> <span data-ttu-id="c205a-169">Die zu den LINQ-APIs gehörenden Methoden <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> stellen Ihnen diese Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="c205a-169">The <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> methods that are part of the LINQ APIs provide that feature for you.</span></span> <span data-ttu-id="c205a-170">Platzieren Sie sie unterhalb der `foreach`-Schleife:</span><span class="sxs-lookup"><span data-stu-id="c205a-170">Place them underneath the `foreach` loop:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    // 52 cards in a deck, so 52 / 2 = 26
    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
}
```

<span data-ttu-id="c205a-171">In der Standardbibliothek ist jedoch keine Mischmethode vorhanden, Sie müssen sie also selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="c205a-171">However, there's no shuffle method to take advantage of in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="c205a-172">Die Mischmethode, die Sie erstellen, veranschaulicht verschiedene Techniken, die Sie mit LINQ-basierten Programmen verwenden, sodass jeder Teil dieses Prozesses in Schritten erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-172">The shuffle method you'll be creating illustrates several techniques that you'll use with LINQ-based programs, so each part of this process will be explained in steps.</span></span>

<span data-ttu-id="c205a-173">Um Funktionalität für Ihre Interaktion mit den <xref:System.Collections.Generic.IEnumerable%601>-Formen, die Sie von einigen LINQ-Abfragen erhalten, hinzuzufügen, müssen Sie einige besondere Arten von Methoden schreiben, die als [Erweiterungsmethoden](../programming-guide/classes-and-structs/extension-methods.md) bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-173">In order to add some functionality to how you interact with the <xref:System.Collections.Generic.IEnumerable%601> you'll get back from LINQ queries, you'll need to write some special kinds of methods called [extension methods](../programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="c205a-174">Eine Erweiterungsmethode ist im Wesentlichen eine *statische Methode* für einen speziellen Zweck, die einem bereits vorhandenen Typ Funktionalität hinzufügt, ohne diesen ursprünglichen Typ ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="c205a-174">Briefly, an extension method is a special purpose *static method* that adds new functionality to an already-existing type without having to modify the original type you want to add functionality to.</span></span>

<span data-ttu-id="c205a-175">Fügen Sie für Ihre Erweiterungsmethoden eine neue *statische* Klassendatei namens `Extensions.cs` Ihrem Programm hinzu, und beginnen Sie dann, die erste Erweiterungsmethode zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c205a-175">Give your extension methods a new home by adding a new *static* class file to your program called `Extensions.cs`, and then start building out the first extension method:</span></span>

```csharp
// Extensions.cs
using System;
using System.Collections.Generic;
using System.Linq;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>(this IEnumerable<T> first, IEnumerable<T> second)
        {
            // Your implementation will go here soon enough
        }
    }
}
```

<span data-ttu-id="c205a-176">Beachten Sie für einen Moment die Signatur der Methode, insbesondere die Parameter:</span><span class="sxs-lookup"><span data-stu-id="c205a-176">Look at the method signature for a moment, specifically the parameters:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T> (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="c205a-177">Sie sehen, dass dem ersten Argument der Methode der `this`-Modifizierer hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="c205a-177">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="c205a-178">Dies bedeutet, dass Sie die Methode so aufrufen können, als wäre sie eine Membermethode vom Typ des ersten Arguments.</span><span class="sxs-lookup"><span data-stu-id="c205a-178">That means you call the method as though it were a member method of the type of the first argument.</span></span> <span data-ttu-id="c205a-179">Diese Methodendeklaration folgt auch einem Standardidiom, bei dem die Eingabe- und Ausgabetypen `IEnumerable<T>` sind.</span><span class="sxs-lookup"><span data-stu-id="c205a-179">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="c205a-180">Auf diese Weise können LINQ-Methoden miteinander verkettet werden, um komplexere Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c205a-180">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

<span data-ttu-id="c205a-181">Wenn Sie den Kartenstapel in zwei Hälften geteilt haben, müssen Sie diese Hälften natürlich auch wieder zusammenführen.</span><span class="sxs-lookup"><span data-stu-id="c205a-181">Naturally, since you split the deck into halves, you'll need to join those halves together.</span></span> <span data-ttu-id="c205a-182">Im Code zählen Sie beide Sequenzen, die Sie durch <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A> erhalten haben, gleichzeitig auf, führen ein *`interleaving`* der Elemente durch und erstellen eine einzige Sequenz: Ihr jetzt gemischter Kartenstapel.</span><span class="sxs-lookup"><span data-stu-id="c205a-182">In code, this means you'll be enumerating both of the sequences you acquired through <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A> at once, *`interleaving`* the elements, and creating one sequence: your now-shuffled deck of cards.</span></span> <span data-ttu-id="c205a-183">Um eine LINQ-Methode schreiben zu können, die mit Sequenzen arbeitet, müssen Sie verstehen, wie <xref:System.Collections.Generic.IEnumerable%601> funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c205a-183">Writing a LINQ method that works with two sequences requires that you understand how <xref:System.Collections.Generic.IEnumerable%601> works.</span></span>

<span data-ttu-id="c205a-184">Die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle weist eine einzige Methode auf: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="c205a-184">The <xref:System.Collections.Generic.IEnumerable%601> interface has one method: <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>.</span></span> <span data-ttu-id="c205a-185">Das von <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> zurückgegebene Objekt verfügt über eine Methode, um zum nächsten Element zu wechseln, und eine Eigenschaft, die das aktuelle Element in der Sequenz abruft.</span><span class="sxs-lookup"><span data-stu-id="c205a-185">The object returned by <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="c205a-186">Sie verwenden diese beiden Member, um die Auflistung aufzuzählen und die Elemente zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c205a-186">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="c205a-187">Diese Interleavemethode ist eine Iteratormethode, daher verwenden Sie die oben gezeigte `yield return`-Syntax, anstatt eine Auflistung zu erstellen und die Auflistung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c205a-187">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span>

<span data-ttu-id="c205a-188">Hier sehen Sie die Implementierung dieser Methode:</span><span class="sxs-lookup"><span data-stu-id="c205a-188">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="c205a-189">Nachdem Sie diese Methode geschrieben haben, kehren Sie jetzt zur `Main`-Methode zurück und mischen den Kartenstapel ein Mal:</span><span class="sxs-lookup"><span data-stu-id="c205a-189">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = from s in Suits()
                       from r in Ranks()
                       select new { Suit = s, Rank = r };

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    var top = startingDeck.Take(26);
    var bottom = startingDeck.Skip(26);
    var shuffle = top.InterleaveSequenceWith(bottom);

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }
}
```

## <a name="comparisons"></a><span data-ttu-id="c205a-190">Vergleiche</span><span class="sxs-lookup"><span data-stu-id="c205a-190">Comparisons</span></span>

<span data-ttu-id="c205a-191">Wie viele Mischvorgänge sind nötig, damit der Kartenstapel wieder in seiner ursprünglichen Reihenfolge vorliegt?</span><span class="sxs-lookup"><span data-stu-id="c205a-191">How many shuffles it takes to set the deck back to its original order?</span></span> <span data-ttu-id="c205a-192">Um dies herauszufinden, müssen Sie eine Methode schreiben, die ermittelt, ob zwei Sequenzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="c205a-192">To find out, you'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="c205a-193">Nachdem Sie diese Methode erstellt haben, müssen Sie den Code, der den Stapel mischt, in eine Schleife platzieren und dann prüfen, wann der Stapel wieder die ursprüngliche Reihenfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="c205a-193">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="c205a-194">Das Schreiben einer Methode, mit der ermittelt wird, ob die beiden Sequenzen gleich sind, sollte kein Problem sein.</span><span class="sxs-lookup"><span data-stu-id="c205a-194">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="c205a-195">Die Methode hat die gleiche Struktur wie die Methode, die Sie zum Mischen des Kartenstapels geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="c205a-195">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="c205a-196">Der Unterschied ist, dass dieses Mal nicht für jedes Element ein `yield return` ausgeführt wird, sondern dass Sie die übereinstimmenden Elemente jeder Sequenz vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c205a-196">Only this time, instead of `yield return`ing each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="c205a-197">Wenn die gesamte Sequenz aufgezählt wurde und alle Elemente übereinstimmen, sind die Sequenzen gleich:</span><span class="sxs-lookup"><span data-stu-id="c205a-197">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="c205a-198">Dies zeigt ein zweites LINQ-Idiom: Terminalmethoden.</span><span class="sxs-lookup"><span data-stu-id="c205a-198">This shows a second LINQ idiom: terminal methods.</span></span> <span data-ttu-id="c205a-199">Diese Methoden akzeptieren eine Sequenz als Eingabe (bzw. in diesem Fall zwei Sequenzen) und geben einen einzelnen Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="c205a-199">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="c205a-200">Terminalmethoden sind immer die endgültige Methode in einer Kette von Methoden für eine LINQ-Abfrage, daher der Namen „Terminalmethode“.</span><span class="sxs-lookup"><span data-stu-id="c205a-200">When using terminal methods, they are always the final method in a chain of methods for a LINQ query, hence the name "terminal".</span></span>

<span data-ttu-id="c205a-201">Sie können diese Methode in Aktion sehen, wenn Sie sie verwenden, um zu ermitteln, wann der Kartenstapel wieder die ursprüngliche Reihenfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="c205a-201">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="c205a-202">Platzieren Sie den Code zum Mischen in einer Schleife, und halten Sie diese an, wenn die Sequenz wieder die ursprüngliche Reihenfolge aufweist. Wenden Sie hierzu die `SequenceEquals()`-Methode an.</span><span class="sxs-lookup"><span data-stu-id="c205a-202">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="c205a-203">Hier sehen Sie, warum diese Methode immer die letzte in einer Abfrage sein muss: sie gibt anstelle einer Sequenz einen einzelnen Wert zurück:</span><span class="sxs-lookup"><span data-stu-id="c205a-203">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
// Program.cs
static void Main(string[] args)
{
    // Query for building the deck

    // Shuffling using InterleaveSequenceWith<T>();

    var times = 0;
    // We can re-use the shuffle variable from earlier, or you can make a new one
    shuffle = startingDeck;
    do
    {
        shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

        foreach (var card in shuffle)
        {
            Console.WriteLine(card);
        }
        Console.WriteLine();
        times++;

    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="c205a-204">Führen Sie den bisher erstellten Code aus, und notieren Sie sich, wie der Kartenstapel bei jedem Mischvorgang neu angeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-204">Run the code you've got so far and take note of how the deck rearranges on each shuffle.</span></span> <span data-ttu-id="c205a-205">Nach 8 Mischvorgängen (Iterationen der Do-while-Schleife) kehrt der Stapel zur ursprünglichen Konfiguration zurück, die er hatte, als Sie ihn zum ersten Mal durch Starten der LINQ-Abfrage erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="c205a-205">After 8 shuffles (iterations of the do-while loop), the deck returns to the original configuration it was in when you first created it from the starting LINQ query.</span></span>

## <a name="optimizations"></a><span data-ttu-id="c205a-206">Optimierungen</span><span class="sxs-lookup"><span data-stu-id="c205a-206">Optimizations</span></span>

<span data-ttu-id="c205a-207">Das Beispiel, das Sie bisher erstellt haben, führt einen *Mischvorgang nach außen* aus, bei dem die oberste und unterste Karte bei jedem Durchgang gleich bleiben.</span><span class="sxs-lookup"><span data-stu-id="c205a-207">The sample you've built so far executes an *out shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="c205a-208">Als Nächstes führen wir stattdessen einen *Mischvorgang nach innen* aus, bei dem alle 52 Karten ihre Position ändern.</span><span class="sxs-lookup"><span data-stu-id="c205a-208">Let's make one change: we'll use an *in shuffle* instead, where all 52 cards change position.</span></span> <span data-ttu-id="c205a-209">Hierbei werden die Hälften so ineinander gefächert, dass die erste Karte der unteren Hälfte zur ersten Karte des Kartenstapels wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-209">For an in shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="c205a-210">Das bedeutet, dass die unterste Karte der oberen Hälfte zur untersten Karte des Stapels wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-210">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="c205a-211">Dies ist eine einfache Änderung einer einzelnen Codezeile.</span><span class="sxs-lookup"><span data-stu-id="c205a-211">This is a simple change to a singular line of code.</span></span> <span data-ttu-id="c205a-212">Aktualisieren Sie den derzeitigen Mischvorgang durch Wechseln der Positionen von <xref:System.Linq.Enumerable.Take%2A> und <xref:System.Linq.Enumerable.Skip%2A>.</span><span class="sxs-lookup"><span data-stu-id="c205a-212">Update the current shuffle query by switching the positions of <xref:System.Linq.Enumerable.Take%2A> and <xref:System.Linq.Enumerable.Skip%2A>.</span></span> <span data-ttu-id="c205a-213">Dies ändert die Reihenfolge der oberen und unteren Hälfte des Kartenstapels:</span><span class="sxs-lookup"><span data-stu-id="c205a-213">This will change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="c205a-214">Führen Sie das Programm erneut aus, Sie werden feststellen, dass 52 Iterationen nötig sind, um den Kartenstapel wieder in die ursprüngliche Reihenfolge zu bringen.</span><span class="sxs-lookup"><span data-stu-id="c205a-214">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="c205a-215">Sie werden auch einige erhebliche Leistungsabfälle beim Ausführen des Programms bemerken.</span><span class="sxs-lookup"><span data-stu-id="c205a-215">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="c205a-216">Dafür gibt es eine Anzahl von Gründen.</span><span class="sxs-lookup"><span data-stu-id="c205a-216">There are a number of reasons for this.</span></span> <span data-ttu-id="c205a-217">Sie können eine der wichtigsten Ursachen dieses Leistungsabfalls bekämpfen: die ineffiziente Nutzung der [*verzögerten Auswertung*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c205a-217">You can tackle one of the major causes of this performance drop: inefficient use of [*lazy evaluation*](../programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

<span data-ttu-id="c205a-218">Der wesentliche Aspekt der verzögerten Auswertung ist, dass eine Anweisung erst dann ausgewertet wird, wenn der Wert benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-218">Briefly, lazy evaluation states that the evaluation of a statement is not performed until its value is needed.</span></span> <span data-ttu-id="c205a-219">LINQ-Abfragen sind verzögert ausgewertete Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c205a-219">LINQ queries are statements that are evaluated lazily.</span></span> <span data-ttu-id="c205a-220">Die Sequenzen werden erst generiert, wenn die Elemente angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-220">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="c205a-221">Dies ist üblicherweise ein großer Vorteil von LINQ.</span><span class="sxs-lookup"><span data-stu-id="c205a-221">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="c205a-222">In Programmen wie diesem verursacht diese Art der Auswertung jedoch ein exponentielles Wachstum der Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="c205a-222">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="c205a-223">Denken Sie daran, dass wir den ursprünglichen Stapel mithilfe einer LINQ-Abfrage generiert haben.</span><span class="sxs-lookup"><span data-stu-id="c205a-223">Remember that we generated the original deck using a LINQ query.</span></span> <span data-ttu-id="c205a-224">Jede Mischung wird durch Ausführung dreier LINQ-Abfragen im vorherigen Kartenstapel generiert.</span><span class="sxs-lookup"><span data-stu-id="c205a-224">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="c205a-225">All diese werden verzögert ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c205a-225">All these are performed lazily.</span></span> <span data-ttu-id="c205a-226">Das bedeutet auch, dass sie bei jeder Anforderung der Sequenz erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-226">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="c205a-227">Zum Zeitpunkt der 52. Iteration haben Sie den ursprünglichen Stapel also sehr häufig neu generiert.</span><span class="sxs-lookup"><span data-stu-id="c205a-227">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="c205a-228">Nun schreiben wir ein Protokoll, das dieses Verhalten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c205a-228">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="c205a-229">Danach werden wir das Problem beheben.</span><span class="sxs-lookup"><span data-stu-id="c205a-229">Then, you'll fix it.</span></span>

<span data-ttu-id="c205a-230">Geben Sie die folgende Methode in Ihre `Extensions.cs`-Datei ein, bzw. kopieren Sie sie hinein.</span><span class="sxs-lookup"><span data-stu-id="c205a-230">In your `Extensions.cs` file, type in or copy the method below.</span></span> <span data-ttu-id="c205a-231">Diese Erweiterungsmethode erstellt eine neue Datei namens `debug.log` in Ihrem Projektverzeichnis, und zeichnet in der Protokolldatei auf, welche Abfrage derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-231">This extension method creates a new file called `debug.log` within your project directory and records what query is currently being executed to the log file.</span></span> <span data-ttu-id="c205a-232">Diese Erweiterungsmethode kann jeder Abfrage angefügt werden, um diese Abfrage als „ausgeführt“ zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c205a-232">This extension method can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/snippets/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="c205a-233">Dann werden unter `File` rote Wellenlinien angezeigt. Das bedeutet, dass dieses Element nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c205a-233">You will see a red squiggle under `File`, meaning it doesn't exist.</span></span> <span data-ttu-id="c205a-234">Es erfolgt keine Kompilierung, da der Compiler nicht weiß, worum es sich bei `File` handelt.</span><span class="sxs-lookup"><span data-stu-id="c205a-234">It won't compile, since the compiler doesn't know what `File` is.</span></span> <span data-ttu-id="c205a-235">Sie können dieses Problem lösen, indem Sie die folgende Codezeile unter die erste Zeile der Datei `Extensions.cs` einfügen:</span><span class="sxs-lookup"><span data-stu-id="c205a-235">To solve this problem, make sure to add the following line of code under the very first line in `Extensions.cs`:</span></span>

```csharp
using System.IO;
```

<span data-ttu-id="c205a-236">Dadurch sollten das Problem behoben und die roten Wellenlinien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c205a-236">This should solve the issue and the red error disappears.</span></span>

<span data-ttu-id="c205a-237">Als Nächstes instrumentieren Sie die Definition jeder Abfrage mit einer Protokollmeldung:</span><span class="sxs-lookup"><span data-stu-id="c205a-237">Next, instrument the definition of each query with a log message:</span></span>

```csharp
// Program.cs
public static void Main(string[] args)
{
    var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                        from r in Ranks().LogQuery("Rank Generation")
                        select new { Suit = s, Rank = r }).LogQuery("Starting Deck");

    foreach (var c in startingDeck)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    var times = 0;
    var shuffle = startingDeck;

    do
    {
        // Out shuffle
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        // In shuffle
        shuffle = shuffle.Skip(26).LogQuery("Bottom Half")
                .InterleaveSequenceWith(shuffle.Take(26).LogQuery("Top Half"))
                .LogQuery("Shuffle");

        foreach (var c in shuffle)
        {
            Console.WriteLine(c);
        }

        times++;
        Console.WriteLine(times);
    } while (!startingDeck.SequenceEquals(shuffle));

    Console.WriteLine(times);
}
```

<span data-ttu-id="c205a-238">Beachten Sie, dass beim Zugreifen auf eine Abfrage kein Protokolleintrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-238">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="c205a-239">Ein Protokolleintrag wird nur erstellt, wenn Sie die ursprüngliche Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="c205a-239">You log only when you create the original query.</span></span> <span data-ttu-id="c205a-240">Die Ausführung des Programms dauert immer noch lang, aber nun sehen Sie den Grund dafür.</span><span class="sxs-lookup"><span data-stu-id="c205a-240">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="c205a-241">Wenn Sie nicht warten möchten, bis das Mischen nach innen mit aktivierter Protokollierung ausgeführt wurde, wechseln Sie zurück zum Mischen nach außen.</span><span class="sxs-lookup"><span data-stu-id="c205a-241">If you run out of patience running the in shuffle with logging turned on, switch back to the out shuffle.</span></span> <span data-ttu-id="c205a-242">Sie sehen immer noch die Auswirkungen der verzögerten Auswertung.</span><span class="sxs-lookup"><span data-stu-id="c205a-242">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="c205a-243">In einer Ausführung werden 2592 Abfragen ausgeführt, einschließlich der Generierung aller Werte und Farben.</span><span class="sxs-lookup"><span data-stu-id="c205a-243">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="c205a-244">Sie können hier die Leistung des Codes verbessern, um die Anzahl der Ausführungen zu reduzieren, die Sie vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c205a-244">You can improve the performance of the code here to reduce the number of executions you make.</span></span> <span data-ttu-id="c205a-245">Eine einfache Lösung ist das *Zwischenspeichern* der Ergebnisse der ursprünglichen LINQ-Abfrage, die den Kartenstapel erstellt.</span><span class="sxs-lookup"><span data-stu-id="c205a-245">A simple fix you can make is to *cache* the results of the original LINQ query that constructs the deck of cards.</span></span> <span data-ttu-id="c205a-246">Derzeit führen Sie die Abfragen jedes Mal erneut aus, wenn die Do-while-Schleife eine Iteration durchläuft, wobei Sie jedes Mal den Kartenstapel neu erstellen und mischen.</span><span class="sxs-lookup"><span data-stu-id="c205a-246">Currently, you're executing the queries again and again every time the do-while loop goes through an iteration, re-constructing the deck of cards and reshuffling it every time.</span></span> <span data-ttu-id="c205a-247">Zum Zwischenspeichern des Kartenstapels können Sie die LINQ-Methoden <xref:System.Linq.Enumerable.ToArray%2A> und <xref:System.Linq.Enumerable.ToList%2A> nutzen; wenn Sie sie an die Abfragen anfügen, führen sie die gleichen Aktionen aus, für die Sie sie programmiert haben, aber jetzt speichern sie die Ergebnisse in einem Array oder einer Liste, je nachdem, welche Methode Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="c205a-247">To cache the deck of cards, you can leverage the LINQ methods <xref:System.Linq.Enumerable.ToArray%2A> and <xref:System.Linq.Enumerable.ToList%2A>; when you append them to the queries, they'll perform the same actions you've told them to, but now they'll store the results in an array or a list, depending on which method you choose to call.</span></span> <span data-ttu-id="c205a-248">Fügen Sie die LINQ-Methode <xref:System.Linq.Enumerable.ToArray%2A> an beide Abfragen an, und führen Sie das Programm erneut aus:</span><span class="sxs-lookup"><span data-stu-id="c205a-248">Append the LINQ method <xref:System.Linq.Enumerable.ToArray%2A> to both queries and run the program again:</span></span>

[!CODE-csharp[Main](../../../samples/snippets/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="c205a-249">Jetzt ist der Mischvorgang nach außen auf 30 Abfragen reduziert.</span><span class="sxs-lookup"><span data-stu-id="c205a-249">Now the out shuffle is down to 30 queries.</span></span> <span data-ttu-id="c205a-250">Auch beim Mischen nach innen werden Sie ähnliche Verbesserungen feststellen: Jetzt werden 162 Abfragen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c205a-250">Run again with the in shuffle and you'll see similar improvements: it now executes 162 queries.</span></span>

<span data-ttu-id="c205a-251">Bitte beachten Sie: Dieses Beispiel sollte **nur** Anwendungsfälle veranschaulichen, bei denen eine verzögerte Auswertung zu Leistungsproblemen führen kann.</span><span class="sxs-lookup"><span data-stu-id="c205a-251">Please note that this example is **designed** to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="c205a-252">Es ist wichtig, festzustellen, wo die verzögerte Auswertung die Codeleistung beeinträchtigen kann, aber es ist gleichermaßen wichtig, zu verstehen, dass nicht alle Abfragen strikt ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="c205a-252">While it's important to see where lazy evaluation can impact code performance, it's equally important to understand that not all queries should run eagerly.</span></span> <span data-ttu-id="c205a-253">Ursache der Leistungseinbußen, die auftreten, wenn Sie <xref:System.Linq.Enumerable.ToArray%2A> nicht verwenden, ist, dass jede neue Anordnung des Kartenstapels aus der vorherigen Anordnung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c205a-253">The performance hit you incur without using <xref:System.Linq.Enumerable.ToArray%2A> is because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="c205a-254">Bei der verzögerten Auswertung bedeutet dies, dass jede neue Kartenstapelkonfiguration aus dem ursprünglichen Kartenstapel erzeugt wird. Dabei wird sogar der Code ausgeführt, der den `startingDeck`-Stapel erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="c205a-254">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="c205a-255">Das verursacht eine Menge zusätzlichen Aufwands.</span><span class="sxs-lookup"><span data-stu-id="c205a-255">That causes a large amount of extra work.</span></span>

<span data-ttu-id="c205a-256">In der Praxis werden manche Algorithmen gut mit der strikten Auswertung ausgeführt, für andere eignet sich die verzögerte Auswertung besser.</span><span class="sxs-lookup"><span data-stu-id="c205a-256">In practice, some algorithms run well using eager evaluation, and others run well using lazy evaluation.</span></span> <span data-ttu-id="c205a-257">Für die routinemäßige Nutzung eignet sich die verzögerte Auswertung in der Regel besser, wenn es sich bei der Datenquelle um einen separaten Prozess handelt, beispielsweise um eine Datenbank-Engine.</span><span class="sxs-lookup"><span data-stu-id="c205a-257">For daily usage, lazy evaluation is usually a better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="c205a-258">Bei Datenbanken ermöglicht die verzögerte Auswertung komplexere Abfragen, um nur einen Roundtrip zum Datenbankprozess und zurück zu Ihrem übrigen Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c205a-258">For databases, lazy evaluation allows more complex queries to execute only one round trip to the database process and back to the rest of your code.</span></span> <span data-ttu-id="c205a-259">LINQ ist flexibel, unabhängig davon, ob Sie die verzögerte oder strikte Auswertung verwenden, also wägen Sie Ihre Prozesse ab, und wählen Sie die Art der Auswertung aus, die Ihnen die beste Leistung bietet.</span><span class="sxs-lookup"><span data-stu-id="c205a-259">LINQ is flexible whether you choose to utilize lazy or eager evaluation, so measure your processes and pick whichever kind of evaluation gives you the best performance.</span></span>

## <a name="conclusion"></a><span data-ttu-id="c205a-260">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="c205a-260">Conclusion</span></span>

<span data-ttu-id="c205a-261">In diesem Projekt wurde Folgendes behandelt:</span><span class="sxs-lookup"><span data-stu-id="c205a-261">In this project, you covered:</span></span>

- <span data-ttu-id="c205a-262">Verwendung von LINQ-Abfragen zum Aggregieren von Daten in einer sinnvollen Abfolge</span><span class="sxs-lookup"><span data-stu-id="c205a-262">using LINQ queries to aggregate data into a meaningful sequence</span></span>
- <span data-ttu-id="c205a-263">Schreiben von Erweiterungsmethoden zum Hinzufügen eigener benutzerdefinierter Funktionalität zu LINQ-Abfragen</span><span class="sxs-lookup"><span data-stu-id="c205a-263">writing Extension methods to add our own custom functionality to LINQ queries</span></span>
- <span data-ttu-id="c205a-264">Lokalisieren von Bereichen in unserem Code, in denen LINQ-Abfragen zu Leistungsproblemen wie Geschwindigkeitseinbußen führen können</span><span class="sxs-lookup"><span data-stu-id="c205a-264">locating areas in our code where our LINQ queries might run into performance issues like degraded speed</span></span>
- <span data-ttu-id="c205a-265">verzögerte und strikte Auswertung im Hinblick auf die LINQ-Abfragen und die möglichen Auswirkungen auf die Abfrageleistung</span><span class="sxs-lookup"><span data-stu-id="c205a-265">lazy and eager evaluation in regards to LINQ queries and the implications they might have on query performance</span></span>

<span data-ttu-id="c205a-266">Abgesehen von LINQ haben Sie ein wenig über die Verfahren gelernt, die Zauberer für Kartentricks anwenden.</span><span class="sxs-lookup"><span data-stu-id="c205a-266">Aside from LINQ, you learned a bit about a technique magicians use for card tricks.</span></span> <span data-ttu-id="c205a-267">Zauberer verwenden den Faro-Shuffle, weil sie damit genau steuern können, wann sich welche Karte wo im Stapel befindet.</span><span class="sxs-lookup"><span data-stu-id="c205a-267">Magicians use the Faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="c205a-268">Verderben Sie mit Ihrem Wissen jetzt aber nicht anderen den Spaß!</span><span class="sxs-lookup"><span data-stu-id="c205a-268">Now that you know, don't spoil it for everyone else!</span></span>

<span data-ttu-id="c205a-269">Weitere Informationen zu LINQ finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="c205a-269">For more information on LINQ, see:</span></span>

- [<span data-ttu-id="c205a-270">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="c205a-270">Language Integrated Query (LINQ)</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="c205a-271">Einführung in LINQ</span><span class="sxs-lookup"><span data-stu-id="c205a-271">Introduction to LINQ</span></span>](../programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="c205a-272">Grundlegende LINQ-Abfragevorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="c205a-272">Basic LINQ Query Operations (C#)</span></span>](../programming-guide/concepts/linq/basic-linq-query-operations.md)
- [<span data-ttu-id="c205a-273">Datentransformationen mit LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c205a-273">Data Transformations With LINQ (C#)</span></span>](../programming-guide/concepts/linq/data-transformations-with-linq.md)
- [<span data-ttu-id="c205a-274">Abfragesyntax und Methodensyntax in LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c205a-274">Query Syntax and Method Syntax in LINQ (C#)</span></span>](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)
- [<span data-ttu-id="c205a-275">C#-Funktionen mit LINQ-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="c205a-275">C# Features That Support LINQ</span></span>](../programming-guide/concepts/linq/features-that-support-linq.md)
