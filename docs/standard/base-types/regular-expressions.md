---
title: "Reguläre Ausdrücke in .NET"
description: "Reguläre Ausdrücke in .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d1a640cf-09ca-48f7-800c-a627a6d549c9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ac26821819b22aa3ea47e6945bb5c8575dcd9807
ms.contentlocale: de-de
ms.lasthandoff: 03/02/2017

---

# <a name="regular-expressions-in-net"></a><span data-ttu-id="751f7-104">Reguläre Ausdrücke in .NET</span><span class="sxs-lookup"><span data-stu-id="751f7-104">Regular expressions in .NET</span></span>

<span data-ttu-id="751f7-105">Der Einsatz regulärer Ausdrücke stellt eine leistungsstarke, flexible und effiziente Methode zur Verarbeitung von Text dar.</span><span class="sxs-lookup"><span data-stu-id="751f7-105">Regular expressions provide a powerful, flexible, and efficient method for processing text.</span></span> <span data-ttu-id="751f7-106">Durch die umfangreiche Notation regulärer Ausdrücke für den Mustervergleich können folgende Aufgaben ausgeführt werden: schnelle Auswertung großer Textmengen zur Suche nach speziellen Zeichenmustern; Validieren von Text, um sicherzustellen, dass er einem vordefinierten Muster entspricht (z. B. eine E-Mail-Adresse); Extrahieren, Bearbeiten, Ersetzen oder Löschen von Textzeichenfolgen; Hinzufügen der extrahierten Zeichenfolgen zu einer Auflistung, um einen Bericht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="751f7-106">The extensive pattern-matching notation of regular expressions enables you to quickly parse large amounts of text to find specific character patterns; to validate text to ensure that it matches a predefined pattern (such as an e-mail address); to extract, edit, replace, or delete text substrings; and to add the extracted strings to a collection in order to generate a report.</span></span> <span data-ttu-id="751f7-107">Für viele Anwendungen, die mit Zeichenfolgen arbeiten oder große Textblöcke analysieren, sind reguläre Ausdrücke ein unverzichtbares Tool.</span><span class="sxs-lookup"><span data-stu-id="751f7-107">For many applications that deal with strings or that parse large blocks of text, regular expressions are an indispensable tool.</span></span>

## <a name="how-regular-expressions-work"></a><span data-ttu-id="751f7-108">Funktionsweise von regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="751f7-108">How Regular Expressions Work</span></span>

