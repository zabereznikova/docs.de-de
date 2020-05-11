---
title: Zeichenfolgeninterpolation – C#-Tutorial
description: Dieses Tutorial erläutert, wie Sie mit dem Zeichenfolgeninterpolations-Feature in C# formatierte Ausdrucksergebnisse in eine größere Zeichenfolge einfügen.
ms.date: 10/23/2018
ms.openlocfilehash: d1b78670361e8b333499d12b68c0364ad9e40a85
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796053"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a><span data-ttu-id="fc04c-103">Erstellen formatierter Zeichenfolgen mit der Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="fc04c-103">Use string interpolation to construct formatted strings</span></span>

<span data-ttu-id="fc04c-104">Dieses Tutorial erläutert, wie Sie die [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md) in C# verwenden, um Werte in eine einzelne Ergebniszeichenfolge einzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-104">This tutorial teaches you how to use C# [string interpolation](../../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="fc04c-105">Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="fc04c-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="fc04c-106">Dieses Tutorial enthält einige Lektionen, in denen Ihnen gezeigt wird, wie Werte in eine Zeichenfolge eingefügt und auf verschiedene Weisen formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc04c-106">The tutorial contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="fc04c-107">Für dieses Tutorial wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="fc04c-107">This tutorial expects that you have a machine you can use for development.</span></span> <span data-ttu-id="fc04c-108">Im .NET-Tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) (Hallo Welt in zehn Minuten) finden Sie eine Anleitung zum Einrichten Ihrer lokalen Entwicklungsumgebung unter Windows, Linux oder macOS.</span><span class="sxs-lookup"><span data-stu-id="fc04c-108">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on Windows, Linux, or macOS.</span></span> <span data-ttu-id="fc04c-109">Sie können auch die [interaktive Version](interpolated-strings.yml) dieses Tutorials in Ihrem Browser durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="fc04c-109">You can also complete the [interactive version](interpolated-strings.yml) of this tutorial in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="fc04c-110">Erstellen einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fc04c-110">Create an interpolated string</span></span>

