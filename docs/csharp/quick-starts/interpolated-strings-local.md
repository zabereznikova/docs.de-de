---
title: 'Tutorial „Zeichenfolgeninterpolation“: Lokale C#-Schnellstarts'
description: In diesem Schnellstart wird erläutert, wie Sie das Zeichenfolgeninterpolationsfeature in C# verwenden, um formatierte Ausdrucksergebnisse in einer größeren Zeichenfolge zu enthalten.
author: rpetrusha
ms.author: ronpet
ms.date: 04/14/2018
ms.custom: mvc
ms.openlocfilehash: da111790ebbc299df16297650347045b9395a90f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46580693"
---
# <a name="string-interpolation"></a><span data-ttu-id="001b1-103">Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="001b1-103">String interpolation</span></span>

<span data-ttu-id="001b1-104">In diesem Schnellstart wird erläutert, wie Sie die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) in C# verwenden können, um Werte in eine einzelne Ergebniszeichenfolge einzufügen.</span><span class="sxs-lookup"><span data-stu-id="001b1-104">This quickstart teaches you how to use C# [string interpolation](../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="001b1-105">Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="001b1-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="001b1-106">In diesem Schnellstart sind einige Lektionen enthalten, in denen Ihnen gezeigt wird, wie Werte in eine Zeichenfolge eingefügt und auf verschiedene Weisen formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="001b1-106">The quickstart contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="001b1-107">Für diesen Schnellstart wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="001b1-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="001b1-108">Das .NET-Thema [Erste Schritte in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-PC.</span><span class="sxs-lookup"><span data-stu-id="001b1-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="001b1-109">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie in der [Einführung zu lokalen Schnellstarts](local-environment.md), die Links mit weiteren Einzelheiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="001b1-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> <span data-ttu-id="001b1-110">Sie können auch die [interaktive Version](interpolated-strings.yml) dieses Schnellstarts in Ihrem Browser durchführen.</span><span class="sxs-lookup"><span data-stu-id="001b1-110">You also can complete the [interactive version](interpolated-strings.yml) of this quickstart in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="001b1-111">Erstellen einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="001b1-111">Create an interpolated string</span></span>

<span data-ttu-id="001b1-112">Erstellen Sie ein Verzeichnis namens **interpolated**.</span><span class="sxs-lookup"><span data-stu-id="001b1-112">Create a directory named **interpolated**.</span></span> <span data-ttu-id="001b1-113">Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie folgenden Befehl in einem Konsolenfenster aus:</span><span class="sxs-lookup"><span data-stu-id="001b1-113">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="001b1-114">Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="001b1-114">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="001b1-115">Öffnen Sie **Program.cs** in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code, in dem Sie `<name>` durch Ihren Namen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="001b1-115">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="001b1-116">Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-116">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="001b1-117">Wenn Sie das Programm ausführen, wird eine einzelne Zeichenfolge angezeigt, die Ihren Namen in der Begrüßung enthält.</span><span class="sxs-lookup"><span data-stu-id="001b1-117">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="001b1-118">Die Zeichenfolge, die in den <xref:System.Console.WriteLine%2A>-Methodenaufruf eingefügt wird, ist eine *interpolierte Zeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="001b1-118">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="001b1-119">Dabei handelt es sich um eine Vorlage, durch die Sie eine einzelne Zeichenfolge (als *Ergebniszeichenfolge* bezeichnet) aus einer Zeichenfolge erstellen können, die eingebetteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="001b1-119">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="001b1-120">Interpolierte Zeichenfolgen sind besonders nützlich für das Einfügen von Werten in eine Zeichenfolge oder zum Verketten (bzw. Verknüpfen) von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="001b1-120">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="001b1-121">Dieses einfache Beispiel enthält die zwei Elemente, über die jede interpolierte Zeichenfolge verfügen muss:</span><span class="sxs-lookup"><span data-stu-id="001b1-121">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="001b1-122">Ein Zeichenfolgenliteral, das ein `$`-Zeichen vor dem öffnenden Anführungszeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="001b1-122">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="001b1-123">Zwischen dem `$`-Symbol und dem Anführungszeichen darf kein Leerraum vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="001b1-123">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="001b1-124">(Wenn Sie testen möchten, was andernfalls geschieht, fügen Sie einen Leerraum nach dem `$`-Zeichen ein, speichern Sie die Datei, und führen Sie das Programm erneut aus, indem Sie `dotnet run` im Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-124">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="001b1-125">Der C#-Compiler zeigt dann die Fehlermeldung „Fehler CS1056: Unerwartetes Zeichen ‚$‘.“ an.)</span><span class="sxs-lookup"><span data-stu-id="001b1-125">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="001b1-126">Mindestens ein *interpolierter Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="001b1-126">One or more *interpolated expressions*.</span></span> <span data-ttu-id="001b1-127">Ein interpolierter Ausdruck wird durch eine öffnende und eine schließende Klammer (`{` und `}`) angegeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-127">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="001b1-128">Sie können jeden C#-Ausdruck in die Klammern einfügen, der einen Wert (einschließlich `null`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="001b1-128">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="001b1-129">Im Folgenden finden Sie weitere Beispiele für die Zeichenfolgeninterpolation mit einigen anderen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="001b1-129">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="001b1-130">Einschließen verschiedener Datentypen</span><span class="sxs-lookup"><span data-stu-id="001b1-130">Include different data types</span></span>