<span data-ttu-id="751f7-109">Das Kernstück der Textverarbeitung mit regulären Ausdrücken ist das Modul für reguläre Ausdrücke, das durch das [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Objekt in .NET dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-109">The centerpiece of text processing with regular expressions is the regular expression engine, which is represented by the [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex) object in .NET.</span></span> <span data-ttu-id="751f7-110">Für die Textverarbeitung mit regulären Ausdrücken ist mindestens erforderlich, dass das Modul für reguläre Ausdrücke mit den folgenden zwei Informationen bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="751f7-110">At a minimum, processing text using regular expressions requires that the regular expression engine be provided with the following two items of information:</span></span>

* <span data-ttu-id="751f7-111">Das Muster des regulären Ausdrucks, das im Text identifiziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="751f7-111">The regular expression pattern to identify in the text.</span></span> 
  
  <span data-ttu-id="751f7-112">In .NET werden Muster für reguläre Ausdrücke durch eine spezielle Syntax oder Sprache definiert, die mit regulären Ausdrücken in Perl 5 kompatibel ist und einige zusätzliche Funktionen wie Mustervergleiche von rechts nach links bietet.</span><span class="sxs-lookup"><span data-stu-id="751f7-112">In .NET, regular expression patterns are defined by a special syntax or language, which is compatible with Perl 5 regular expressions and adds some additional features such as right-to-left matching.</span></span> <span data-ttu-id="751f7-113">Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="751f7-113">For more information, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>
  
* <span data-ttu-id="751f7-114">Der Text, der nach dem Muster des regulären Ausdrucks analysiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="751f7-114">The text to parse for the regular expression pattern.</span></span>

<span data-ttu-id="751f7-115">Mit den Methoden der [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse können Sie die folgenden Vorgänge durchführen:</span><span class="sxs-lookup"><span data-stu-id="751f7-115">The methods of the [Regex](xref:System.Text.RegularExpressions.Regex) class let you perform the following operations:</span></span>

* <span data-ttu-id="751f7-116">Ermitteln, ob das Muster für reguläre Ausdrücke im Eingabetext vorkommt, indem die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-116">Determine whether the regular expression pattern occurs in the input text by calling the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method.</span></span> <span data-ttu-id="751f7-117">Ein Beispiel für die Validierung von Text mit der [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode finden Sie unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](verify-format.md).</span><span class="sxs-lookup"><span data-stu-id="751f7-117">For an example that uses the [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method for validating text, see [How to: Verify that Strings Are in Valid Email Format](verify-format.md).</span></span>

* <span data-ttu-id="751f7-118">Abrufen eines oder aller Vorkommen des Texts, die dem Muster für reguläre Ausdrücke entsprechen, indem die [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String))-Methode oder die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-118">Retrieve one or all occurrences of text that matches the regular expression pattern by calling the [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) or [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String)) method.</span></span> <span data-ttu-id="751f7-119">Die erste Methode gibt ein [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match)-Objekt zurück, das Informationen über den übereinstimmenden Text bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="751f7-119">The former method returns a [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object that provides information about the matching text.</span></span> <span data-ttu-id="751f7-120">Die zweite gibt ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt zurück, das ein [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match)-Objekt für jede im analysierten Text gefundene Übereinstimmung enthält.</span><span class="sxs-lookup"><span data-stu-id="751f7-120">The latter returns a [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) object that contains one [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match) object for each match found in the parsed text.</span></span> 

* <span data-ttu-id="751f7-121">Ersetzen von Text, der das Muster für reguläre Ausdrücke abgleicht, indem die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-121">Replace text that matches the regular expression pattern by calling the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method.</span></span> <span data-ttu-id="751f7-122">Beispiele, in denen die [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode verwendet wird, um Datumsformate zu ändern und ungültige Zeichen aus einer Zeichenfolge zu entfernen, finden Sie unter [Gewusst wie: Entfernen von ungültigen Zeichen aus einer Zeichenfolge](strip-characters.md) und unter [Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten](changing-formats.md).</span><span class="sxs-lookup"><span data-stu-id="751f7-122">For examples that use the [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method to change date formats and remove invalid characters from a string, see [How to: Strip Invalid Characters from a String](strip-characters.md) and [Regular Expression Example: Changing Date Formats](changing-formats.md).</span></span>

<span data-ttu-id="751f7-123">Eine Übersicht über das Objektmodell für reguläre Ausdrücke finden Sie unter [Das Objektmodell für reguläre Ausdrücke](object-model.md).</span><span class="sxs-lookup"><span data-stu-id="751f7-123">For an overview of the regular expression object model, see [The Regular Expression Object Model](object-model.md).</span></span>

<span data-ttu-id="751f7-124">Weitere Informationen über die Sprache für reguläre Ausdrücke finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md).</span><span class="sxs-lookup"><span data-stu-id="751f7-124">For more information about the regular expression language, see [Regular Expression Language - Quick Reference](quick-ref.md).</span></span>

## <a name="regular-expression-examples"></a><span data-ttu-id="751f7-125">Beispiele für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="751f7-125">Regular Expression Examples</span></span>