<span data-ttu-id="fc04c-111">Erstellen Sie ein Verzeichnis namens *interpolated*.</span><span class="sxs-lookup"><span data-stu-id="fc04c-111">Create a directory named *interpolated*.</span></span> <span data-ttu-id="fc04c-112">Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie folgenden Befehl in einem Konsolenfenster aus:</span><span class="sxs-lookup"><span data-stu-id="fc04c-112">Make it the current directory and run the following command from a console window:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="fc04c-113">Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="fc04c-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="fc04c-114">Öffnen Sie *Program.cs* in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code, in dem Sie `<name>` durch Ihren Namen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="fc04c-114">Open *Program.cs* in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="fc04c-115">Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="fc04c-116">Wenn Sie das Programm ausführen, wird eine einzelne Zeichenfolge angezeigt, die Ihren Namen in der Begrüßung enthält.</span><span class="sxs-lookup"><span data-stu-id="fc04c-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="fc04c-117">Die im <xref:System.Console.WriteLine%2A>-Methodenaufruf enthaltene Zeichenfolge ist ein *interpolierter Zeichenfolgenausdruck*.</span><span class="sxs-lookup"><span data-stu-id="fc04c-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string expression*.</span></span> <span data-ttu-id="fc04c-118">Dabei handelt es sich um eine Vorlage, durch die Sie eine einzelne Zeichenfolge (als *Ergebniszeichenfolge* bezeichnet) aus einer Zeichenfolge erstellen können, die eingebetteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="fc04c-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="fc04c-119">Interpolierte Zeichenfolgen sind besonders nützlich für das Einfügen von Werten in eine Zeichenfolge oder zum Verketten (bzw. Verknüpfen) von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="fc04c-120">Dieses einfache Beispiel enthält die zwei Elemente, über die jede interpolierte Zeichenfolge verfügen muss:</span><span class="sxs-lookup"><span data-stu-id="fc04c-120">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="fc04c-121">Ein Zeichenfolgenliteral, das ein `$`-Zeichen vor dem öffnenden Anführungszeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="fc04c-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="fc04c-122">Zwischen dem `$`-Symbol und dem Anführungszeichen darf kein Leerraum vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="fc04c-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="fc04c-123">(Wenn Sie testen möchten, was andernfalls geschieht, fügen Sie einen Leerraum nach dem `$`-Zeichen ein, speichern Sie die Datei, und führen Sie das Programm erneut aus, indem Sie `dotnet run` im Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="fc04c-124">Der C#-Compiler zeigt dann die Fehlermeldung „Fehler CS1056: Unerwartetes Zeichen '$'“ an.)</span><span class="sxs-lookup"><span data-stu-id="fc04c-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="fc04c-125">Mindestens ein *Interpolationsausdruck*.</span><span class="sxs-lookup"><span data-stu-id="fc04c-125">One or more *interpolation expressions*.</span></span> <span data-ttu-id="fc04c-126">Ein Interpolationsausdruck wird durch eine öffnende und eine schließende geschweifte Klammer (`{` und `}`) angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-126">An interpolation expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="fc04c-127">Sie können jeden C#-Ausdruck in die Klammern einfügen, der einen Wert (einschließlich `null`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="fc04c-128">Im Folgenden finden Sie weitere Beispiele für die Zeichenfolgeninterpolation mit einigen anderen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-128">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="fc04c-129">Einschließen verschiedener Datentypen</span><span class="sxs-lookup"><span data-stu-id="fc04c-129">Include different data types</span></span>

<span data-ttu-id="fc04c-130">Im vorherigen Abschnitt haben Sie die Zeichenfolgeninterpolation verwendet, um eine Zeichenfolge in eine andere einzufügen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-130">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="fc04c-131">Das Ergebnis eines Interpolationsausdrucks kann jedoch jeden Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-131">The result of an interpolation expression can be of any data type, though.</span></span> <span data-ttu-id="fc04c-132">Im Folgenden werden mehrere Datentypen in eine interpolierte Zeichenfolge einbezogen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-132">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="fc04c-133">Im folgenden Beispiel wird zunächst ein [Klassen](../../programming-guide/classes-and-structs/classes.md)-Datentyp `Vegetable` definiert, der über die [Eigenschaft](../../properties.md)`Name` und die [Methode](../../methods.md) `ToString` verfügt. Diese Methode [überschreibt](../../language-reference/keywords/override.md) das Verhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="fc04c-133">In the following example, we first define a [class](../../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has a `Name` [property](../../properties.md) and a `ToString` [method](../../methods.md), which [overrides](../../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fc04c-134">Der [`public`-Zugriffsmodifizierer](../../language-reference/keywords/public.md) stellt diese Methode jedem Clientcode zur Verfügung, um die Zeichenfolgendarstellung einer `Vegetable`-Instanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-134">The [`public` access modifier](../../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="fc04c-135">Im Beispiel gibt die Methode `Vegetable.ToString` den Wert der Eigenschaft `Name` zurück, die beim [Konstruktor](../../programming-guide/classes-and-structs/constructors.md) `Vegetable` initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="fc04c-135">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="fc04c-136">Dann wird eine Instanz der Klasse `Vegetable` mit dem Namen `item` mithilfe des [`new`Operators](../../language-reference/operators/new-operator.md) erstellt und ein Name für den Konstruktor `Vegetable` angegeben:</span><span class="sxs-lookup"><span data-stu-id="fc04c-136">Then we create an instance of the `Vegetable` class named `item` by using the [`new` operator](../../language-reference/operators/new-operator.md) and providing a name for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="fc04c-137">Zum Schluss wird die Variable `item` in eine interpolierte Zeichenfolge einbezogen, die auch einen <xref:System.DateTime>-Wert, <xref:System.Decimal>-Wert und einen [Enumerationswert](../../language-reference/builtin-types/enum.md) `Unit` enthält.</span><span class="sxs-lookup"><span data-stu-id="fc04c-137">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../../language-reference/builtin-types/enum.md) value.</span></span> <span data-ttu-id="fc04c-138">Ersetzen Sie sämtlichen C#-Code in Ihrem Editor durch folgenden Code, und verwenden Sie dann den `dotnet run`-Befehl, um diesen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fc04c-138">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

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

<span data-ttu-id="fc04c-139">Beachten Sie, dass der Interpolationsausdruck `item` der interpolierten Zeichenfolge in der Ergebniszeichenfolge zu dem Text „eggplant“ aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="fc04c-139">Note that the interpolation expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="fc04c-140">Dies liegt daran, dass der Ausdruckergebnistyp keine Zeichenfolge ist. Daher wird das Ergebnis auf folgende Weise zu einer Zeichenfolge aufgelöst:</span><span class="sxs-lookup"><span data-stu-id="fc04c-140">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="fc04c-141">Wenn der Interpolationsausdruck zu `null` ausgewertet wird, wird eine leere Zeichenfolge („“ oder <xref:System.String.Empty?displayProperty=nameWithType>) verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc04c-141">If the interpolation expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="fc04c-142">Wenn der Interpolationsausdruck nicht zu `null` ausgewertet wird, wird in der Regel die Methode `ToString` des Ergebnistyps aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-142">If the interpolation expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="fc04c-143">Sie können dies testen, indem Sie die Implementierung der Methode `Vegetable.ToString` aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fc04c-143">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="fc04c-144">Sie müssen die Methode `ToString` nicht einmal implementieren, da jeder Typ auf die eine oder andere Art über eine Implementierung dieser Methode verfügt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-144">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="fc04c-145">Sie können dies testen, indem Sie die Definition der Methode `Vegetable.ToString` im Beispiel auskommentieren (fügen Sie hierzu davor ein Kommentarsymbol `//` ein).</span><span class="sxs-lookup"><span data-stu-id="fc04c-145">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="fc04c-146">In der Ausgabe wird die Zeichenfolge „eggplant“ durch den vollqualifizierten Typnamen ersetzt (in diesem Beispiel „Vegetable“). Dies stellt das Standardverhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode dar.</span><span class="sxs-lookup"><span data-stu-id="fc04c-146">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fc04c-147">Das Standardverhalten der Methode `ToString` für einen Enumerationswert besteht darin, die Zeichenfolgendarstellung eines Werts zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-147">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="fc04c-148">Bei der Ausgabe dieses Beispielcodes ist das Datum zu genau angegeben (der Preis von Auberginen ändert sich nicht sekündlich), und der Wert der Variablen „price“ gibt keine Währungsinformation an.</span><span class="sxs-lookup"><span data-stu-id="fc04c-148">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="fc04c-149">Im nächsten Abschnitt erfahren Sie, wie Sie diese Probleme beheben, indem Sie das Format der Zeichenfolgendarstellung der Ergebnisse des Ausdrucks steuern.</span><span class="sxs-lookup"><span data-stu-id="fc04c-149">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolation-expressions"></a><span data-ttu-id="fc04c-150">Steuern der Formatierung von Interpolationsausdrücken</span><span class="sxs-lookup"><span data-stu-id="fc04c-150">Control the formatting of interpolation expressions</span></span>

<span data-ttu-id="fc04c-151">Im vorherigen Abschnitt wurden zwei fehlerhaft formatierte Zeichenfolgen in die Ergebniszeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-151">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="fc04c-152">Bei einer davon handelte es sich um einen Datums- und Uhrzeitwert, bei dem nur das Datum relevant war.</span><span class="sxs-lookup"><span data-stu-id="fc04c-152">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="fc04c-153">Bei der zweiten handelte es sich um einen Preis, bei dem keine Währungseinheit angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fc04c-153">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="fc04c-154">Beide Probleme sind einfach zu beheben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-154">Both issues are easy to address.</span></span> <span data-ttu-id="fc04c-155">Mithilfe der Zeichenfolgeninterpolation können Sie *Formatzeichenfolgen* angeben, die die Formatierung bestimmter Typen steuern.</span><span class="sxs-lookup"><span data-stu-id="fc04c-155">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="fc04c-156">Ändern Sie den Aufruf von `Console.WriteLine` im vorherigen Beispiel, damit die Formatzeichenfolgen für die Ausdrücke „date“ und „price,“ wie in der folgenden Zeile dargestellt, enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="fc04c-156">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="fc04c-157">Sie können eine Formatzeichenfolge angeben, indem Sie dem Interpolationsausdruck einen Doppelpunkt („:“) und die Formatzeichenfolge anfügen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-157">You specify a format string by following the interpolation expression with a colon (":") and the format string.</span></span> <span data-ttu-id="fc04c-158">Bei „d“ handelt es sich um eine [Zeichenfolge für das Standardformat für Datum und Uhrzeit](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), die das kurze Datumsformat darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-158">"d" is a [standard date and time format string](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="fc04c-159">Bei „C2“ handelt es sich um eine [Zeichenfolge für das numerische Standardformat](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), die eine Zahl als Währungswert mit zwei Ziffern nach dem Dezimaltrennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-159">"C2" is a  [standard numeric format string](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="fc04c-160">Einige Typen in den .NET-Bibliotheken unterstützen einen vordefinierten Satz von Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-160">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="fc04c-161">Darin sind alle numerischen Typen sowie alle Datums- und Uhrzeittypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fc04c-161">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="fc04c-162">Eine vollständige Liste der Typen, die Formatzeichenfolgen unterstützen, finden Sie im Artikel [Formatieren von Typen in .NET](../../../standard/base-types/formatting-types.md) unter [Format Strings and .NET Class Library Types (Formatzeichenfolgen und .NET-Klassenbibliothekstypen)](../../../standard/base-types/formatting-types.md#format-strings-and-net-types).</span><span class="sxs-lookup"><span data-stu-id="fc04c-162">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../../standard/base-types/formatting-types.md#format-strings-and-net-types) in the [Formatting Types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="fc04c-163">Versuchen Sie, die Formatzeichenfolgen in Ihrem Text-Editor zu ändern, und führen Sie das Programm jedes Mal erneut aus, wenn Sie eine Änderung vornehmen. So können Sie feststellen, wie sich die Änderungen auf die Formatierung des Datums, der Uhrzeit und des numerischen Werts auswirken.</span><span class="sxs-lookup"><span data-stu-id="fc04c-163">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="fc04c-164">Ändern Sie „d“ in `{date:d}` in „t“ (um das kurze Uhrzeitformat anzuzeigen) sowie in „y“ (um das Jahr und den Monat anzuzeigen) und in „yyyy“ (um das Jahr als vierstellige Zahl anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="fc04c-164">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="fc04c-165">Ändern Sie „C2“ in `{price:C2}` in „e“ (für die Exponentialschreibweise) und in „F3“ (für einen numerischen Wert mit drei Ziffern nach dem Dezimaltrennzeichen).</span><span class="sxs-lookup"><span data-stu-id="fc04c-165">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="fc04c-166">Sie können zusätzlich zum Steuern der Formatierung auch die Feldbreite und die Ausrichtung der formatierten Zeichenfolgen steuern, die in der Ergebniszeichenfolge enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fc04c-166">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="fc04c-167">Im nächsten Abschnitt erfahren Sie mehr zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="fc04c-167">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolation-expressions"></a><span data-ttu-id="fc04c-168">Steuern der Feldbreite und der Ausrichtung von Interpolationsausdrücken</span><span class="sxs-lookup"><span data-stu-id="fc04c-168">Control the field width and alignment of interpolation expressions</span></span>

<span data-ttu-id="fc04c-169">Wenn das Ergebnis eines Interpolationsausdrucks als Zeichenfolge formatiert wird, wird diese Zeichenfolge normalerweise in eine Ergebniszeichenfolge ohne führende oder nachgestellte Leerzeichen einbezogen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-169">Ordinarily, when the result of an interpolation expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="fc04c-170">Die Feldbreite und Ausrichtung des Texts steuern zu können, ist insbesondere bei der Arbeit mit Daten hilfreich, um eine besser lesbare Ausgabe zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-170">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="fc04c-171">Ersetzen Sie zur Veranschaulichung den gesamten Code in Ihrem Text-Editor durch folgenden Code, und geben Sie dann `dotnet run` ein, um das Programm auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fc04c-171">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

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

<span data-ttu-id="fc04c-172">Die Namen der Autoren sind linksbündig ausgerichtet, während deren Werke rechtsbündig ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="fc04c-172">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="fc04c-173">Sie können die Ausrichtung festlegen, indem Sie einem Interpolationsausdruck ein Komma („,“) anfügen und die *minimale* Feldbreite angeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-173">You specify the alignment by adding a comma (",") after an interpolation expression and designating the *minimum* field width.</span></span> <span data-ttu-id="fc04c-174">Wenn der angegebene Wert eine positive Zahl ist, wird das Feld rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="fc04c-174">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="fc04c-175">Wenn er eine negative Zahl ist, wird das Feld linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="fc04c-175">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="fc04c-176">Versuchen Sie die negativen Vorzeichen aus dem Code `{"Author",-25}` und `{title.Key,-25}` wie im folgenden Code zu entfernen, und führen Sie das Beispiel erneut aus:</span><span class="sxs-lookup"><span data-stu-id="fc04c-176">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="fc04c-177">Diesmal sind die Informationen zum Autor rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="fc04c-177">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="fc04c-178">Sie können einen Ausrichtungsspezifizierer und eine Formatzeichenfolge für einen einzigen Interpolationsausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="fc04c-178">You can combine an alignment specifier and a format string for a single interpolation expression.</span></span> <span data-ttu-id="fc04c-179">Geben Sie dazu zunächst die Ausrichtung gefolgt von einem Doppelpunkt und der Formatzeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="fc04c-179">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="fc04c-180">Ersetzen Sie sämtlichen Code innerhalb der `Main`-Methode durch folgenden Code, der drei formatierte Zeichenfolgen mit definierten Feldbreiten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="fc04c-180">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="fc04c-181">Führen Sie das Programm anschließend aus, indem Sie den Befehl `dotnet run` eingeben.</span><span class="sxs-lookup"><span data-stu-id="fc04c-181">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="fc04c-182">Die Ausgabe sieht in etwa folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="fc04c-182">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="fc04c-183">Sie haben da Tutorial für die Zeichenfolgeninterpolation abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fc04c-183">You've completed the string interpolation tutorial.</span></span>

<span data-ttu-id="fc04c-184">Weitere Informationen finden Sie im Artikel zur [Zeichenfolgeninterpolation](../../language-reference/tokens/interpolated.md) und dem Tutorial [Zeichenfolgeninterpolation in C#](../string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="fc04c-184">For more information, see the [String interpolation](../../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../string-interpolation.md) tutorial.</span></span>