<span data-ttu-id="001b1-131">Im vorherigen Abschnitt haben Sie die Zeichenfolgeninterpolation verwendet, um eine Zeichenfolge in eine andere einzufügen.</span><span class="sxs-lookup"><span data-stu-id="001b1-131">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="001b1-132">Das Ergebnis eines interpolierten Ausdrucks kann jedoch jeden Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="001b1-132">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="001b1-133">Im Folgenden werden mehrere Datentypen in eine interpolierte Zeichenfolge einbezogen.</span><span class="sxs-lookup"><span data-stu-id="001b1-133">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="001b1-134">Im folgenden Beispiel wird zunächst ein [Klassen](../programming-guide/classes-and-structs/classes.md)-Datentyp `Vegetable` definiert, der über die [Eigenschaft](../properties.md) `Name` und die [Methode](../methods.md) `ToString` verfügt. Diese Methode [setzt das Verhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode außer Kraft](../language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="001b1-134">In the following example, first, we define a [class](../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has the `Name` [property](../properties.md) and the `ToString` [method](../methods.md), which [overrides](../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="001b1-135">Der [`public`-Zugriffsmodifizierer](../language-reference/keywords/public.md) stellt diese Methode jedem Clientcode zur Verfügung, um die Zeichenfolgendarstellung einer `Vegetable`-Instanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="001b1-135">The [`public` access modifier](../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="001b1-136">Im Beispiel gibt die Methode `Vegetable.ToString` den Wert der Eigenschaft `Name` zurück, die beim [Konstruktor](../programming-guide/classes-and-structs/constructors.md) `Vegetable` initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="001b1-136">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="001b1-137">Dann wird eine Instanz der Klasse `Vegetable` mithilfe des [Schlüsselworts `new`](../language-reference/keywords/new-operator.md) erstellt und ein Name-Parameter für den Konstruktor `Vegetable` angegeben:</span><span class="sxs-lookup"><span data-stu-id="001b1-137">Then we create an instance of the `Vegetable` class by using [`new` keyword](../language-reference/keywords/new-operator.md) and providing a name parameter for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="001b1-138">Zum Schluss wird die Variable `item` in eine interpolierte Zeichenfolge einbezogen, die auch einen <xref:System.DateTime>-Wert, <xref:System.Decimal>-Wert und einen [Enumerationswert](../programming-guide/enumeration-types.md) `Unit` enthält.</span><span class="sxs-lookup"><span data-stu-id="001b1-138">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="001b1-139">Ersetzen Sie sämtlichen C#-Code in Ihrem Editor durch folgenden Code, und verwenden Sie dann den `dotnet run`-Befehl, um diesen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="001b1-139">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

<span data-ttu-id="001b1-140">Beachten Sie, dass der interpolierte Ausdruck `item` in der interpolierten Zeichenfolge zu dem Text „eggplant“ in der Ergebniszeichenfolge aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="001b1-140">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="001b1-141">Dies liegt daran, dass der Ausdruckergebnistyp keine Zeichenfolge ist. Daher wird das Ergebnis auf folgende Weise zu einer Zeichenfolge aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="001b1-141">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="001b1-142">Wenn der interpolierte Ausdruck `null` ergibt, wird eine leere Zeichenfolge („“ oder <xref:System.String.Empty?displayProperty=nameWithType>) verwendet.</span><span class="sxs-lookup"><span data-stu-id="001b1-142">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="001b1-143">Wenn der interpolierte Ausdruck nicht `null` ergibt, wird in der Regel die Methode `ToString` des Ergebnistyps aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="001b1-143">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="001b1-144">Sie können dies testen, indem Sie die Implementierung der Methode `Vegetable.ToString` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="001b1-144">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="001b1-145">Sie müssen die Methode `ToString` nicht einmal implementieren, da jeder Typ auf die eine oder andere Art über eine Implementierung dieser Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="001b1-145">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="001b1-146">Sie können dies testen, indem Sie die Definition der Methode `Vegetable.ToString` im Beispiel auskommentieren (fügen Sie hierzu davor ein Kommentarsymbol `//` ein).</span><span class="sxs-lookup"><span data-stu-id="001b1-146">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="001b1-147">In der Ausgabe wird die Zeichenfolge „eggplant“ durch den vollqualifizierten Typnamen ersetzt (in diesem Beispiel „Vegetable“). Dies stellt das Standardverhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode dar.</span><span class="sxs-lookup"><span data-stu-id="001b1-147">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="001b1-148">Das Standardverhalten der Methode `ToString` für einen Enumerationswert besteht darin, die Zeichenfolgendarstellung eines Werts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-148">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="001b1-149">Bei der Ausgabe dieses Beispielcodes ist das Datum zu genau angegeben (der Preis von Auberginen ändert sich nicht sekündlich), und der Wert der Variablen „price“ gibt keine Währungsinformation an.</span><span class="sxs-lookup"><span data-stu-id="001b1-149">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="001b1-150">Im nächsten Abschnitt erfahren Sie, wie Sie diese Probleme beheben, indem Sie das Format der Zeichenfolgendarstellung der Ergebnisse des Ausdrucks steuern.</span><span class="sxs-lookup"><span data-stu-id="001b1-150">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="001b1-151">Steuern der Formatierung von interpolierten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="001b1-151">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="001b1-152">Im vorherigen Abschnitt wurden zwei fehlerhaft formatierte Zeichenfolgen in die Ergebniszeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="001b1-152">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="001b1-153">Bei einer davon handelte es sich um einen Datums- und Uhrzeitwert, bei dem nur das Datum relevant war.</span><span class="sxs-lookup"><span data-stu-id="001b1-153">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="001b1-154">Bei der zweiten handelte es sich um einen Preis, bei dem keine Währungseinheit angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="001b1-154">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="001b1-155">Beide Probleme sind einfach zu beheben.</span><span class="sxs-lookup"><span data-stu-id="001b1-155">Both issues are easy to address.</span></span> <span data-ttu-id="001b1-156">Mithilfe der Zeichenfolgeninterpolation können Sie *Formatzeichenfolgen* angeben, die die Formatierung bestimmter Typen steuern.</span><span class="sxs-lookup"><span data-stu-id="001b1-156">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="001b1-157">Ändern Sie den Aufruf von `Console.WriteLine` im vorherigen Beispiel, damit die Formatzeichenfolgen für die Ausdrücke „date“ und „price,“ wie in der folgenden Zeile dargestellt, enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="001b1-157">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="001b1-158">Sie können eine Formatzeichenfolge angeben, indem Sie dem interpolierten Ausdruck einen Doppelpunkt („:“) und die Formatzeichenfolge anfügen.</span><span class="sxs-lookup"><span data-stu-id="001b1-158">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="001b1-159">Bei „d“ handelt es sich um eine [Zeichenfolge für das Standardformat für Datum und Uhrzeit](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), die das kurze Datumsformat darstellt.</span><span class="sxs-lookup"><span data-stu-id="001b1-159">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="001b1-160">Bei „C2“ handelt es sich um eine [Zeichenfolge für das numerische Standardformat](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), die eine Zahl als Währungswert mit zwei Ziffern nach dem Dezimaltrennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="001b1-160">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="001b1-161">Einige Typen in den .NET-Bibliotheken unterstützen einen vordefinierten Satz von Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="001b1-161">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="001b1-162">Darin sind alle numerischen Typen sowie alle Datums- und Uhrzeittypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="001b1-162">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="001b1-163">Eine vollständige Liste der Typen, die Formatzeichenfolgen unterstützen, finden Sie im Artikel [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) unter [Format Strings and .NET Class Library Types (Formatzeichenfolgen und .NET-Klassenbibliothekstypen)](../../standard/base-types/formatting-types.md#stringRef).</span><span class="sxs-lookup"><span data-stu-id="001b1-163">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="001b1-164">Versuchen Sie, die Formatzeichenfolgen in Ihrem Text-Editor zu ändern, und führen Sie das Programm jedes Mal erneut aus, wenn Sie eine Änderung vornehmen. So können Sie feststellen, wie sich die Änderungen auf die Formatierung des Datums, der Uhrzeit und des numerischen Werts auswirken.</span><span class="sxs-lookup"><span data-stu-id="001b1-164">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="001b1-165">Ändern Sie „d“ in `{date:d}` in „t“ (um das kurze Uhrzeitformat anzuzeigen) sowie in „y“ (um das Jahr und den Monat anzuzeigen) und in „yyyy“ (um das Jahr als vierstellige Zahl anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="001b1-165">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="001b1-166">Ändern Sie „C2“ in `{price:C2}` in „e“ (für die Exponentialschreibweise) und in „F3“ (für einen numerischen Wert mit drei Ziffern nach dem Dezimaltrennzeichen).</span><span class="sxs-lookup"><span data-stu-id="001b1-166">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="001b1-167">Sie können zusätzlich zum Steuern der Formatierung auch die Feldbreite und die Ausrichtung der formatierten Zeichenfolgen steuern, die in der Ergebniszeichenfolge enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="001b1-167">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="001b1-168">Im nächsten Abschnitt erfahren Sie mehr zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="001b1-168">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="001b1-169">Steuern der Feldbreite und der Ausrichtung von interpolierten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="001b1-169">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="001b1-170">Wenn das Ergebnis eines interpolierten Ausdrucks als Zeichenfolge formatiert wird, wird diese Zeichenfolge normalerweise in eine Ergebniszeichenfolge ohne führende oder nachgestellte Leerzeichen einbezogen.</span><span class="sxs-lookup"><span data-stu-id="001b1-170">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="001b1-171">Die Feldbreite und Ausrichtung des Texts steuern zu können, ist insbesondere bei der Arbeit mit Daten hilfreich, um eine besser lesbare Ausgabe zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="001b1-171">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="001b1-172">Ersetzen Sie zur Veranschaulichung den gesamten Code in Ihrem Text-Editor durch folgenden Code, und geben Sie dann `dotnet run` ein, um das Programm auszuführen:</span><span class="sxs-lookup"><span data-stu-id="001b1-172">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

<span data-ttu-id="001b1-173">Die Namen der Autoren sind linksbündig ausgerichtet, während deren Werke rechtsbündig ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="001b1-173">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="001b1-174">Sie können die Ausrichtung festlegen, indem Sie einem interpolierten Ausdruck ein Komma („,“) anfügen und die *minimale* Feldbreite angeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-174">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="001b1-175">Wenn der angegebene Wert eine positive Zahl ist, wird das Feld rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="001b1-175">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="001b1-176">Wenn er eine negative Zahl ist, wird das Feld linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="001b1-176">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="001b1-177">Versuchen Sie die negativen Vorzeichen aus dem Code `{"Author",-25}` und `{title.Key,-25}` wie im folgenden Code zu entfernen, und führen Sie das Beispiel erneut aus:</span><span class="sxs-lookup"><span data-stu-id="001b1-177">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="001b1-178">Diesmal sind die Informationen zum Autor rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="001b1-178">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="001b1-179">Sie können einen Ausrichtungsspezifizierer und eine Formatzeichenfolge für einen einzigen interpolierten Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="001b1-179">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="001b1-180">Geben Sie dazu zunächst die Ausrichtung gefolgt von einem Doppelpunkt und der Formatzeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="001b1-180">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="001b1-181">Ersetzen Sie sämtlichen Code innerhalb der `Main`-Methode durch folgenden Code, der drei formatierte Zeichenfolgen mit definierten Feldbreiten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="001b1-181">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="001b1-182">Führen Sie das Programm anschließend aus, indem Sie den Befehl `dotnet run` eingeben.</span><span class="sxs-lookup"><span data-stu-id="001b1-182">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="001b1-183">Die Ausgabe sieht in etwa folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="001b1-183">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="001b1-184">Sie haben den Schnellstart für die Zeichenfolgeninterpolation abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="001b1-184">You've completed the string interpolation quickstart.</span></span>

<span data-ttu-id="001b1-185">Sie können mit dem Schnellstart [Listensammlungen](arrays-and-collections.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="001b1-185">You can continue with the [List collection](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="001b1-186">Weitere Informationen finden Sie im Artikel zur [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) und dem Tutorial [Zeichenfolgeninterpolation in C#](../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="001b1-186">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>