<span data-ttu-id="751f7-126">Die [String](xref:System.String)-Klasse enthält eine Reihe von Such- und Ersetzungsmethoden für Zeichenfolgen, die Sie verwenden können, wenn Sie Literalzeichenfolgen in einer größeren Zeichenfolge suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="751f7-126">The [String](xref:System.String) class includes a number of string search and replacement methods that you can use when you want to locate literal strings in a larger string.</span></span> <span data-ttu-id="751f7-127">Reguläre Ausdrücke sind besonders hilfreich, wenn Sie eine von mehreren Teilzeichenfolgen in einer größeren Zeichenfolge suchen oder wenn Sie Muster in einer Zeichenfolge identifizieren möchten, wie in den folgenden Beispielen veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-127">Regular expressions are most useful either when you want to locate one of several substrings in a larger string, or when you want to identify patterns in a string, as the following examples illustrate.</span></span> 

### <a name="example-1-replacing-substrings"></a><span data-ttu-id="751f7-128">Beispiel 1: Ersetzen von Teilzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="751f7-128">Example 1: Replacing Substrings</span></span>

<span data-ttu-id="751f7-129">Angenommen, eine Mailingliste enthält neben dem Vor- und Nachnamen bei einigen Personen auch Angaben zur Anrede (Mr., Mrs., Miss oder Ms.).</span><span class="sxs-lookup"><span data-stu-id="751f7-129">Assume that a mailing list contains names that sometimes include a title (Mr., Mrs., Miss, or Ms.) along with a first and last name.</span></span> <span data-ttu-id="751f7-130">Wenn Sie Adressaufkleber aus der Liste generieren, die Anrede dabei jedoch unberücksichtigt lassen möchten, können Sie diese mithilfe eines regulären Ausdrucks entfernen, wie im folgenden Beispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-130">If you do not want to include the titles when you generate envelope labels from the list, you can use a regular expression to remove the titles, as the following example illustrates.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(Mr\\.? |Mrs\\.? |Miss |Ms\\.? )";
      string[] names = { "Mr. Henry Hunt", "Ms. Sara Samuels", 
                         "Abraham Adams", "Ms. Nicole Norris" };
      foreach (string name in names)
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty));
   }
}
// The example displays the following output:
//    Henry Hunt
//    Sara Samuels
//    Abraham Adams
//    Nicole Norris
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(Mr\.? |Mrs\.? |Miss |Ms\.? )"
      Dim names() As String = { "Mr. Henry Hunt", "Ms. Sara Samuels", _
                                "Abraham Adams", "Ms. Nicole Norris" }
      For Each name As String In names
         Console.WriteLine(Regex.Replace(name, pattern, String.Empty))
      Next                                
   End Sub
End Module
' The example displays the following output:
'    Henry Hunt
'    Sara Samuels
'    Abraham Adams
'    Nicole Norris
```

<span data-ttu-id="751f7-131">Das Muster für reguläre Ausdrücke `(Mr\.? |Mrs\.? |Miss |Ms\.? )` entspricht jedem Vorkommen von „Mr “, „Mr. “, „Mrs “, „Mrs. “, „Miss “, „Ms “ oder „Ms. “.</span><span class="sxs-lookup"><span data-stu-id="751f7-131">The regular expression pattern `(Mr\.? |Mrs\.? |Miss |Ms\.? )` matches any occurrence of "Mr ", "Mr. ", "Mrs ", "Mrs. ", "Miss ", "Ms or "Ms. ".</span></span> <span data-ttu-id="751f7-132">Wenn Sie die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode aufrufen, wird die entsprechende Zeichenfolge durch [String.Empty](xref:System.String.Empty) ersetzt, d.h., die Zeichenfolge wird aus der ursprünglichen Zeichenfolge entfernt.</span><span class="sxs-lookup"><span data-stu-id="751f7-132">The call to the [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String)) method replaces the matched string with [String.Empty](xref:System.String.Empty); in other words, it removes it from the original string.</span></span>

### <a name="example-2-identifying-duplicated-words"></a><span data-ttu-id="751f7-133">Beispiel 2: Identifizieren von doppelten Wörtern</span><span class="sxs-lookup"><span data-stu-id="751f7-133">Example 2: Identifying Duplicated Words</span></span>

<span data-ttu-id="751f7-134">Das versehentliche Erstellen doppelter Wörter ist ein Fehler, der häufig von Entwicklern gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-134">Accidentally duplicating words is a common error that writers make.</span></span> <span data-ttu-id="751f7-135">Mithilfe eines regulären Ausdrucks können Sie doppelte Wörter identifizieren, wie im folgenden Beispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-135">A regular expression can be used to identify duplicated words, as the following example shows.</span></span>

```csharp
using System;
using System.Text.RegularExpressions;

