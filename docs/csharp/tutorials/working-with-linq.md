---
title: Arbeiten mit LINQ
description: "In diesem Tutorial erfahren Sie, wie Sie Sequenzen mit LINQ generieren, Methoden zur Verwendung in LINQ-Abfragen schreiben und zwischen strikter Auswertung (Eager Evaluation) und verzögerter Auswertung (Lazy Evaluation) unterscheiden."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/28/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 0db12548-82cb-4903-ac88-13103d70aa77
ms.openlocfilehash: e9707d3b67a80fface2c26c589780c60c2e293f7
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="working-with-linq"></a><span data-ttu-id="88a88-104">Arbeiten mit LINQ</span><span class="sxs-lookup"><span data-stu-id="88a88-104">Working with LINQ</span></span>

## <a name="introduction"></a><span data-ttu-id="88a88-105">Einführung</span><span class="sxs-lookup"><span data-stu-id="88a88-105">Introduction</span></span>

<span data-ttu-id="88a88-106">In diesem Tutorial lernen Sie verschiedene Features in .NET Core und der Sprache C# kennen.</span><span class="sxs-lookup"><span data-stu-id="88a88-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="88a88-107">Es werden die folgenden Themen abgedeckt:</span><span class="sxs-lookup"><span data-stu-id="88a88-107">You’ll learn:</span></span>

*   <span data-ttu-id="88a88-108">Generieren von Sequenzen mit LINQ</span><span class="sxs-lookup"><span data-stu-id="88a88-108">How to generate sequences with LINQ</span></span>
*   <span data-ttu-id="88a88-109">Schreiben von Methoden, die sich problemlos in LINQ-Abfragen verwenden lassen</span><span class="sxs-lookup"><span data-stu-id="88a88-109">How to write methods that can be easily used in LINQ queries.</span></span>
*   <span data-ttu-id="88a88-110">Unterscheiden zwischen strenger und verzögerter Auswertung</span><span class="sxs-lookup"><span data-stu-id="88a88-110">How to distinguish between eager and lazy evaluation.</span></span>

