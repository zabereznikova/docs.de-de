---
title: "Tutorial „Interpolierte Zeichenfolgen“: Lokale C#-Schnellstarts"
description: "In diesem Schnellstart über interpolierte Zeichenfolgen schreiben Sie C#-Code, um das Ergebnis eines Ausdrucks in eine größere Zeichenfolge einzufügen."
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="92494-103">Interpolierte Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="92494-103">Interpolated strings</span></span>

<span data-ttu-id="92494-104">In diesem Schnellstart wird erläutert, wie Sie interpolierte Zeichenfolgen in C# verwenden können, um Werte in eine einzige Ausgabezeichenfolge einzufügen.</span><span class="sxs-lookup"><span data-stu-id="92494-104">This quickstart teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="92494-105">Sie schreiben einen C#-Code und sehen dort die Ergebnisse der Kompilierung und Ausführung Ihres Codes.</span><span class="sxs-lookup"><span data-stu-id="92494-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="92494-106">In diesem Schnellstart sind einige Lektionen enthalten, bei denen Werte in Zeichenfolgen eingefügt und auf verschiedene Arten formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="92494-106">The quickstart contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="92494-107">Für diesen Schnellstart wird vorausgesetzt, dass Sie über einen Computer verfügen, den Sie für die Entwicklung nutzen können.</span><span class="sxs-lookup"><span data-stu-id="92494-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="92494-108">Das .NET-Thema [Erste Schritte in 10 Minuten](https://www.microsoft.com/net/core) umfasst Anweisungen zum Einrichten Ihrer lokalen Entwicklungsumgebung auf einem Mac-, Windows- oder Linux-PC.</span><span class="sxs-lookup"><span data-stu-id="92494-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="92494-109">Einen schnellen Überblick über die Befehle, die Sie verwenden werden, finden Sie in der [Einführung zu lokalen Schnellstarts](local-environment.md), die Links mit weiteren Einzelheiten enthalten.</span><span class="sxs-lookup"><span data-stu-id="92494-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="92494-110">Erstellen einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="92494-110">Create an interpolated string</span></span>