public class Class1
{
   public static void Main()
   {
      string pattern = @"\b(\w+?)\s\1\b";
      string input = "This this is a nice day. What about this? This tastes good. I saw a a dog.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", 
                           match.Value, match.Groups[1].Value, match.Index);
   }
}
// The example displays the following output:
//       This this (duplicates 'This)' at position 0
//       a a (duplicates 'a)' at position 66
```

```vb
Imports System.Text.RegularExpressions

Module modMain
   Public Sub Main()
      Dim pattern As String = "\b(\w+?)\s\1\b"
      Dim input As String = "This this is a nice day. What about this? This tastes good. I saw a a dog."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("{0} (duplicates '{1}') at position {2}", _
                           match.Value, match.Groups(1).Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       This this (duplicates 'This)' at position 0
'       a a (duplicates 'a)' at position 66
```

<span data-ttu-id="751f7-136">Das Muster des regulären Ausdrucks `\b(\w+?)\s\1\b` kann wie folgt interpretiert werden:</span><span class="sxs-lookup"><span data-stu-id="751f7-136">The regular expression pattern `\b(\w+?)\s\1\b` can be interpreted as follows:</span></span>

<span data-ttu-id="751f7-137">Syntax</span><span class="sxs-lookup"><span data-stu-id="751f7-137">Syntax</span></span> | <span data-ttu-id="751f7-138">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="751f7-138">Meaning</span></span>
------ | -------
`\b` | <span data-ttu-id="751f7-139">An einer Wortgrenze beginnen.</span><span class="sxs-lookup"><span data-stu-id="751f7-139">Start at a word boundary.</span></span>
`(\w+?)` | <span data-ttu-id="751f7-140">Entspricht einem oder mehreren Wortzeichen, aber so wenigen Zeichen wie möglich.</span><span class="sxs-lookup"><span data-stu-id="751f7-140">Match one or more word characters, but as few characters as possible.</span></span> <span data-ttu-id="751f7-141">Zusammen bilden diese eine Gruppe, auf die mit `\1` verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="751f7-141">Together, they form a group that can be referred to as `\1`.</span></span>
`\s` | <span data-ttu-id="751f7-142">Entsprechung für ein Leerraumzeichen finden.</span><span class="sxs-lookup"><span data-stu-id="751f7-142">Match a white-space character.</span></span>
`\1` | <span data-ttu-id="751f7-143">Entsprechung für die Teilzeichenfolge finden, die gleich der Gruppe `\1` ist.</span><span class="sxs-lookup"><span data-stu-id="751f7-143">Match the substring that is equal to the group named `\1`.</span></span>
`\b` | <span data-ttu-id="751f7-144">Übereinstimmung mit einer Wortgrenze.</span><span class="sxs-lookup"><span data-stu-id="751f7-144">Match a word boundary.</span></span>

<span data-ttu-id="751f7-145">Die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode wird aufgerufen, wobei die Optionen für reguläre Ausdrücke auf [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="751f7-145">The [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions)) method is called with regular expression options set to [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase).</span></span> <span data-ttu-id="751f7-146">Beim Abgleichvorgang spielt die Groß- und Kleinschreibung daher keine Rolle, und die Teilzeichenfolge "This this" wird im Beispiel als Duplikat identifiziert.</span><span class="sxs-lookup"><span data-stu-id="751f7-146">Therefore, the match operation is case-insensitive, and the example identifies the substring "This this" as a duplication.</span></span>

<span data-ttu-id="751f7-147">Beachten Sie, dass die Eingabezeichenfolge die Teilzeichenfolge "this?</span><span class="sxs-lookup"><span data-stu-id="751f7-147">Note that the input string includes the substring "this?</span></span> <span data-ttu-id="751f7-148">This" enthält.</span><span class="sxs-lookup"><span data-stu-id="751f7-148">This".</span></span> <span data-ttu-id="751f7-149">Aufgrund des dazwischenliegenden Satzzeichens wird diese jedoch nicht als Duplikat identifiziert.</span><span class="sxs-lookup"><span data-stu-id="751f7-149">However, because of the intervening punctuation mark, it is not identified as a duplication.</span></span>

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a><span data-ttu-id="751f7-150">Beispiel 3: Dynamisches Erstellen eines kulturabhängigen regulären Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="751f7-150">Example 3: Dynamically Building a Culture-Sensitive Regular Expression</span></span>

<span data-ttu-id="751f7-151">Das folgende Beispiel veranschaulicht die Leistungsfähigkeit regulärer Ausdrücke in Kombination mit der Flexibilität der .NET-Globalisierungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="751f7-151">The following example illustrates the power of regular expressions combined with the flexibility offered by .NET's globalization features.</span></span> <span data-ttu-id="751f7-152">Mit dem [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt wird das Format von Währungswerten in der aktuellen Kultur des Systems bestimmt.</span><span class="sxs-lookup"><span data-stu-id="751f7-152">It uses the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to determine the format of currency values in the system's current culture.</span></span> <span data-ttu-id="751f7-153">Anschließend wird anhand dieser Informationen dynamisch ein regulärer Ausdruck erstellt, der Währungswerte aus dem Text extrahiert.</span><span class="sxs-lookup"><span data-stu-id="751f7-153">It then uses that information to dynamically construct a regular expression that extracts currency values from the text.</span></span> <span data-ttu-id="751f7-154">Für jede Übereinstimmung wird die Untergruppe extrahiert, die nur die numerische Zeichenfolge enthält. Diese wird in einen [Decimal](xref:System.Decimal)-Wert konvertiert, und dann wird ein laufender Gesamtbetrag berechnet.</span><span class="sxs-lookup"><span data-stu-id="751f7-154">For each match, it extracts the subgroup that contains the numeric string only, converts it to a [Decimal](xref:System.Decimal) value, and calculates a running total.</span></span> 

```csharp
using System;
using System.Collections.Generic;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define text to be parsed.
      string input = "Office expenses on 2/13/2008:\n" + 
                     "Paper (500 sheets)                      $3.95\n" + 
                     "Pencils (box of 10)                     $1.00\n" + 
                     "Pens (box of 10)                        $4.49\n" + 
                     "Erasers                                 $2.19\n" + 
                     "Ink jet printer                        $69.95\n\n" + 
                     "Total Expenses                        $ 81.58\n"; 

      // Get current culture's NumberFormatInfo object.
      NumberFormatInfo nfi = CultureInfo.CurrentCulture.NumberFormat;
      // Assign needed property values to variables.
      string currencySymbol = nfi.CurrencySymbol;
      bool symbolPrecedesIfPositive = nfi.CurrencyPositivePattern % 2 == 0;
      string groupSeparator = nfi.CurrencyGroupSeparator;
      string decimalSeparator = nfi.CurrencyDecimalSeparator;

      // Form regular expression pattern.
      string pattern = Regex.Escape( symbolPrecedesIfPositive ? currencySymbol : "") + 
                       @"\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + 
                       Regex.Escape(decimalSeparator) + "[0-9]+)?)" + 
                       (! symbolPrecedesIfPositive ? currencySymbol : ""); 
      Console.WriteLine( "The regular expression pattern is:");
      Console.WriteLine("   " + pattern);      

      // Get text that matches regular expression pattern.
      MatchCollection matches = Regex.Matches(input, pattern, 
                                              RegexOptions.IgnorePatternWhitespace);               
      Console.WriteLine("Found {0} matches.", matches.Count); 

      // Get numeric string, convert it to a value, and add it to List object.
      List<decimal> expenses = new List<Decimal>();

      foreach (Match match in matches)
         expenses.Add(Decimal.Parse(match.Groups[1].Value));      

      // Determine whether total is present and if present, whether it is correct.
      decimal total = 0;
      foreach (decimal value in expenses)
         total += value;

      if (total / 2 == expenses[expenses.Count - 1]) 
         Console.WriteLine("The expenses total {0:C2}.", expenses[expenses.Count - 1]);
      else
         Console.WriteLine("The expenses total {0:C2}.", total);
   }  
}
// The example displays the following output:
//       The regular expression pattern is:
//          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
//       Found 6 matches.
//       The expenses total $81.58.
```

```vb
Imports System.Collections.Generic
Imports System.Globalization
Imports System.Text.RegularExpressions