<span data-ttu-id="88a88-111">Sie lernen diese Techniken durch Erstellen einer Anwendung, die eine der grundlegenden Fertigkeiten jedes Zauberkünstlers demonstriert: den [Faro-Shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span><span class="sxs-lookup"><span data-stu-id="88a88-111">You'll learn these techniques by building an application that demonstrates one of the basic skills of any magician: the [faro shuffle](https://en.wikipedia.org/wiki/Faro_shuffle).</span></span> <span data-ttu-id="88a88-112">Ein Faro-Shuffle ist eine Kartenmischtechnik, bei der zwei Kartenpäckchen exakt so ineinander gefächert werden, dass auf eine Karte des einen Stapels stets eine Karte des anderen Stapels folgt.</span><span class="sxs-lookup"><span data-stu-id="88a88-112">Briefly, a faro shuffle is a technique where you split a card deck exactly in half, then the shuffle interleaves each one card from each half to rebuild the original deck.</span></span>

<span data-ttu-id="88a88-113">Zauberer verwenden diese Technik, weil sie damit nach jedem Mischen genau wissen, welche Karte sich wo befindet, und die Reihenfolge ein sich wiederholendes Muster ist.</span><span class="sxs-lookup"><span data-stu-id="88a88-113">Magicians use this technique because every card is in a known location after each shuffle, and the order is a repeating pattern.</span></span> 

<span data-ttu-id="88a88-114">Im vorliegenden Artikel dient die Technik dazu, das Manipulieren von Datensequenzen mit einem anschaulichen Beispiel zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="88a88-114">For our purposes, it is a light hearted look at manipulating sequences of data.</span></span> <span data-ttu-id="88a88-115">Die von Ihnen erstellte Anwendung stellt einen Kartenstapel zusammen und führt dann eine Sequenz aus Mischvorgängen aus, wobei die Sequenz jedes Mal ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-115">The application you'll build will construct a card deck, and then perform a sequence of shuffles, writing the sequence out each time.</span></span> <span data-ttu-id="88a88-116">Sie werden auch die aktualisierte mit der ursprünglichen Reihenfolge vergleichen.</span><span class="sxs-lookup"><span data-stu-id="88a88-116">You'll also compare the updated order to the original order.</span></span>

<span data-ttu-id="88a88-117">Dieses Tutorial besteht aus vielen Schritten.</span><span class="sxs-lookup"><span data-stu-id="88a88-117">This tutorial has multiple steps.</span></span> <span data-ttu-id="88a88-118">Sie können die Anwendung nach jedem Schritt ausführen und sich den Fortschritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="88a88-118">After each step, you can run the application and see the progress.</span></span> <span data-ttu-id="88a88-119">Sie können sich auch das [abgeschlossene Beispiel](https://github.com/dotnet/docs/blob/master/samples/csharp/getting-started/console-linq) in unserem Repository „dotnet/docs“ auf GitHub ansehen.</span><span class="sxs-lookup"><span data-stu-id="88a88-119">You can also see the [completed sample](https://github.com/dotnet/docs/blob/master/samples/csharp/getting-started/console-linq) in the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="88a88-120">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="88a88-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="88a88-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="88a88-121">Prerequisites</span></span>

<span data-ttu-id="88a88-122">Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten.</span><span class="sxs-lookup"><span data-stu-id="88a88-122">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="88a88-123">Die Installationsanweisungen finden Sie auf der Seite [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="88a88-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="88a88-124">Sie können diese Anwendung unter Windows, Ubuntu Linux, OS X oder in einem Docker-Container ausführen.</span><span class="sxs-lookup"><span data-stu-id="88a88-124">You can run this application on Windows, Ubuntu Linux, OS X or in a Docker container.</span></span> <span data-ttu-id="88a88-125">Sie müssen Ihren bevorzugten Code-Editor installieren.</span><span class="sxs-lookup"><span data-stu-id="88a88-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="88a88-126">In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor.</span><span class="sxs-lookup"><span data-stu-id="88a88-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="88a88-127">Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="88a88-127">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="88a88-128">Erstellen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="88a88-128">Create the Application</span></span>

<span data-ttu-id="88a88-129">Im ersten Schritt wird eine neue Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="88a88-129">The first step is to create a new application.</span></span> <span data-ttu-id="88a88-130">Öffnen Sie eine Eingabeaufforderung, und erstellen Sie ein neues Verzeichnis für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="88a88-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="88a88-131">Legen Sie das Verzeichnis als aktuelles Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="88a88-131">Make that the current directory.</span></span> <span data-ttu-id="88a88-132">Geben Sie an der Eingabeaufforderung den Befehl `dotnet new console` ein.</span><span class="sxs-lookup"><span data-stu-id="88a88-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="88a88-133">Hierdurch werden die Startdateien für eine einfache „Hello World“-Anwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="88a88-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="88a88-134">Wenn Sie C# noch nie verwendet haben, erläutert [dieses Tutorial](console-teleprompter.md) die Struktur eines C#-Programms.</span><span class="sxs-lookup"><span data-stu-id="88a88-134">If you've never used C# before, [this tutorial](console-teleprompter.md) explains the structure of a C# program.</span></span> <span data-ttu-id="88a88-135">Sie können dieses Tutorial lesen und dann zu diesem Artikel zurückkehren, um mehr über LINQ zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="88a88-135">You can read that and then return here to learn more about LINQ.</span></span> 

## <a name="creating-the-data-set"></a><span data-ttu-id="88a88-136">Erstellen des Datasets</span><span class="sxs-lookup"><span data-stu-id="88a88-136">Creating the Data Set</span></span>

<span data-ttu-id="88a88-137">Beginnen wir damit, einen Kartenstapel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="88a88-137">Let's start by creating a deck of cards.</span></span> <span data-ttu-id="88a88-138">Zu diesem Zweck erstellen Sie eine LINQ-Abfrage mit zwei Quellen (eine für die vier Farben, eine für die dreizehn Werte).</span><span class="sxs-lookup"><span data-stu-id="88a88-138">You'll do this using a LINQ query that has two sources (one for the four suits, one for the thirteen values).</span></span> <span data-ttu-id="88a88-139">Diese Quellen werden Sie zu einem aus 52 Karten bestehenden Kartenstapel kombinieren.</span><span class="sxs-lookup"><span data-stu-id="88a88-139">You'll combine those sources into a 52 card deck.</span></span> <span data-ttu-id="88a88-140">Ein `Console.WriteLine`-Auszug innerhalb einer `foreach`-Schleife zeigt die Karten an.</span><span class="sxs-lookup"><span data-stu-id="88a88-140">A `Console.WriteLine` statement inside a `foreach` loop displays the cards.</span></span>

<span data-ttu-id="88a88-141">Hier ist die Abfrage:</span><span class="sxs-lookup"><span data-stu-id="88a88-141">Here's the query:</span></span>

```csharp
var startingDeck = from s in Suits()
                   from r in Ranks()
                   select new { Suit = s, Rank = r };

foreach (var c in startingDeck)
{
    Console.WriteLine(c);
}
```

<span data-ttu-id="88a88-142">Die verschiedenen `from`-Klauseln erzeugen `SelectMany`, wodurch aus der Kombination jedes Elements in der ersten Sequenz mit jedem Element in der zweiten Sequenz eine einzige Sequenz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-142">The multiple `from` clauses produce a `SelectMany`, which creates a single sequence from combining each element in the first sequence with each element in the second sequence.</span></span> <span data-ttu-id="88a88-143">Für unsere Zwecke ist die Reihenfolge wichtig.</span><span class="sxs-lookup"><span data-stu-id="88a88-143">The order is important for our purposes.</span></span> <span data-ttu-id="88a88-144">Das erste Element in der ersten Quellsequenz (Farben) wird mit jedem Element in der zweiten Sequenz (Werte) kombiniert.</span><span class="sxs-lookup"><span data-stu-id="88a88-144">The first element in the first source sequence (Suits) is combined with every element in the second sequence (Values).</span></span> <span data-ttu-id="88a88-145">Dadurch werden alle dreizehn Karten der ersten Farbe erzeugt.</span><span class="sxs-lookup"><span data-stu-id="88a88-145">This produces all thirteen cards of first suit.</span></span> <span data-ttu-id="88a88-146">Dieser Vorgang wird mit jedem Element in der ersten Sequenz (Farben) wiederholt.</span><span class="sxs-lookup"><span data-stu-id="88a88-146">That process is repeated with each element in the first sequence (Suits).</span></span> <span data-ttu-id="88a88-147">Das Ergebnis ist ein Kartenstapel, der erst nach Farben und innerhalb der Farben nach Werten sortiert ist.</span><span class="sxs-lookup"><span data-stu-id="88a88-147">The end result is a deck of cards ordered by suits, followed by values.</span></span>

<span data-ttu-id="88a88-148">Als Nächstes müssen Sie die Methoden „Suits()“ und „Ranks()“ erstellen.</span><span class="sxs-lookup"><span data-stu-id="88a88-148">Next, you'll need to build the Suits() and Ranks() methods.</span></span> <span data-ttu-id="88a88-149">Wir beginnen mit einem einfachen Satz von *Iteratormethoden*, die die Sequenz als Enumeration von Zeichenfolgen generieren:</span><span class="sxs-lookup"><span data-stu-id="88a88-149">Let's start with a really simple set of *iterator methods* that generate the sequence as an enumerable of strings:</span></span>

```csharp
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

<span data-ttu-id="88a88-150">Diese Methoden nutzen beide die `yield return`-Syntax, um während der Ausführung eine Sequenz zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="88a88-150">These two methods both utilize the `yield return` syntax to produce a sequence as they run.</span></span> <span data-ttu-id="88a88-151">Der Compiler erstellt ein Objekt, das `IEnumerable<T>`implementiert und die Sequenz aus Zeichenfolgen erst dann generiert, wenn diese angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-151">The compiler builds an object that implements `IEnumerable<T>` and generates the sequence of strings as they are requested.</span></span>

<span data-ttu-id="88a88-152">Führen Sie jetzt das erstellte Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="88a88-152">Go ahead and run the sample you've built at this point.</span></span> <span data-ttu-id="88a88-153">Es werden alle 52 Karten des Kartenstapels angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88a88-153">It will display all 52 cards in the deck.</span></span> <span data-ttu-id="88a88-154">Es kann sehr hilfreich sein, dieses Beispiel mit einem Debugger auszuführen, um zu beobachten, wie die Methoden `Suits()` und `Values()` ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-154">You may find it very helpful to run this sample under a debugger to observe how the `Suits()` and `Values()` methods execute.</span></span> <span data-ttu-id="88a88-155">Sie können deutlich erkennen, dass jede Zeichenfolge in jeder Sequenz erst dann erstellt wird, wenn sie benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-155">You can clearly see that each string in each sequence is generated only as it is needed.</span></span>

![Konsolenfenster, das die App zeigt, die 52 Karten schreibt](./media/working-with-linq/console.png)

## <a name="manipulating-the-order"></a><span data-ttu-id="88a88-157">Ändern der Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="88a88-157">Manipulating the Order</span></span>

<span data-ttu-id="88a88-158">Als Nächstes erstellen wir eine Hilfsprogrammmethode, die das Mischen ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="88a88-158">Next, let's build a utility method that can perform the shuffle.</span></span> <span data-ttu-id="88a88-159">Der erste Schritt besteht darin, den Kartenstapel in zwei Hälften zu teilen.</span><span class="sxs-lookup"><span data-stu-id="88a88-159">The first step is to split the deck in two.</span></span> <span data-ttu-id="88a88-160">Die zu den LINQ-APIs gehörenden Methoden `Take()` und `Skip()` stellen uns diese Funktion bereit:</span><span class="sxs-lookup"><span data-stu-id="88a88-160">The `Take()` and `Skip()` methods that are part of the LINQ APIs provide that feature for us:</span></span>

```csharp
var top = startingDeck.Take(26);
var bottom = startingDeck.Skip(26);
```

<span data-ttu-id="88a88-161">Die Mischmethode ist in der Standardbibliothek nicht vorhanden, Sie müssen sie also selbst schreiben.</span><span class="sxs-lookup"><span data-stu-id="88a88-161">The shuffle method doesn't exist in the standard library, so you'll have to write your own.</span></span> <span data-ttu-id="88a88-162">Diese neue Methode veranschaulicht verschiedene Techniken, die Sie mit LINQ-basierten Programmen verwenden werden. Daher erläutern wir jeden Teil der Methode in den Schritten.</span><span class="sxs-lookup"><span data-stu-id="88a88-162">This new method illustrates several techniques that you'll use with LINQ-based programs, so let's explain each part of the method in steps.</span></span>

<span data-ttu-id="88a88-163">Die Signatur für die Methode erstellt eine *Erweiterungsmethode*:</span><span class="sxs-lookup"><span data-stu-id="88a88-163">The signature for the method creates an *extension method*:</span></span>

```csharp
public static IEnumerable<T> InterleaveSequenceWith<T>
    (this IEnumerable<T> first, IEnumerable<T> second)
```

<span data-ttu-id="88a88-164">Bei einer Erweiterungsmethode handelt es sich um eine *statische Methode*, die einem bestimmten Zweck dient.</span><span class="sxs-lookup"><span data-stu-id="88a88-164">An extension method is a special purpose *static method.*</span></span> <span data-ttu-id="88a88-165">Sie sehen, dass dem ersten Argument der Methode der `this`-Modifizierer hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="88a88-165">You can see the addition of the `this` modifier on the first argument to the method.</span></span> <span data-ttu-id="88a88-166">Dies bedeutet, dass Sie die Methode so aufrufen können, als wäre sie eine Membermethode vom Typ des ersten Arguments.</span><span class="sxs-lookup"><span data-stu-id="88a88-166">That means you call the method as though it were a member method of the type of the first argument.</span></span>

<span data-ttu-id="88a88-167">Erweiterungsmethoden können nur innerhalb von `static`-Klassen deklariert werden. Also erstellen wir hierfür eine neue statische Klasse namens `extensions`.</span><span class="sxs-lookup"><span data-stu-id="88a88-167">Extension methods can be declared only inside `static` classes, so let's create a new static class called `extensions` for this functionality.</span></span> <span data-ttu-id="88a88-168">Im weiteren Verlauf dieses Tutorials werden Sie weitere Erweiterungsmethoden hinzufügen. Diese werden in der gleichen Klasse platziert.</span><span class="sxs-lookup"><span data-stu-id="88a88-168">You'll add more extension methods as you continue this tutorial, and those will be placed in the same class.</span></span>

<span data-ttu-id="88a88-169">Diese Methodendeklaration folgt auch einem Standardidiom, bei dem die Eingabe- und Ausgabetypen `IEnumerable<T>` sind.</span><span class="sxs-lookup"><span data-stu-id="88a88-169">This method declaration also follows a standard idiom where the input and output types are `IEnumerable<T>`.</span></span> <span data-ttu-id="88a88-170">Auf diese Weise können LINQ-Methoden miteinander verkettet werden, um komplexere Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88a88-170">That practice enables LINQ methods to be chained together to perform more complex queries.</span></span>

```csharp
using System.Collections.Generic;

namespace LinqFaroShuffle
{
    public static class Extensions
    {
        public static IEnumerable<T> InterleaveSequenceWith<T>
            (this IEnumerable<T> first, IEnumerable<T> second)
        {
            // implementation coming.
        }
    }
}
```

<span data-ttu-id="88a88-171">Sie zählen beide Sequenzen gleichzeitig auf, fächern die Elemente ineinander und erstellen ein einziges Objekt.</span><span class="sxs-lookup"><span data-stu-id="88a88-171">You will be enumerating both sequences at once, interleaving the elements, and creating one object.</span></span>  <span data-ttu-id="88a88-172">Um eine LINQ-Methode schreiben zu können, die mit Sequenzen arbeitet, müssen Sie verstehen, wie `IEnumerable` funktioniert.</span><span class="sxs-lookup"><span data-stu-id="88a88-172">Writing a LINQ method that works with two sequences requires that you understand how `IEnumerable` works.</span></span>

<span data-ttu-id="88a88-173">Die `IEnumerable`-Schnittstelle weist eine einzige Methode auf: `GetEnumerator()`.</span><span class="sxs-lookup"><span data-stu-id="88a88-173">The `IEnumerable` interface has one method: `GetEnumerator()`.</span></span> <span data-ttu-id="88a88-174">Das von `GetEnumerator()` zurückgegebene Objekt verfügt über eine Methode, um zum nächsten Element zu wechseln, und eine Eigenschaft, die das aktuelle Element in der Sequenz abruft.</span><span class="sxs-lookup"><span data-stu-id="88a88-174">The object returned by `GetEnumerator()` has a method to move to the next element, and a property that retrieves the current element in the sequence.</span></span> <span data-ttu-id="88a88-175">Sie verwenden diese beiden Member, um die Auflistung aufzuzählen und die Elemente zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="88a88-175">You will use those two members to enumerate the collection and return the elements.</span></span> <span data-ttu-id="88a88-176">Diese Interleavemethode ist eine Iteratormethode, daher verwenden Sie die oben gezeigte `yield return`-Syntax, anstatt eine Auflistung zu erstellen und die Auflistung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="88a88-176">This Interleave method will be an iterator method, so instead of building a collection and returning the collection, you'll use the `yield return` syntax shown above.</span></span> 

<span data-ttu-id="88a88-177">Hier sehen Sie die Implementierung dieser Methode:</span><span class="sxs-lookup"><span data-stu-id="88a88-177">Here's the implementation of that method:</span></span>

[!CODE-csharp[InterleaveSequenceWith](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet1)]

<span data-ttu-id="88a88-178">Nachdem Sie diese Methode geschrieben haben, kehren Sie jetzt zur `Main`-Methode zurück und mischen den Kartenstapel ein Mal:</span><span class="sxs-lookup"><span data-stu-id="88a88-178">Now that you've written this method, go back to the `Main` method and shuffle the deck once:</span></span>

```csharp
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

## <a name="comparisons"></a><span data-ttu-id="88a88-179">Vergleiche</span><span class="sxs-lookup"><span data-stu-id="88a88-179">Comparisons</span></span>

<span data-ttu-id="88a88-180">Sehen wir uns an, wie viele Mischvorgänge benötigt werden, damit der Kartenstapel wieder in seiner ursprünglichen Reihenfolge vorliegt.</span><span class="sxs-lookup"><span data-stu-id="88a88-180">Let's see how many shuffles it takes to set the deck back to its original order.</span></span> <span data-ttu-id="88a88-181">Sie müssen eine Methode schreiben, die ermittelt, ob zwei Sequenzen gleich sind.</span><span class="sxs-lookup"><span data-stu-id="88a88-181">You'll need to write a method that determines if two sequences are equal.</span></span> <span data-ttu-id="88a88-182">Nachdem Sie diese Methode erstellt haben, müssen Sie den Code, der den Stapel mischt, in eine Schleife platzieren und dann prüfen, wann der Stapel wieder die ursprüngliche Reihenfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="88a88-182">After you have that method, you'll need to place the code that shuffles the deck in a loop, and check to see when the deck is back in order.</span></span>

<span data-ttu-id="88a88-183">Das Schreiben einer Methode, mit der ermittelt wird, ob die beiden Sequenzen gleich sind, sollte kein Problem sein.</span><span class="sxs-lookup"><span data-stu-id="88a88-183">Writing a method to determine if the two sequences are equal should be straightforward.</span></span> <span data-ttu-id="88a88-184">Die Methode hat die gleiche Struktur wie die Methode, die Sie zum Mischen des Kartenstapels geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="88a88-184">It's a similar structure to the method you wrote to shuffle the deck.</span></span> <span data-ttu-id="88a88-185">Der Unterschied ist, dass dieses Mal nicht jedes Element zurückgegeben werden soll, sondern dass Sie die übereinstimmenden Elemente jeder Sequenz vergleichen.</span><span class="sxs-lookup"><span data-stu-id="88a88-185">Only this time, instead of yield returning each element, you'll compare the matching elements of each sequence.</span></span> <span data-ttu-id="88a88-186">Wenn die gesamte Sequenz aufgezählt wurde und alle Elemente übereinstimmen, sind die Sequenzen gleich:</span><span class="sxs-lookup"><span data-stu-id="88a88-186">When the entire sequence has been enumerated, if every element matches, the sequences are the same:</span></span>

[!CODE-csharp[SequenceEquals](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet2)]

<span data-ttu-id="88a88-187">Dies zeigt ein zweites LINQ-Idiom: Terminalmethoden.</span><span class="sxs-lookup"><span data-stu-id="88a88-187">This shows a second Linq idiom: terminal methods.</span></span> <span data-ttu-id="88a88-188">Diese Methoden akzeptieren eine Sequenz als Eingabe (bzw. in diesem Fall zwei Sequenzen) und geben einen einzelnen Skalarwert zurück.</span><span class="sxs-lookup"><span data-stu-id="88a88-188">They take a sequence as input (or in this case, two sequences), and return a single scalar value.</span></span> <span data-ttu-id="88a88-189">Wenn diese Methoden verwendet werden, sind sie immer die letzten Methoden einer Abfrage.</span><span class="sxs-lookup"><span data-stu-id="88a88-189">These methods, when they are used, are always the final method of a query.</span></span> <span data-ttu-id="88a88-190">(Sie beenden – englisch: to terminate – die Abfrage, daher der Name.)</span><span class="sxs-lookup"><span data-stu-id="88a88-190">(Hence the name).</span></span> 

<span data-ttu-id="88a88-191">Sie können diese Methode in Aktion sehen, wenn Sie sie verwenden, um zu ermitteln, wann der Kartenstapel wieder die ursprüngliche Reihenfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="88a88-191">You can see this in action when you use it to determine when the deck is back in its original order.</span></span> <span data-ttu-id="88a88-192">Platzieren Sie den Code zum Mischen in einer Schleife, und halten Sie diese an, wenn die Sequenz wieder die ursprüngliche Reihenfolge aufweist. Wenden Sie hierzu die `SequenceEquals()`-Methode an.</span><span class="sxs-lookup"><span data-stu-id="88a88-192">Put the shuffle code inside a loop, and stop when the sequence is back in its original order by applying the `SequenceEquals()` method.</span></span> <span data-ttu-id="88a88-193">Hier sehen Sie, warum diese Methode immer die letzte in einer Abfrage sein muss: sie gibt anstelle einer Sequenz einen einzelnen Wert zurück:</span><span class="sxs-lookup"><span data-stu-id="88a88-193">You can see it would always be the final method in any query, because it returns a single value instead of a sequence:</span></span>

```csharp
var times = 0;
var shuffle = startingDeck;

do
{
    shuffle = shuffle.Take(26).InterleaveSequenceWith(shuffle.Skip(26));

    foreach (var c in shuffle)
    {
        Console.WriteLine(c);
    }

    Console.WriteLine();
    times++;
} while (!startingDeck.SequenceEquals(shuffle));

Console.WriteLine(times);
```

<span data-ttu-id="88a88-194">Führen Sie das Beispiel aus, und sehen Sie sich an, wie der Kartenstapel nach jedem Mischvorgang neu sortiert wird und nach 8 Durchgängen wieder seine ursprüngliche Konfiguration aufweist.</span><span class="sxs-lookup"><span data-stu-id="88a88-194">Run the sample, and see how the deck rearranges on each shuffle, until it returns to its original configuration after 8 iterations.</span></span>

## <a name="optimizations"></a><span data-ttu-id="88a88-195">Optimierungen</span><span class="sxs-lookup"><span data-stu-id="88a88-195">Optimizations</span></span>

<span data-ttu-id="88a88-196">Das Beispiel, das Sie bisher erstellt haben, führt einen *Mischvorgang nach innen* aus, bei dem die oberste und unterste Karte bei jedem Durchgang gleich bleiben.</span><span class="sxs-lookup"><span data-stu-id="88a88-196">The sample you've built so far executes an *in shuffle*, where the top and bottom cards stay the same on each run.</span></span> <span data-ttu-id="88a88-197">Als Nächstes führen wir einen *Mischvorgang nach außen* aus, bei dem alle 52 Karten ihre Position ändern.</span><span class="sxs-lookup"><span data-stu-id="88a88-197">Let's make one change, and run an *out shuffle*, where all 52 cards change position.</span></span> <span data-ttu-id="88a88-198">Hierbei werden die Hälften so ineinander gefächert, dass die erste Karte der unteren Hälfte zur ersten Karte des Kartenstapels wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-198">For an out shuffle, you interleave the deck so that the first card in the bottom half becomes the first card in the deck.</span></span> <span data-ttu-id="88a88-199">Das bedeutet, dass die unterste Karte der oberen Hälfte zur untersten Karte des Stapels wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-199">That means the last card in the top half becomes the bottom card.</span></span> <span data-ttu-id="88a88-200">Dazu muss nur eine Zeile geändert werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-200">That's just a one line change.</span></span> <span data-ttu-id="88a88-201">Aktualisieren Sie den Aufruf zum Mischen so, dass die Reihenfolge der oberen und unteren Hälften des Kartenstapels getauscht wird:</span><span class="sxs-lookup"><span data-stu-id="88a88-201">Update the call to shuffle to change the order of the top and bottom halves of the deck:</span></span>

```csharp
shuffle = shuffle.Skip(26).InterleaveSequenceWith(shuffle.Take(26));
```

<span data-ttu-id="88a88-202">Führen Sie das Programm erneut aus, Sie werden feststellen, dass 52 Iterationen nötig sind, um den Kartenstapel wieder in die ursprüngliche Reihenfolge zu bringen.</span><span class="sxs-lookup"><span data-stu-id="88a88-202">Run the program again, and you'll see that it takes 52 iterations for the deck to reorder itself.</span></span> <span data-ttu-id="88a88-203">Sie werden auch einige erhebliche Leistungsabfälle beim Ausführen des Programms bemerken.</span><span class="sxs-lookup"><span data-stu-id="88a88-203">You'll also start to notice some serious performance degradations as the program continues to run.</span></span>

<span data-ttu-id="88a88-204">Dafür gibt es eine Anzahl von Gründen.</span><span class="sxs-lookup"><span data-stu-id="88a88-204">There are a number of reasons for this.</span></span> <span data-ttu-id="88a88-205">Befassen wir uns mit einem der wichtigsten Gründe: der ineffizienten Nutzung der *verzögerten Auswertung*.</span><span class="sxs-lookup"><span data-stu-id="88a88-205">Let's tackle one of the major causes: inefficient use of *lazy evaluation*.</span></span>

<span data-ttu-id="88a88-206">LINQ-Abfragen werden verzögert ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="88a88-206">LINQ queries are evaluated lazily.</span></span> <span data-ttu-id="88a88-207">Die Sequenzen werden erst generiert, wenn die Elemente angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-207">The sequences are generated only as the elements are requested.</span></span> <span data-ttu-id="88a88-208">Dies ist üblicherweise ein großer Vorteil von LINQ.</span><span class="sxs-lookup"><span data-stu-id="88a88-208">Usually, that's a major benefit of LINQ.</span></span> <span data-ttu-id="88a88-209">In Programmen wie diesem verursacht diese Art der Auswertung jedoch ein exponentielles Wachstum der Ausführungszeit.</span><span class="sxs-lookup"><span data-stu-id="88a88-209">However, in a use such as this program, this causes exponential growth in execution time.</span></span>

<span data-ttu-id="88a88-210">Der ursprüngliche Kartenstapel wurde mithilfe einer LINQ-Abfrage generiert.</span><span class="sxs-lookup"><span data-stu-id="88a88-210">The original deck was generated using a LINQ query.</span></span> <span data-ttu-id="88a88-211">Jede Mischung wird durch Ausführung dreier LINQ-Abfragen im vorherigen Kartenstapel generiert.</span><span class="sxs-lookup"><span data-stu-id="88a88-211">Each shuffle is generated by performing three LINQ queries on the previous deck.</span></span> <span data-ttu-id="88a88-212">All diese werden verzögert ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="88a88-212">All these are performed lazily.</span></span> <span data-ttu-id="88a88-213">Das bedeutet auch, dass sie bei jeder Anforderung der Sequenz erneut ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-213">That also means they are performed again each time the sequence is requested.</span></span> <span data-ttu-id="88a88-214">Zum Zeitpunkt der 52. Iteration haben Sie den ursprünglichen Stapel also sehr häufig neu generiert.</span><span class="sxs-lookup"><span data-stu-id="88a88-214">By the time you get to the 52nd iteration, you're regenerating the original deck many, many times.</span></span> <span data-ttu-id="88a88-215">Nun schreiben wir ein Protokoll, das dieses Verhalten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="88a88-215">Let's write a log to demonstrate this behavior.</span></span> <span data-ttu-id="88a88-216">Danach werden wir das Problem beheben.</span><span class="sxs-lookup"><span data-stu-id="88a88-216">Then, you'll fix it.</span></span>

<span data-ttu-id="88a88-217">Im Folgenden finden Sie eine Protokollmethode, die an jede Abfrage angefügt werden kann, um diese Abfrage als „ausgeführt“ zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="88a88-217">Here's a log method that can be appended to any query to mark that the query executed.</span></span>

[!CODE-csharp[LogQuery](../../../samples/csharp/getting-started/console-linq/extensions.cs?name=snippet3)]

<span data-ttu-id="88a88-218">Als Nächstes instrumentieren Sie die Definition jeder Abfrage mit einer Protokollmeldung:</span><span class="sxs-lookup"><span data-stu-id="88a88-218">Next, instrument the definition of each query with a log message:</span></span>

```csharp
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
        /*
        shuffle = shuffle.Take(26)
            .LogQuery("Top Half")
            .InterleaveSequenceWith(shuffle.Skip(26)
            .LogQuery("Bottom Half"))
            .LogQuery("Shuffle");
        */

        shuffle = shuffle.Skip(26)
            .LogQuery("Bottom Half")
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

<span data-ttu-id="88a88-219">Beachten Sie, dass beim Zugreifen auf eine Abfrage kein Protokolleintrag erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-219">Notice that you don't log every time you access a query.</span></span> <span data-ttu-id="88a88-220">Ein Protokolleintrag wird nur erstellt, wenn Sie die ursprüngliche Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="88a88-220">You log only when you create the original query.</span></span> <span data-ttu-id="88a88-221">Die Ausführung des Programms dauert immer noch lang, aber nun sehen Sie den Grund dafür.</span><span class="sxs-lookup"><span data-stu-id="88a88-221">The program still takes a long time to run, but now you can see why.</span></span> <span data-ttu-id="88a88-222">Wenn Sie nicht warten möchten, bis das Mischen nach außen mit aktivierter Protokollierung ausgeführt wurde, wechseln Sie zurück zum Mischen nach innen.</span><span class="sxs-lookup"><span data-stu-id="88a88-222">If you run out of patience running the outer shuffle with logging turned on, switch back to the inner shuffle.</span></span> <span data-ttu-id="88a88-223">Sie sehen immer noch die Auswirkungen der verzögerten Auswertung.</span><span class="sxs-lookup"><span data-stu-id="88a88-223">You'll still see the lazy evaluation effects.</span></span> <span data-ttu-id="88a88-224">In einer Ausführung werden 2592 Abfragen ausgeführt, einschließlich der Generierung aller Werte und Farben.</span><span class="sxs-lookup"><span data-stu-id="88a88-224">In one run, it executes 2592 queries, including all the value and suit generation.</span></span>

<span data-ttu-id="88a88-225">Es gibt eine einfache Möglichkeit, dieses Programm so zu ändern, dass all diese Ausführungen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-225">There is an easy way to update this program to avoid all those executions.</span></span> <span data-ttu-id="88a88-226">Die LINQ-Methoden `ToArray()` und `ToList()` sorgen dafür, dass die Abfrage ausgeführt wird, und speichern die Ergebnisse in einem Array bzw. einer Liste.</span><span class="sxs-lookup"><span data-stu-id="88a88-226">There are LINQ methods `ToArray()` and `ToList()` that cause the query to run, and store the results in an array or a list, respectively.</span></span> <span data-ttu-id="88a88-227">Sie verwenden diese Methoden dazu, die Datenergebnisse einer Abfrage zwischenzuspeichern, anstatt die Quellabfrage erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="88a88-227">You use these methods to cache the data results of a query rather than execute the source query again.</span></span>  <span data-ttu-id="88a88-228">Fügen Sie die Abfragen, die die Kartenstapel generieren, an einen Aufruf von `ToArray()` an, und führen Sie die Abfrage erneut aus:</span><span class="sxs-lookup"><span data-stu-id="88a88-228">Append the queries that generate the card decks with a call to `ToArray()` and run the query again:</span></span>

[!CODE-csharp[Main](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet1)]

<span data-ttu-id="88a88-229">Führen Sie das Programm erneut aus – das Mischen nach innen wurde auf 30 Abfragen reduziert.</span><span class="sxs-lookup"><span data-stu-id="88a88-229">Run again, and the inner shuffle is down to 30 queries.</span></span> <span data-ttu-id="88a88-230">Auch beim Mischen nach außen werden Sie ähnliche Verbesserungen feststellen.</span><span class="sxs-lookup"><span data-stu-id="88a88-230">Run again with the outer shuffle and you'll see similar improvements.</span></span> <span data-ttu-id="88a88-231">(Dabei werden jetzt 162 Abfragen ausgeführt.)</span><span class="sxs-lookup"><span data-stu-id="88a88-231">(It now executes 162 queries).</span></span>

<span data-ttu-id="88a88-232">Sie dürfen dieses Beispiel aber nicht so interpretieren, dass alle Abfragen mit strikter Auswertung ausgeführt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="88a88-232">Don't misinterpret this example by thinking that all queries should run eagerly.</span></span> <span data-ttu-id="88a88-233">Dieses Beispiel sollte nur Anwendungsfälle veranschaulichen, bei denen eine verzögerte Auswertung zu Leistungsproblemen führen kann.</span><span class="sxs-lookup"><span data-stu-id="88a88-233">This example is designed to highlight the use cases where lazy evaluation can cause performance difficulties.</span></span> <span data-ttu-id="88a88-234">Die Ursache des Problems ist, dass jede neue Anordnung des Kartenstapels aus der vorherigen Anordnung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="88a88-234">That's because each new arrangement of the deck of cards is built from the previous arrangement.</span></span> <span data-ttu-id="88a88-235">Bei der verzögerten Auswertung bedeutet dies, dass jede neue Kartenstapelkonfiguration aus dem ursprünglichen Kartenstapel erzeugt wird. Dabei wird sogar der Code ausgeführt, der den `startingDeck`-Stapel erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="88a88-235">Using lazy evaluation means each new deck configuration is built from the original deck, even executing the code that built the `startingDeck`.</span></span> <span data-ttu-id="88a88-236">Das verursacht eine Menge zusätzlichen Aufwands.</span><span class="sxs-lookup"><span data-stu-id="88a88-236">That causes a large amount of extra work.</span></span> 

<span data-ttu-id="88a88-237">In der Praxis werden manche Algorithmen besser mit der strikten Auswertung ausgeführt, für andere eignet sich die verzögerte Auswertung besser.</span><span class="sxs-lookup"><span data-stu-id="88a88-237">In practice, some algorithms run much better using eager evaluation, and others run much better using lazy evaluation.</span></span> <span data-ttu-id="88a88-238">(Im Allgemeinen eignet sich die verzögerte Auswertung wesentlich besser, wenn es sich bei der Datenquelle um einen separaten Prozess handelt, beispielsweise um ein Datenbankmodul.</span><span class="sxs-lookup"><span data-stu-id="88a88-238">(In general, lazy evaluation is a much better choice when the data source is a separate process, like a database engine.</span></span> <span data-ttu-id="88a88-239">In diesen Fällen ermöglicht die verzögerte Auswertung komplexere Abfragen, um nur einen Roundtrip an den Datenbankprozess auszuführen.) LINQ ermöglicht sowohl eine verzögerte als auch eine strikte Auswertung.</span><span class="sxs-lookup"><span data-stu-id="88a88-239">In those cases, lazy evaluation enables more complex queries to execute only one round trip to the database process.) LINQ enables both lazy and eager evaluation.</span></span> <span data-ttu-id="88a88-240">Wählen Sie die für Ihr jeweiliges Programm am besten geeignete Variante aus.</span><span class="sxs-lookup"><span data-stu-id="88a88-240">Measure, and pick the best choice.</span></span>

## <a name="preparing-for-new-features"></a><span data-ttu-id="88a88-241">Vorbereiten auf neue Funktionen</span><span class="sxs-lookup"><span data-stu-id="88a88-241">Preparing for New Features</span></span>

<span data-ttu-id="88a88-242">Der Code, den Sie für diesen Artikel geschrieben haben, ist ein Beispiel für die Erstellung eines einfachen Prototyps, der das gewünschte Ergebnis erzielt.</span><span class="sxs-lookup"><span data-stu-id="88a88-242">The code you've written for this sample is an example of creating a simple prototype that does the job.</span></span> <span data-ttu-id="88a88-243">Er eignet sich hervorragend, um einen Problembereich zu untersuchen, und ist für viele Funktionen möglicherweise die beste dauerhafte Lösung.</span><span class="sxs-lookup"><span data-stu-id="88a88-243">This is a great way to explore a problem space, and for many features, it may be the best permanent solution.</span></span> <span data-ttu-id="88a88-244">Sie haben *anonyme Typen* für die Karten verwendet, und jede Karte wird durch Zeichenfolgen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="88a88-244">You've leveraged *anonymous types* for the cards, and each card is represented by strings.</span></span>

<span data-ttu-id="88a88-245">*Anonyme Typen* bieten viele Produktivitätsvorteile.</span><span class="sxs-lookup"><span data-stu-id="88a88-245">*Anonymous Types* have many productivity advantages.</span></span> <span data-ttu-id="88a88-246">Sie müssen nicht selbst eine Klasse definieren, um den Speicher darzustellen.</span><span class="sxs-lookup"><span data-stu-id="88a88-246">You don't need to define a class yourself to represent the storage.</span></span> <span data-ttu-id="88a88-247">Der Compiler generiert den Typ für Sie.</span><span class="sxs-lookup"><span data-stu-id="88a88-247">The compiler generates the type for you.</span></span> <span data-ttu-id="88a88-248">Der vom Compiler generierte Typ nutzt viele der bewährten Methoden für einfache Datenobjekte.</span><span class="sxs-lookup"><span data-stu-id="88a88-248">The compiler generated type utilizes many of the best practices for simple data objects.</span></span> <span data-ttu-id="88a88-249">Er ist *unveränderlich*, d.h., nach dem Erstellen kann keine seiner Eigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-249">It's *immutable*, meaning that none of its properties can be changed after it has been constructed.</span></span> <span data-ttu-id="88a88-250">Anonyme Typen sind für eine Assembly intern, gehören also nicht zur öffentlichen API für diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="88a88-250">Anonymous types are internal to an assembly, so they aren't seen as part of the public API for that assembly.</span></span> <span data-ttu-id="88a88-251">Anonyme Typen enthalten auch eine Überschreibung der `ToString()`-Methode, die eine formatierte Zeichenfolge mit den jeweiligen Werten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="88a88-251">Anonymous types also contain an override of the `ToString()` method that returns a formatted string with each of the values.</span></span>

<span data-ttu-id="88a88-252">Anonyme Typen haben jedoch auch Nachteile.</span><span class="sxs-lookup"><span data-stu-id="88a88-252">Anonymous types also have disadvantages.</span></span> <span data-ttu-id="88a88-253">Sie verfügen nicht über aufrufbare Namen, können also nicht als Rückgabewerte oder Argumente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-253">They don't have accessible names, so you can't use them as return values or arguments.</span></span> <span data-ttu-id="88a88-254">Sie werden feststellen, dass alle oben genannten Methoden, die diese anonymen Typen verwenden, generische Methoden sind.</span><span class="sxs-lookup"><span data-stu-id="88a88-254">You'll notice that any methods above that used these anonymous types are generic methods.</span></span> <span data-ttu-id="88a88-255">Die Überschreibung von `ToString()` ist möglicherweise nicht wünschenswert, wenn der Anwendung weitere Funktionen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-255">The override of `ToString()` may not be what you want as the application grows more features.</span></span> 

<span data-ttu-id="88a88-256">Das Beispiel verwendet auch Zeichenfolgen für die Farbe und den Rang jeder Karte.</span><span class="sxs-lookup"><span data-stu-id="88a88-256">The sample also uses strings for the suit and the rank of each card.</span></span> <span data-ttu-id="88a88-257">Es ist fast beliebig erweiterbar.</span><span class="sxs-lookup"><span data-stu-id="88a88-257">That's quite open ended.</span></span> <span data-ttu-id="88a88-258">Mit dem Typsystem von C# lässt sich ein besserer Code erstellen, indem `enum`-Typen für diese Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-258">The C# type system can help us make better code, by leveraging `enum` types for those values.</span></span>

<span data-ttu-id="88a88-259">Beginnen Sie mit den Farben.</span><span class="sxs-lookup"><span data-stu-id="88a88-259">Start with the suits.</span></span> <span data-ttu-id="88a88-260">Jetzt ist der perfekte Zeitpunkt, einen `enum`-Typ zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="88a88-260">This is a perfect time to use an `enum`:</span></span>

[!CODE-csharp[Suit enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet2)]

<span data-ttu-id="88a88-261">Die `Suits()`-Methode ändert auch den Typ und Implementierung:</span><span class="sxs-lookup"><span data-stu-id="88a88-261">The `Suits()` method also changes type and implementation:</span></span>

[!CODE-csharp[Suit IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet4)]

<span data-ttu-id="88a88-262">Als Nächstes nehmen Sie die gleiche Änderung am Rang der Karten vor:</span><span class="sxs-lookup"><span data-stu-id="88a88-262">Next, do the same change with the Rank of the cards:</span></span>

[!CODE-csharp[Rank enum](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet3)]

<span data-ttu-id="88a88-263">Ändern Sie auch die Methode, die den Rang generiert:</span><span class="sxs-lookup"><span data-stu-id="88a88-263">And the method that generates them:</span></span>

[!CODE-csharp[Rank IEnumerable](../../../samples/csharp/getting-started/console-linq/Program.cs?name=snippet5)]

<span data-ttu-id="88a88-264">Und um das Ganze abzuschließen, erstellen wir einen Typ zur Darstellung der Karte, statt einen anonymen Typ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="88a88-264">As one final cleanup, let's make a type to represent the card, instead of relying on an anonymous type.</span></span> <span data-ttu-id="88a88-265">Anonyme Typen eignen sich hervorragend für einfache lokale Typen, aber im vorliegenden Beispiel ist die Spielkarte eines der wichtigsten Konzepte.</span><span class="sxs-lookup"><span data-stu-id="88a88-265">Anonymous types are great for lightweight, local types, but in this example, the playing card is one of the main concepts.</span></span> <span data-ttu-id="88a88-266">Daher sollte sie einen konkreten Typ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="88a88-266">It should be a concrete type.</span></span>

[!CODE-csharp[PlayingCard](../../../samples/csharp/getting-started/console-linq/playingcard.cs?name=snippet1)]

<span data-ttu-id="88a88-267">Dieser Typ verwendet *automatisch implementierte, schreibgeschützte Eigenschaften*, die im Konstruktor festgelegt werden und danach nicht mehr geändert werden können.</span><span class="sxs-lookup"><span data-stu-id="88a88-267">This type uses *auto-implemented read-only properties* which are set in the constructor, and then cannot be modified.</span></span> <span data-ttu-id="88a88-268">Er verwendet auch die neue Funktion der *Zeichenfolgeninterpolation*, mit der sich die Zeichenfolgenausgabe einfacher formatieren lässt.</span><span class="sxs-lookup"><span data-stu-id="88a88-268">It also makes use of the new *string interpolation* feature that makes it easier to format string output.</span></span>

<span data-ttu-id="88a88-269">Aktualisieren Sie die Abfrage zum Generieren des anfänglichen Kartenstapels so, dass der neue Typ verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="88a88-269">Update the query that generates the starting deck to use the new type:</span></span>

```csharp
var startingDeck = (from s in Suits().LogQuery("Suit Generation")
                    from r in Ranks().LogQuery("Value Generation")
                    select new PlayingCard(s, r))
                    .LogQuery("Starting Deck")
                    .ToArray();
```

<span data-ttu-id="88a88-270">Kompilieren Sie den Code, und führen Sie ihn erneut aus.</span><span class="sxs-lookup"><span data-stu-id="88a88-270">Compile and run again.</span></span> <span data-ttu-id="88a88-271">Die Ausgabe ist etwas sauberer, und der Code ist klarer und kann einfacher erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="88a88-271">The output is a little cleaner, and the code is a bit more clear and can be extended more easily.</span></span>

## <a name="conclusion"></a><span data-ttu-id="88a88-272">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="88a88-272">Conclusion</span></span>

<span data-ttu-id="88a88-273">In diesem Beispiel wurden einige der in LINQ verwendeten Methoden veranschaulicht sowie das Erstellen von eigenen Methoden, die einfach mit für LINQ aktiviertem Code verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="88a88-273">This sample showed you some of the methods used in LINQ, how to create your own methods that will be easily used with LINQ enabled code.</span></span> <span data-ttu-id="88a88-274">Das Beispiel hat auch die Unterschiede zwischen verzögerter und strikter Auswertung aufgezeigt und erläutert, wie sich die Entscheidung für die eine oder andere Variante auf die Leistung auswirken kann.</span><span class="sxs-lookup"><span data-stu-id="88a88-274">It also showed you the differences between lazy and eager evaluation, and the affect that decision can have on performance.</span></span>

<span data-ttu-id="88a88-275">Sie haben etwas über die Techniken von Zauberkünstlern erfahren.</span><span class="sxs-lookup"><span data-stu-id="88a88-275">You learned a bit about one magician's technique.</span></span> <span data-ttu-id="88a88-276">Zauberer verwenden den Faro-Shuffle, weil sie damit genau steuern können, wann sich welche Karte wo im Stapel befindet.</span><span class="sxs-lookup"><span data-stu-id="88a88-276">Magicians use the faro shuffle because they can control where every card moves in the deck.</span></span> <span data-ttu-id="88a88-277">Bei manchen Tricks bittet der Zauberer einen Zuschauer, eine Karte ganz nach oben auf den Stapel zu legen. Dann mischt der Zauberer die Karten einige Male und weiß genau, wo die Karte ist.</span><span class="sxs-lookup"><span data-stu-id="88a88-277">In some tricks, the magician has an audience member place a card on top of the deck, and shuffles a few times, knowing where that card goes.</span></span> <span data-ttu-id="88a88-278">Für andere Tricks muss der Kartenstapel auf eine ganz bestimmte Art sortiert sein.</span><span class="sxs-lookup"><span data-stu-id="88a88-278">Other illusions require the deck set a certain way.</span></span> <span data-ttu-id="88a88-279">Der Zauberer bereitet den Stapel vor dem Trick vor.</span><span class="sxs-lookup"><span data-stu-id="88a88-279">A magician will set the deck prior to performing the trick.</span></span> <span data-ttu-id="88a88-280">Dann mischt er den Stapel 5-mal nach innen.</span><span class="sxs-lookup"><span data-stu-id="88a88-280">Then she will shuffle the deck 5 times using an inner shuffle.</span></span> <span data-ttu-id="88a88-281">Auf der Bühne zeigt er den Zuschauern dann einen Kartenstapel, der zufällig gemischt aussieht, mischt ihn noch 3-mal und erzielt so genau die gewünschte Kartenreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="88a88-281">On stage, she can show what looks like a random deck, shuffle it 3 more times, and have the deck set exactly how she wants.</span></span>