<span data-ttu-id="92494-111">Erstellen Sie ein Verzeichnis namens **interpolated-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="92494-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="92494-112">Legen Sie dieses als das aktuelle Verzeichnis fest, und führen Sie folgenden Befehl in einem Konsolenfenster aus:</span><span class="sxs-lookup"><span data-stu-id="92494-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="92494-113">Dieser Befehl erstellt im aktuellen Verzeichnis eine neue .NET Core-Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="92494-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="92494-114">Öffnen Sie **Program.cs** in Ihrem bevorzugten Editor, und ersetzen Sie die Zeile `Console.WriteLine("Hello World!");` durch den folgenden Code, in dem Sie `<name>` durch Ihren Namen ersetzen:</span><span class="sxs-lookup"><span data-stu-id="92494-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="92494-115">Testen Sie diesen Code, indem Sie `dotnet run` in Ihr Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="92494-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="92494-116">Wenn Sie das Programm ausführen, wird eine einzelne Zeichenfolge angezeigt, die Ihren Namen in der Begrüßung enthält.</span><span class="sxs-lookup"><span data-stu-id="92494-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="92494-117">Die Zeichenfolge, die in den <xref:System.Console.WriteLine%2A>-Methodenaufruf eingefügt wird, ist eine *interpolierte Zeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="92494-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="92494-118">Dabei handelt es sich um eine Vorlage, durch die Sie eine einzelne Zeichenfolge (als *Ergebniszeichenfolge* bezeichnet) aus einer Zeichenfolge erstellen können, die eingebetteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="92494-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="92494-119">Interpolierte Zeichenfolgen sind besonders nützlich für das Einfügen von Werten in eine Zeichenfolge oder zum Verketten (bzw. Verknüpfen) von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="92494-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="92494-120">Dieses einfache Beispiel enthält die zwei Elemente, über die jede interpolierte Zeichenfolge verfügen muss:</span><span class="sxs-lookup"><span data-stu-id="92494-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="92494-121">Ein Zeichenfolgenliteral, das ein `$`-Zeichen vor dem öffnenden Anführungszeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="92494-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="92494-122">Zwischen dem `$`-Symbol und dem Anführungszeichen darf kein Leerraum vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="92494-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="92494-123">(Wenn Sie testen möchten, was andernfalls geschieht, fügen Sie einen Leerraum nach dem `$`-Zeichen ein, speichern Sie die Datei, und führen Sie das Programm erneut aus, indem Sie `dotnet run` im Konsolenfenster eingeben.</span><span class="sxs-lookup"><span data-stu-id="92494-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="92494-124">Der C#-Compiler zeigt dann die Fehlermeldung „Fehler CS1056: Unerwartetes Zeichen ‚$‘.“ an.)</span><span class="sxs-lookup"><span data-stu-id="92494-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="92494-125">Mindestens ein *interpolierter Ausdruck*.</span><span class="sxs-lookup"><span data-stu-id="92494-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="92494-126">Ein interpolierter Ausdruck wird durch eine öffnende und eine schließende Klammer (`{` und `}`) angegeben.</span><span class="sxs-lookup"><span data-stu-id="92494-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="92494-127">Sie können jeden C#-Ausdruck in die Klammern einfügen, der einen Wert (einschließlich `null`) zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="92494-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="92494-128">Im Folgenden finden Sie weitere Beispiele für interpolierte Zeichenfolgen mit einigen anderen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="92494-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="92494-129">Einschließen verschiedener Datentypen</span><span class="sxs-lookup"><span data-stu-id="92494-129">Include different data types</span></span>

<span data-ttu-id="92494-130">Im vorherigen Abschnitt haben Sie eine interpolierte Zeichenfolge verwendet, um eine Zeichenfolge in eine andere einzufügen.</span><span class="sxs-lookup"><span data-stu-id="92494-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="92494-131">Ein interpolierter Zeichenfolgenausdruck kann jedoch jeden Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92494-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="92494-132">Im Folgenden wird eine interpolierte Zeichenfolge dargestellt, die Werte mehrerer Datentypen enthält.</span><span class="sxs-lookup"><span data-stu-id="92494-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="92494-133">Im folgenden Beispiel sind interpolierte Ausdrücke enthalten, die über ein `Vegetable`-Objekt, einen Member der `Unit`-Enumeration, einen <xref:System.DateTime>-Wert und einen <xref:System.Decimal>-Wert verfügen.</span><span class="sxs-lookup"><span data-stu-id="92494-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="92494-134">Ersetzen Sie sämtlichen C#-Code in Ihrem Editor durch folgenden Code, und verwenden Sie dann den `console run`-Befehl, um diesen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="92494-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
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
    
<span data-ttu-id="92494-135">Beachten Sie, dass der zweite interpolierte Ausdruck das `item`-Objekt in der Ergebniszeichenfolge enthält, die in der Konsole angezeigt wird. In diesem Fall wird die Zeichenfolge „eggplant“ in die Ergebniszeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="92494-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="92494-136">Dies liegt daran, dass der C#-Compiler Folgendes durchführt, wenn der Typ eines interpolierten Ausdrucks keine Zeichenfolge ist:</span><span class="sxs-lookup"><span data-stu-id="92494-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="92494-137">Wenn der interpolierte Ausdruck `null` ist, gibt dieser eine leere Zeichenfolge ("" oder <xref:System.String.Empty?displayProperty=nameWithType>) zurück.</span><span class="sxs-lookup"><span data-stu-id="92494-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="92494-138">Wenn der interpolierte Ausdruck nicht `null` ist, wird die `ToString`-Methode des Typs des interpolierten Ausdrucks aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="92494-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="92494-139">Sie können dies testen, indem Sie die Definition der `Vegetable.ToString`-Methode im Beispiel auskommentieren, indem Sie ein Kommentarsymbol (`//`) davor einfügen.</span><span class="sxs-lookup"><span data-stu-id="92494-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="92494-140">In der Ausgabe wird die Zeichenfolge „eggplant“ durch den Typnamen „Vegetable“ ersetzt. Dies stellt das Standardverhalten der <xref:System.Object.ToString?displayProperty=nameWithType>-Methode dar.</span><span class="sxs-lookup"><span data-stu-id="92494-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="92494-141">Bei der Ausgabe dieses Beispielcodes ist das Datum zu genau angegeben (der Preis von Auberginen ändert sich nicht sekündlich), und der Wert der Variablen „price“ gibt keine Währungsinformation an.</span><span class="sxs-lookup"><span data-stu-id="92494-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="92494-142">Im nächsten Abschnitt erfahren Sie, wie Sie diese Probleme beheben, indem Sie das Format der Zeichenfolgen steuern, die von interpolierten Ausdrücken zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92494-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="92494-143">Steuern der Formatierung von interpolierten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="92494-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="92494-144">Im vorherigen Abschnitt wurden zwei fehlerhaft formatierte Zeichenfolgen in die Ergebniszeichenfolge eingefügt.</span><span class="sxs-lookup"><span data-stu-id="92494-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="92494-145">Bei einer davon handelte es sich um einen Datums- und Uhrzeitwert, bei dem nur das Datum relevant war.</span><span class="sxs-lookup"><span data-stu-id="92494-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="92494-146">Bei der zweiten handelte es sich um einen Preis, bei dem keine Währungseinheit angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="92494-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="92494-147">Beide Probleme sind einfach zu beheben.</span><span class="sxs-lookup"><span data-stu-id="92494-147">Both issues are easy to address.</span></span> <span data-ttu-id="92494-148">Interpolierte Ausdrücke können *Formatzeichenfolgen* enthalten, die die Formatierung von bestimmten Typen steuern.</span><span class="sxs-lookup"><span data-stu-id="92494-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="92494-149">Ändern Sie den Aufruf von `Console.WriteLine` im vorherigen Beispiel, damit der Formatbezeichner für die Felder „date“ und „price“ wie in der folgenden Zeile dargestellt enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="92494-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="92494-150">Sie können eine Formatzeichenfolge angeben, indem Sie dem interpolierten Ausdruck einen Doppelpunkt und die Formatzeichenfolge anfügen.</span><span class="sxs-lookup"><span data-stu-id="92494-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="92494-151">Bei „d“ handelt es sich um eine [Zeichenfolge für das Standardformat für Datum und Uhrzeit](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier), die das kurze Datumsformat darstellt.</span><span class="sxs-lookup"><span data-stu-id="92494-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="92494-152">Bei „C2“ handelt es sich um eine [Zeichenfolge für das numerische Standardformat](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier), die eine Zahl als Währungswert mit zwei Ziffern nach dem Dezimaltrennzeichen darstellt.</span><span class="sxs-lookup"><span data-stu-id="92494-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="92494-153">Einige Typen in den .NET Standard-Bibliotheken unterstützen einen vordefinierten Satz von Formatzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="92494-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="92494-154">Darin sind alle numerischen Typen sowie alle Datums- und Uhrzeittypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="92494-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="92494-155">Eine vollständige Liste der Typen, die Formatzeichenfolgen unterstützen, finden Sie im Artikel [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) unter [Format Strings and .NET Class Library Types (Formatzeichenfolgen und .NET-Klassenbibliothekstypen)](../../standard/base-types/formatting-types.md#stringRef).</span><span class="sxs-lookup"><span data-stu-id="92494-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="92494-156">Jeder dieser Typen kann bestimmte Formatzeichenfolgen unterstützen. Sie können jedoch ebenfalls benutzerdefinierte Formatierungserweiterungen entwickeln, um benutzerdefinierte Formatierungen für vorhandene Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="92494-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="92494-157">Weitere Informationen zur benutzerdefinierten Formatierung durch die Bereitstellung einer <xref:System.ICustomFormatter>-Implementierung finden Sie im Artikel [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) unter [Benutzerdefinierte Formatierung mit ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="92494-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="92494-158">Versuchen Sie, die Formatzeichenfolgen in Ihrem Text-Editor zu ändern, und führen Sie das Programm jedes Mal erneut aus, wenn Sie eine Änderung vornehmen. So können Sie feststellen, wie sich die Änderungen auf die Formatierung des Datums, der Uhrzeit und des numerischen Werts auswirken.</span><span class="sxs-lookup"><span data-stu-id="92494-158">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="92494-159">Ändern Sie „d“ in `{date:d}` in „t“ (um das kurze Uhrzeitformat anzuzeigen) sowie in „y“ (um das Jahr und den Monat anzuzeigen) und in „yyyy“ (um das Jahr als vierstellige Zahl anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="92494-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="92494-160">Ändern Sie „C2“ in `{price:C2}` in „e“ (für die Exponentialschreibweise) und in „F3“ (für einen numerischen Wert mit drei Ziffern nach dem Dezimaltrennzeichen).</span><span class="sxs-lookup"><span data-stu-id="92494-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="92494-161">Sie können zusätzlich zum Steuern der Formatierung auch die Feldbreite und die Ausrichtung der Zeichenfolgen steuern, die von einem interpolierten Ausdruck zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="92494-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="92494-162">Im nächsten Abschnitt erfahren Sie mehr zu diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="92494-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="92494-163">Steuern der Feldbreite und der Ausrichtung von interpolierten Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="92494-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="92494-164">Wenn die von einem interpolierten Ausdruck zurückgegebene Zeichenfolge in eine Ergebniszeichenfolge eingefügt wird, enthält diese normalerweise keine führenden oder nachgestellten Leerräume.</span><span class="sxs-lookup"><span data-stu-id="92494-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="92494-165">Insbesondere bei Instanzen, bei denen Sie mit einem Datensatz arbeiten, können Sie durch interpolierte Ausdrücke die Breite und Ausrichtung eines Felds angeben.</span><span class="sxs-lookup"><span data-stu-id="92494-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="92494-166">Ersetzen Sie zur Veranschaulichung den gesamten Code in Ihrem Text-Editor durch folgenden Code, und geben Sie dann `console run` ein, um das Programm auszuführen:</span><span class="sxs-lookup"><span data-stu-id="92494-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
<span data-ttu-id="92494-167">Die Namen der Autoren sind linksbündig ausgerichtet, während deren Werke rechtsbündig ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="92494-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="92494-168">Sie können die Ausrichtung festlegen, indem Sie dem Ausdruck ein Komma („,“) anfügen und die Feldbreite angeben.</span><span class="sxs-lookup"><span data-stu-id="92494-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="92494-169">Wenn Sie eine positive Zahl für die Feldbreite eingeben, wird das Feld rechtsbündig ausgerichtet:</span><span class="sxs-lookup"><span data-stu-id="92494-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="92494-170">Wenn Sie eine negative Zahl für die Feldbreite eingeben, wird das Feld linksbündig ausgerichtet:</span><span class="sxs-lookup"><span data-stu-id="92494-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="92494-171">Entfernen Sie die negativen Vorzeichen der interpolierten Ausdrücke `{"Author",-25}` und `{title.Key,-25}`, und führen Sie das Beispiel erneut aus.</span><span class="sxs-lookup"><span data-stu-id="92494-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

<span data-ttu-id="92494-172">Diesmal sind die Informationen zum Autor rechtsbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="92494-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="92494-173">Sie können eine Feldbreite und eine Formatzeichenfolge in einem einzigen interpolierten Ausdruck kombinieren.</span><span class="sxs-lookup"><span data-stu-id="92494-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="92494-174">Die Feldbreite wird zuerst angegeben, gefolgt von einem Doppelpunkt und der Formatzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="92494-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="92494-175">Ersetzen Sie sämtlichen Code innerhalb der `Main`-Methode durch folgenden Code, der drei formatierte Zeichenfolgen mit definierten Feldbreiten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="92494-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="92494-176">Führen Sie das Programm anschließend aus, indem Sie den Befehl `dotnet run` eingeben.</span><span class="sxs-lookup"><span data-stu-id="92494-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="92494-177">Die Ausgabe sieht in etwa folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="92494-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="92494-178">Sie haben den Schnellstart für interpolierte Zeichenfolgen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="92494-178">You've completed the interpolated strings quickstart.</span></span> 
    
<span data-ttu-id="92494-179">Sie können mit dem Schnellstart [Arrays und Auflistungen](arrays-and-collections.md) in Ihrer eigenen Entwicklungsumgebung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="92494-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="92494-180">Weitere Informationen zum Arbeiten mit interpolierten Zeichenfolgen finden Sie im Artikel [Interpolierte Zeichenfolgen](../language-reference/keywords/interpolated-strings.md) in der C#-Referenz.</span><span class="sxs-lookup"><span data-stu-id="92494-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>