Public Module Example
   Public Sub Main()
      ' Define text to be parsed.
      Dim input As String = "Office expenses on 2/13/2008:" + vbCrLf + _
                            "Paper (500 sheets)                      $3.95" + vbCrLf + _
                            "Pencils (box of 10)                     $1.00" + vbCrLf + _
                            "Pens (box of 10)                        $4.49" + vbCrLf + _
                            "Erasers                                 $2.19" + vbCrLf + _
                            "Ink jet printer                        $69.95" + vbCrLf + vbCrLf + _
                            "Total Expenses                        $ 81.58" + vbCrLf
      ' Get current culture's NumberFormatInfo object.
      Dim nfi As NumberFormatInfo = CultureInfo.CurrentCulture.NumberFormat
      ' Assign needed property values to variables.
      Dim currencySymbol As String = nfi.CurrencySymbol
      Dim symbolPrecedesIfPositive As Boolean = CBool(nfi.CurrencyPositivePattern Mod 2 = 0)
      Dim groupSeparator As String = nfi.CurrencyGroupSeparator
      Dim decimalSeparator As String = nfi.CurrencyDecimalSeparator

      ' Form regular expression pattern.
      Dim pattern As String = Regex.Escape(CStr(IIf(symbolPrecedesIfPositive, currencySymbol, ""))) + _
                              "\s*[-+]?" + "([0-9]{0,3}(" + groupSeparator + "[0-9]{3})*(" + _
                              Regex.Escape(decimalSeparator) + "[0-9]+)?)" + _
                              CStr(IIf(Not symbolPrecedesIfPositive, currencySymbol, "")) 
      Console.WriteLine("The regular expression pattern is: ")
      Console.WriteLine("   " + pattern)      

      ' Get text that matches regular expression pattern.
      Dim matches As MatchCollection = Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)               
      Console.WriteLine("Found {0} matches. ", matches.Count)

      ' Get numeric string, convert it to a value, and add it to List object.
      Dim expenses As New List(Of Decimal)

      For Each match As Match In matches
         expenses.Add(Decimal.Parse(match.Groups.Item(1).Value))      
      Next

      ' Determine whether total is present and if present, whether it is correct.
      Dim total As Decimal
      For Each value As Decimal In expenses
         total += value
      Next

      If total / 2 = expenses(expenses.Count - 1) Then
         Console.WriteLine("The expenses total {0:C2}.", expenses(expenses.Count - 1))
      Else
         Console.WriteLine("The expenses total {0:C2}.", total)
      End If   
   End Sub
End Module
' The example displays the following output:
'       The regular expression pattern is:
'          \$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)
'       Found 6 matches.
'       The expenses total $81.58.
```

<span data-ttu-id="751f7-155">Im Beispiel wird dynamisch der reguläre Ausdruck `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` auf einem Computer mit der aktuellen Kultur Englisch - USA (en-US) erstellt.</span><span class="sxs-lookup"><span data-stu-id="751f7-155">On a computer whose current culture is English - United States (en-US), the example dynamically builds the regular expression `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`.</span></span> <span data-ttu-id="751f7-156">Dieses Muster des regulären Ausdrucks kann wie folgt interpretiert werden:</span><span class="sxs-lookup"><span data-stu-id="751f7-156">This regular expression pattern can be interpreted as follows:</span></span>

<span data-ttu-id="751f7-157">Syntax</span><span class="sxs-lookup"><span data-stu-id="751f7-157">Syntax</span></span> | <span data-ttu-id="751f7-158">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="751f7-158">Meaning</span></span>
------ | -------
`\$` | <span data-ttu-id="751f7-159">Suche nach einem einzelnen Vorkommen des Dollarsymbols ($) in der Eingabezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="751f7-159">Look for a single occurrence of the dollar symbol ($) in the input string.</span></span> <span data-ttu-id="751f7-160">Die Musterzeichenfolge des regulären Ausdrucks schließt einen umgekehrten Schrägstrich ein, der angibt, dass das Dollarsymbol nicht als Anchor des regulären Ausdrucks, sondern wörtlich interpretiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="751f7-160">The regular expression pattern string includes a backslash to indicate that the dollar symbol is to be interpreted literally rather than as a regular expression anchor.</span></span> <span data-ttu-id="751f7-161">(Das $-Symbol allein würde angeben, dass das Modul für reguläre Ausdrücke versuchen soll, mit der Suche nach Übereinstimmungen am Ende einer Zeichenfolge zu beginnen.) Um sicherzustellen, dass das Währungssymbol der aktuellen Kultur nicht als reguläres Ausdruckssymbol fehlinterpretiert wird, wird im Beispiel die [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String))-Methode aufgerufen, um das Zeichen mit Escapezeichen zu versehen.</span><span class="sxs-lookup"><span data-stu-id="751f7-161">(The $ symbol alone would indicate that the regular expression engine should try to begin its match at the end of a string.) To ensure that the current culture's currency symbol is not misinterpreted as a regular expression symbol, the example calls the [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String)) method to escape the character.</span></span>
`\s*` | <span data-ttu-id="751f7-162">Suche nach&0; (null) oder mehr Vorkommen eines Leerstellenzeichens.</span><span class="sxs-lookup"><span data-stu-id="751f7-162">Look for zero or more occurrences of a white-space character.</span></span>
`[-+]?` | <span data-ttu-id="751f7-163">Suche nach&0; (null) oder einem Vorkommen entweder eines positiven oder eines negativen Vorzeichens.</span><span class="sxs-lookup"><span data-stu-id="751f7-163">Look for zero or one occurrence of either a positive sign or a negative sign.</span></span>
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | <span data-ttu-id="751f7-164">Die äußeren Klammern um diesen Ausdruck definieren ihn als Erfassungsgruppe oder Teilausdruck.</span><span class="sxs-lookup"><span data-stu-id="751f7-164">The outer parentheses around this expression define it as a capturing group or a subexpression.</span></span> <span data-ttu-id="751f7-165">Wenn eine Übereinstimmung gefunden wird, können Informationen über diesen Teil der übereinstimmenden Zeichenfolge aus dem zweiten [Group](xref:System.Text.RegularExpressions.Group)-Objekt in dem [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt abgerufen werden, das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="751f7-165">If a match is found, information about this part of the matching string can be retrieved from the second [Group](xref:System.Text.RegularExpressions.Group) object in the [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection) object returned by the [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups) property.</span></span> <span data-ttu-id="751f7-166">(Das erste Element in der Auflistung stellt die gesamte Übereinstimmung dar.)</span><span class="sxs-lookup"><span data-stu-id="751f7-166">(The first element in the collection represents the entire match.)</span></span>
`[0-9]{0,3}` | <span data-ttu-id="751f7-167">Suche nach 0 (null) bis drei Vorkommen der Dezimalstellen 0 bis 9.</span><span class="sxs-lookup"><span data-stu-id="751f7-167">Look for zero to three occurrences of the decimal digits 0 through 9.</span></span>
`(,[0-9]{3})*` | <span data-ttu-id="751f7-168">Suche nach&0; (null) oder mehr Vorkommen eines Gruppentrennzeichens gefolgt von drei Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="751f7-168">Look for zero or more occurrences of a group separator followed by three decimal digits.</span></span>
`\.` | <span data-ttu-id="751f7-169">Suche nach einem einzelnen Vorkommen des Dezimaltrennzeichens.</span><span class="sxs-lookup"><span data-stu-id="751f7-169">Look for a single occurrence of the decimal separator.</span></span>
`[0-9]+` | <span data-ttu-id="751f7-170">Suche nach einer oder mehr Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="751f7-170">Look for one or more decimal digits.</span></span>
`(\.[0-9]+)?` | <span data-ttu-id="751f7-171">Suche nach&0; (null) oder einem Vorkommen des Dezimaltrennzeichens, auf das mindestens eine Dezimalstelle folgt.</span><span class="sxs-lookup"><span data-stu-id="751f7-171">Look for zero or one occurrence of the decimal separator followed by at least one decimal digit.</span></span>

## <a name="related-topics"></a><span data-ttu-id="751f7-172">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="751f7-172">Related Topics</span></span>

<span data-ttu-id="751f7-173">Titel</span><span class="sxs-lookup"><span data-stu-id="751f7-173">Title</span></span> | <span data-ttu-id="751f7-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="751f7-174">Description</span></span>
----- | -----------
[<span data-ttu-id="751f7-175">Sprachelemente für reguläre Ausdrücke – Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="751f7-175">Regular expression language - quick reference</span></span>](quick-ref.md) | <span data-ttu-id="751f7-176">Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.</span><span class="sxs-lookup"><span data-stu-id="751f7-176">Provides information on the set of characters, operators, and constructs that you can use to define regular expressions.</span></span>
[<span data-ttu-id="751f7-177">Das Objektmodell für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="751f7-177">The regular expression object model</span></span>](object-model.md) | <span data-ttu-id="751f7-178">Ausführliche Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="751f7-178">Provides information and code examples that illustrate how to use the regular expression classes.</span></span>
[<span data-ttu-id="751f7-179">Einzelheiten zum Verhalten regulärer Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="751f7-179">Details of regular expression behavior</span></span>](regex-behavior.md) | <span data-ttu-id="751f7-180">Ausführliche Informationen zu den Funktionen und dem Verhalten von regulären Ausdrücken in .NET.</span><span class="sxs-lookup"><span data-stu-id="751f7-180">Provides information about the capabilities and behavior of .NETregular expressions.</span></span>
[<span data-ttu-id="751f7-181">Beispiele für reguläre Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="751f7-181">Regular expression examples</span></span>](regex-examples.md) | <span data-ttu-id="751f7-182">Codebeispiele, die typische Anwendungen regulärer Ausdrücke veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="751f7-182">Provides code examples that illustrate typical uses of regular expressions.</span></span>


## <a name="reference"></a><span data-ttu-id="751f7-183">Verweis</span><span class="sxs-lookup"><span data-stu-id="751f7-183">Reference</span></span>

[<span data-ttu-id="751f7-184">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="751f7-184">System.Text.RegularExpressions</span></span>](xref:System.Text.RegularExpressions)

[<span data-ttu-id="751f7-185">System.Text.RegularExpressions.Regex</span><span class="sxs-lookup"><span data-stu-id="751f7-185">System.Text.RegularExpressions.Regex</span></span>](xref:System.Text.RegularExpressions.Regex)


