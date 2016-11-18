---
title: "Optionen für reguläre Ausdrücke"
description: "Optionen für reguläre Ausdrücke"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2db2c3e6-953e-4913-8168-d707c437f2df
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: a2a9fe356a0b2e9cf9415714bc01b77ea86229fc

---

# <a name="regular-expression-options"></a>Optionen für reguläre Ausdrücke

Standardmäßig wird beim Vergleich einer Eingabezeichenfolge mit Literalzeichen in einem Muster eines regulären Ausdrucks die Groß-/Kleinschreibung beachtet, Leerstellen in einem Muster eines regulären Ausdrucks werden als literale Leerstellenzeichen interpretiert, und Erfassungsgruppen in einem regulären Ausdruck werden implizit sowie explizit benannt. Sie können diese und andere Aspekte des Standardverhaltens regulärer Ausdrücke ändern, indem Sie Optionen für reguläre Ausdrücke angeben. Diese Optionen, die in der folgenden Tabelle aufgeführt sind, können inline als Teil des Musters für reguläre Ausdrücke enthalten sein, oder sie können für einen [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktor oder eine statische Musterabgleichsmethode als [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Enumerationswert angegeben werden. 

RegexOptions-Member | Inlinezeichen | Effekt
------------------- | ---------------- | ------ 
[Keine](xref:System.Text.RegularExpressions.RegexOptions.None) | Nicht verfügbar | Standardverfahren verwenden. Weitere Informationen finden Sie unter [Standardoptionen](#default-options).
[IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) | **i** | Groß-/Kleinschreibung bei der Suche ignorieren Weitere Informationen finden Sie unter [Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung](#case-insensitive-matching).
[Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) | **m** | Verwenden Sie den Mehrzeilenmodus, in dem **^** und **$** dem Anfang und dem Ende jeder Zeile (und nicht dem Anfang und dem Ende der Eingabezeichenfolge) entsprechen. Weitere Informationen finden Sie unter [Mehrzeilenmodus](#multiline-mode).
[Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) | **s** | Verwenden Sie den Einzeilenmodus, in dem der Punkt (**.**) den einzelnen Zeichen entspricht (anstatt allen Zeichen mit Ausnahme von **\n**). Weitere Informationen finden Sie unter [Einzeilenmodus](#single-line-mode).
[ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) | **n** | Unbenannte Gruppen nicht erfassen Die einzigen gültigen Erfassungen sind explizit benannte oder nummerierte Gruppen in der Form **(?<**_name_**>** _teilausdruck_**)**. Weitere Informationen finden Sie unter [Nur explizite Erfassungen](#explicit-captures-only).
[Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) | Nicht verfügbar | Kompiliert den regulären Ausdruck in eine Assembly. Weitere Informationen hierzu finden Sie unter [Kompilierte reguläre Ausdrücke](#compiled-regular-expressions).
[IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) | **x** | Schließt Leerzeichen ohne Escapezeichen vom Muster aus und aktiviert Kommentare nach einem Nummernzeichen (**#**). Weitere Informationen finden Sie unter [Leerzeichen ignorieren](#ignore-white-space).
[RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) | Nicht verfügbar | Ändert die Suchrichtung. Die Suche wird von rechts nach links und nicht von links nach rechts durchgeführt. Weitere Informationen finden Sie unter [Rechts-nach-links-Modus](#right-to-left-mode).
[ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) | Nicht verfügbar | ECMAScript-kompatibles Verhalten für den Ausdruck aktivieren. Weitere Informationen finden Sie unter [ECMAScript-Vergleichsverhalten](#ecmascript-matching-behavior).
[CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) | Nicht verfügbar | Ignoriert kulturelle Unterschiede in der Sprache. Weitere Informationen finden Sie unter [Vergleiche mit der invarianten Kultur](#comparison-using-the-invariant-culture).
 
## <a name="specifying-the-options"></a>Angeben der Optionen

Sie können Optionen für reguläre Ausdrücke mit einer von drei Methoden angeben:

* Im *options*-Parameter eines [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors wie z.B. [Regex.Regex(String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.%23ctor(System.String,System.Text.RegularExpressions.RegexOptions)) oder einer statischen („Shared“ in Visual Basic) Mustervergleichsmethode, z.B. [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). Der *options*-Parameter ist eine bitweise OR-Kombination aus [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Enumerationswerten. 

  Optionen, die mithilfe des *options*-Parameters eines Klassenkonstruktors an eine [Regex](xref:System.Text.RegularExpressions.Regex)-Instanz übergeben werden, werden der [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Eigenschaft zugewiesen. Die [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Eigenschaft gibt jedoch keine Inlineoptionen des eigentlichen Musters für reguläre Ausdrücke wieder. 

  Dies wird im folgenden Beispiel veranschaulicht. Darin wird der *options*-Parameter der [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode verwendet, um Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung zu ermöglichen und Leerzeichen im Muster zu ignorieren, wenn Wörter identifiziert werden, die mit dem Buchstaben „d“ beginnen.

  ```csharp
  string pattern = @"d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  RegexOptions options = RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace;
  
  foreach (Match match in Regex.Matches(input, pattern, options))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."
  Dim options As RegexOptions = RegexOptions.IgnoreCase Or RegexOptions.IgnorePatternWhitespace

  For Each match As Match In Regex.Matches(input, pattern, options)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Durch Anwenden von Inlineoptionen in einem Muster für reguläre Ausdrücke mit der Syntax **(?imnsx-imnsx)**. Die Option gilt für das Muster ab dem Punkt, an dem die Option definiert wird, bis zum Ende des Musters oder zu dem Punkt, an dem die Definition der Option von einer anderen Inlineoption aufgehoben wird. Beachten Sie, dass die [System.Text.RegularExpressions.RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Eigenschaft einer [Regex](xref:System.Text.RegularExpressions.Regex)-Instanz diese Inlineoptionen nicht wiedergibt. Weitere Informationen finden Sie im Thema [Verschiedene Konstrukte in regulären Ausdrücken](miscellaneous.md).

  Dies wird im folgenden Beispiel veranschaulicht. Dabei werden Inlineoptionen verwendet, um Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung zu ermöglichen und das Ignorieren von Leerzeichenmustern zu aktivieren, wenn Wörter identifiziert werden, die mit dem Buchstaben "d" beginnen.

  ```csharp
  string pattern = @"(?ix) d \w+ \s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix) d \w+ \s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9.  
  ```

* Durch Anwenden von Inlineoptionen in einem bestimmten Gruppierungskonstrukt in einem Muster für reguläre Ausdrücke mit der Syntax **(?imnsx-imnsx:**_teilausdruck_**)**. Kein Vorzeichen vor einer Gruppe von Optionen aktiviert diese Optionen. Ein Minuszeichen deaktiviert sie. (**?** ist ein fester Bestandteil der Syntax des Sprachkonstrukts, der immer erforderlich ist, unabhängig davon, ob Optionen aktiviert oder deaktiviert sind.) Die Option wird nur auf diese Gruppe angewendet. Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

  Dies wird im folgenden Beispiel veranschaulicht. Dabei werden Inlineoptionen in einem Gruppierungskonstrukt verwendet, um Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung zu ermöglichen und das Ignorieren von Leerzeichenmustern zu aktivieren, wenn Wörter identifiziert werden, die mit dem Buchstaben "d" beginnen.

  ```csharp
  string pattern = @"\b(?ix: d \w+)\s";
  string input = "Dogs are decidedly good pets.";
  
  foreach (Match match in Regex.Matches(input, pattern))
     Console.WriteLine("'{0}// found at index {1}.", match.Value, match.Index);
  // The example displays the following output:
  //    'Dogs // found at index 0.
  //    'decidedly // found at index 9.      
  ```

  ```vb
  Dim pattern As String = "\b(?ix: d \w+)\s"
  Dim input As String = "Dogs are decidedly good pets."

  For Each match As Match In Regex.Matches(input, pattern)
     Console.WriteLine("'{0}' found at index {1}.", match.Value, match.Index)
  Next
  ' The example displays the following output:
  '    'Dogs ' found at index 0.
  '    'decidedly ' found at index 9. 
  ```


Wenn Optionen inline angegeben werden, werden diese Optionen durch ein Minuszeichen (-) vor einer Option oder einer Gruppe von Optionen deaktiviert. Beispielsweise aktiviert das Inlinekonstrukt **(?ix-ms)** die Optionen [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) und [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) und deaktiviert die Optionen [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) und [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Alle Optionen für reguläre Ausdrücke sind standardmäßig deaktiviert.

> [!NOTE]
> Wenn die Optionen für reguläre Ausdrücke im options-Parameter eines Konstruktors oder Methodenaufrufs in Konflikt mit den Optionen stehen, die inline in einem Muster für reguläre Ausdrücke angegeben wurden, werden die Inlineoptionen verwendet.
 

Die folgenden fünf Optionen für reguläre Ausdrücke können sowohl mit dem *options*-Parameter als auch inline festgelegt werden:

* [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)

* [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)

* [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline)

* [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)

* [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace)

Die folgenden fünf Optionen für reguläre Ausdrücke können mit dem *options*-Parameter, jedoch nicht inline festgelegt werden:

* [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None)

* [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)

* [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)

* [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant)

* [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript)

## <a name="determining-the-options"></a>Ermitteln der Optionen

Sie können ermitteln, welche Optionen für ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt bei seiner Instanziierung bereitgestellt wurden, indem Sie den Wert der schreibgeschützten [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options)-Eigenschaft abrufen.

Um das Vorhandensein einer anderen Option als [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) zu prüfen, führen Sie eine AND-Operation mit dem Wert der [Regex.Options](xref:System.Text.RegularExpressions.Regex.Options)-Eigenschaft und dem [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Wert aus, für den Sie sich interessieren. Anschließend testen Sie, ob das Ergebnis diesem [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Wert entspricht. Im folgenden Beispiel wird getestet, ob die [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option festgelegt wurde. 

```csharp
if ((rgx.Options & RegexOptions.IgnoreCase) == RegexOptions.IgnoreCase)
   Console.WriteLine("Case-insensitive pattern comparison.");
else
   Console.WriteLine("Case-sensitive pattern comparison.");
```

```vb
If (rgx.Options And RegexOptions.IgnoreCase) = RegexOptions.IgnoreCase Then
   Console.WriteLine("Case-insensitive pattern comparison.")
Else
   Console.WriteLine("Case-sensitive pattern comparison.")
End If 
```

Um auf [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) zu testen, ermitteln Sie, ob der Wert der [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Eigenschaft dem Wert [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) entspricht, wie im folgenden Beispiel veranschaulicht. 

```csharp
if (rgx.Options == RegexOptions.None)
   Console.WriteLine("No options have been set.");
```

```vb
If rgx.Options = RegexOptions.None Then
   Console.WriteLine("No options have been set.")
End If
```

In den folgenden Abschnitten werden die Optionen aufgeführt, die von regulären .NET-Ausdrücken unterstützt werden. 

## <a name="default-options"></a>Standardoptionen

Die [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None)-Option gibt an, dass keine Optionen angegeben wurden, und das Modul für reguläre Ausdrücke verwendet sein Standardverhalten. Hierzu gehören folgende Elemente:

* Das Muster wird kanonisch und nicht als regulärer ECMAScript-Ausdruck interpretiert.

* Das Muster eines regulären Ausdrucks wird von links nach rechts mit der Eingabezeichenfolge verglichen.

* Bei Vergleichen wird die Groß-/Kleinschreibung berücksichtigt.

* Die Sprachelemente **^** und **$** finden eine Entsprechung für den Anfang und das Ende der Eingabezeichenfolge.

* Das Sprachelement **.** entspricht jedem Zeichen außer **\n**.

* Alle Leerstellen in einem Muster eines regulären Ausdrucks werden als literale Leerzeichen interpretiert.

* Die Konventionen der aktuellen Kultur werden zum Vergleichen des Musters mit der Eingabezeichenfolge verwendet. 

* Erfassungsgruppen im Muster eines regulären Ausdrucks sind implizit und explizit. 

> [!NOTE]
> Die Option [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) besitzt keine Inlineentsprechung. Wenn reguläre Ausdrucksoptionen inline übernommen werden, wird das Standardverhalten auf optionsweiser Basis durch Deaktivieren einer bestimmten Option wiederhergestellt. `(?i)` aktiviert z. B. Vergleiche, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, und `(?-i)` stellt das Standardverhalten mit Beachtung der Groß-/Kleinschreibung wieder her.
 
Da die Option [RegexOptions.None](xref:System.Text.RegularExpressions.RegexOptions.None) das Standardverhalten des Moduls für reguläre Ausdrücke darstellt, wird sie selten explizit in einem Methodenaufruf angegeben. Stattdessen wird ein Konstruktor oder eine statische Mustervergleichsmethode ohne options-Parameter aufgerufen.

## <a name="caseinsensitive-matching"></a>Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung

Die Option [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) oder die Inlineoption **i** stellt die Suche nach Übereinstimmungen ohne Berücksichtigung von Groß-/Kleinschreibung bereit. Standardmäßig werden die Groß-/Kleinschreibungskonventionen der aktuellen Kultur verwendet.

Im folgenden Beispiel wird das Muster eines regulären Ausdrucks `\bthe\w*\b` definiert, das eine Entsprechung für alle Wörter findet, die mit "the" beginnen. Da der erste Aufruf der Match-Methode beim Vergleich standardmäßig die Groß-/Kleinschreibung beachtet, gibt die Ausgabe an, dass zur Zeichenfolge „The“ am Anfang des Satzes keine Übereinstimmung gefunden wurde. Eine Entsprechung wird gefunden, wenn die [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit der Einstellung [IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) für die Optionen aufgerufen wird. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bthe\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bthe\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern, _
                                               RegexOptions.IgnoreCase)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

Im folgenden Beispiel wird das Muster für reguläre Ausdrücke aus dem vorherigen Beispiel so geändert, dass Inlineoptionen anstelle des *options*-Parameters verwendet werden, um einen Vergleich ohne Berücksichtigung von Groß- und Kleinschreibung bereitzustellen. Das erste Muster definiert die Option zum Ignorieren der Groß-/Kleinschreibung in einem Gruppierungskonstrukt, das in der Zeichenfolge "the" nur für den Buchstaben "t" gilt. Da das Optionskonstrukt am Anfang des Musters auftritt, wendet das zweite Muster die Option zur Missachtung der Groß-/Kleinschreibung auf den gesamten regulären Ausdruck an.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?i:t)he\w*\b";
      string input = "The man then told them about that event.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);

      Console.WriteLine();
      pattern = @"(?i)\bthe\w*\b";
      foreach (Match match in Regex.Matches(input, pattern, 
                                            RegexOptions.IgnoreCase))
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
//       
//       Found The at index 0.
//       Found then at index 8.
//       Found them at index 18.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?i:t)he\w*\b"
      Dim input As String = "The man then told them about that event."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
      Console.WriteLine()
      pattern = "(?i)\bthe\w*\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found {0} at index {1}.", match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
'       
'       Found The at index 0.
'       Found then at index 8.
'       Found them at index 18.
```

## <a name="multiline-mode"></a>Mehrzeilenmodus

Die Option [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) oder die Inlineoption **m** ermöglicht dem Modul für reguläre Ausdrücke das Verarbeiten einer Eingabezeichenfolge, die aus mehreren Zeilen besteht. Sie ändert die Bedeutung der Sprachelemente **^** und **$**, sodass sie jeweils dem Anfang und dem Ende einer Zeile und nicht nur dem Anfang und dem Ende der Eingabezeichenfolge entsprechen. 

Standardmäßig findet **$** nur eine Entsprechung für das Ende der Eingabezeichenfolge. Wenn Sie die Option [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) angeben, entspricht diese entweder dem Zeilenumbruchzeichen (**\n**) oder dem Ende der Eingabezeichenfolge. Sie entspricht jedoch nicht der Kombination aus Wagenrücklauf- und Zeilenvorschubzeichen. Um dafür erfolgreich eine Entsprechung zu finden, verwenden Sie den Teilausdruck **\r?$** statt nur **$**. 

Im folgenden Beispiel werden die Namen und Ergebnisse von Bowlern extrahiert und einer Sammlung [SortedList&lt;TKey, TValue&gt;](xref:System.Collections.Generic.SortedList%602) hinzugefügt, in der sie in absteigender Reihenfolge sortiert werden. Die [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode wird zweimal aufgerufen. Im ersten Methodenaufruf ist der reguläre Ausdruck `^(\w+)\s(\d+)$`. Es werden keine Optionen festgelegt. Wie die Ausgabe zeigt, werden keine Übereinstimmungen gefunden, da das Modul für reguläre Ausdrücke das Eingabemuster nicht mit dem Anfang und dem Ende der Eingabezeichenfolge vergleichen kann. Im zweiten Methodenaufruf wird der reguläre Ausdruck in `^(\w+)\s(\d+)\r?$` geändert, und die Optionen werden auf [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) festgelegt. Wie die Ausgabe zeigt, werden die Namen und Ergebnisse erfolgreich abgeglichen, und die Ergebnisse werden in absteigender Reihenfolge angezeigt.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" + 
                     "Sam 208\n" + 
                     "Allison 211\n" + 
                     "Gwen 171\n"; 
      string pattern = @"^(\w+)\s(\d+)$";
      bool matched = false;

      Console.WriteLine("Without Multiline option:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);
         matched = true;
      }
      if (! matched)
         Console.WriteLine("   No matches.");
      Console.WriteLine();

      // Redefine pattern to handle multiple lines.
      pattern = @"^(\w+)\s(\d+)\r*$";
      Console.WriteLine("With multiline option:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Int32.Parse(match.Groups[2].Value), (string) match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y)
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//   Without Multiline option:
//      No matches.
//   
//   With multiline option:
//   Allison: 211
//   Sam: 208
//   Gwen: 171
//   Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "^(\w+)\s(\d+)$"
      Dim matched As Boolean = False

      Console.WriteLine("Without Multiline option:")
      For Each match As Match In Regex.Matches(input, pattern)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
         matched = True
      Next
      If Not matched Then Console.WriteLine("   No matches.")
      Console.WriteLine()

      ' Redefine pattern to handle multiple lines.
      pattern = "^(\w+)\s(\d+)\r*$"
      Console.WriteLine("With multiline option:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Without Multiline option:
'       No matches.
'    
'    With multiline option:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

Das Muster für reguläre Ausdrücke `^(\w+)\s(\d+)\r*$` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`^` | Am Anfang der Zeile beginnen.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(\d+)` | Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die zweite Erfassungsgruppe.
`\r?` | Entspricht null oder mehr Wagenrücklaufzeichen.
`$` | Ende am Ende der Zeile.
 
Das folgende Beispiel entspricht dem vorherigen, abgesehen davon, dass zum Festlegen der Mehrzeilenoption die Inlineoption **(?m)** verwendet wird.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      SortedList<int, string> scores = new SortedList<int, string>(new DescendingComparer<int>());

      string input = "Joe 164\n" +  
                     "Sam 208\n" +  
                     "Allison 211\n" +  
                     "Gwen 171\n"; 
      string pattern = @"(?m)^(\w+)\s(\d+)\r*$";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
         scores.Add(Convert.ToInt32(match.Groups[2].Value), match.Groups[1].Value);

      // List scores in descending order. 
      foreach (KeyValuePair<int, string> score in scores)
         Console.WriteLine("{0}: {1}", score.Value, score.Key);
   }
}

public class DescendingComparer<T> : IComparer<T>
{
   public int Compare(T x, T y) 
   {
      return Comparer<T>.Default.Compare(x, y) * -1;       
   }
}
// The example displays the following output:
//    Allison: 211
//    Sam: 208
//    Gwen: 171
//    Joe: 164
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim scores As New SortedList(Of Integer, String)(New DescendingComparer(Of Integer)())

      Dim input As String = "Joe 164" + vbCrLf + _
                            "Sam 208" + vbCrLf + _
                            "Allison 211" + vbCrLf + _
                            "Gwen 171" + vbCrLf
      Dim pattern As String = "(?m)^(\w+)\s(\d+)\r*$"

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         scores.Add(CInt(match.Groups(2).Value), match.Groups(1).Value)
      Next
      ' List scores in descending order. 
      For Each score As KeyValuePair(Of Integer, String) In scores
         Console.WriteLine("{0}: {1}", score.Value, score.Key)
      Next
   End Sub
End Module

Public Class DescendingComparer(Of T) : Implements IComparer(Of T)
   Public Function Compare(x As T, y As T) As Integer _
          Implements IComparer(Of T).Compare
      Return Comparer(Of T).Default.Compare(x, y) * -1       
   End Function
End Class
' The example displays the following output:
'    Allison: 211
'    Sam: 208
'    Gwen: 171
'    Joe: 164
```

## <a name="singleline-mode"></a>Einzeilenmodus

Die Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) bzw. die Inlineoption „s“ sorgt dafür, dass das Modul für reguläre Ausdrücke die Eingabezeichenfolge so behandelt, als ob sie aus einer einzigen Zeile besteht. Hierzu wird das Verhalten des Sprachelements Punkt (**.**) geändert, sodass dieser jedem Zeichen entspricht, anstatt jedem Zeichen außer dem Zeilenumbruchzeichen **\n** oder \u000A.

Im folgenden Beispiel wird veranschaulicht, wie sich das Verhalten des Sprachelements . ändert, wenn Sie die Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) verwenden. Der reguläre `^.+`-Ausdruck beginnt am Anfang der Zeichenfolge und stimmt mit jedem Zeichen überein. Standardmäßig endet die Übereinstimmung am Ende der ersten Zeile. Das Muster für reguläre Ausdrücke stimmt mit dem Wagenrücklaufzeichen (**\r** oder \u000D), jedoch nicht mit **\n** überein. Da die gesamte Eingabezeichenfolge von der Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) als einzelne Zeile interpretiert wird, wird für jedes enthaltene Zeichen ein Abgleich vorgenommen, einschließlich **\n**.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));

      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Singleline))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r
//       
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^.+"
      Dim input As String = "This is one line and" + vbCrLf + "this is the second."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.SingleLine)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
   End Sub
End Module
' The example displays the following output:
'       This\ is\ one\ line\ and\r
'       
'       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

Das folgende Beispiel entspricht dem vorherigen, abgesehen davon, dass zum Aktivieren des Einzelzeilenmodus die Inlineoption **(?s)** verwendet wird. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {      
      string pattern = "(?s)^.+";
      string input = "This is one line and" + Environment.NewLine + "this is the second.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(Regex.Escape(match.Value));
   }
}
// The example displays the following output:
//       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?s)^.+"
      Dim input As String = "This is one line and" + vbCrLf + "this is the second."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(Regex.Escape(match.Value))
      Next
   End Sub
End Module
' The example displays the following output:
'       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
```

## <a name="explicit-captures-only"></a>Nur explizite Erfassungen

Standardmäßig werden Erfassungsgruppen durch die Verwendung von Klammern im Muster eines regulären Ausdrucks definiert. Benannten Gruppen wird von der Sprachoption **(?<**_name_**>** _teilausdruck_**)** ein Name oder eine Zahl zugewiesen, wohingegen auf unbenannte Gruppen über den Index zugegriffen werden kann. Im [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt gehen unbenannte Gruppen benannten Gruppen voraus. 

Gruppierungskonstrukte werden häufig nur verwendet, um Quantifizierer für mehrere Sprachelemente zu übernehmen, und die erfassten Teilzeichenfolgen sind nicht von Bedeutung. Wenn beispielsweise der reguläre Ausdruck wie folgt lautet:

```
\b\(?((\w+),?\s?)+[\.!?]\)?
```

und nur dazu dienen soll, Sätze mit einem Punkt, Ausrufezeichen oder Fragezeichen am Ende aus einem Dokument zu extrahieren, ist nur der resultierende Satz von Interesse (der durch das [Match](xref:System.Text.RegularExpressions.Match)-Objekt dargestellt wird). Die einzelnen Wörter in der Auflistung sind irrelevant. 

Erfassungsgruppen, die anschließend nicht verwendet werden, können speicherintensiv sein, da das Modul für reguläre Ausdrücke sowohl das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)- als auch das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Sammlungsobjekt auffüllen muss. Als Alternative können Sie entweder die [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)-Option oder die **n**-Inlineoption verwenden, um anzugeben, dass die einzigen gültigen Erfassungen explizit benannte oder nummerierte Gruppen sind, die durch das Konstrukt **(?<**_name_**>** _teilausdruck_**)** angegeben werden. 

Das folgende Beispiel zeigt Informationen zu den Übereinstimmungen an, die vom Muster für reguläre Ausdrücke `\b\(?((\w+),?\s?)+[\.!?]\)?` zurückgegeben werden, wenn die [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32))-Methode mit und ohne die [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)-Option aufgerufen wird. Wie die Ausgabe des ersten Methodenaufrufs zeigt, füllt das Modul für reguläre Ausdrücke das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Sammlungsobjekt und das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Sammlungsobjekt vollständig mit Informationen zu erfassten Teilzeichenfolgen auf. Da die zweite Methode mit Optionen mit dem Wert [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) aufgerufen wird, werden keine Informationen zu Gruppen erfasst.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";
      Console.WriteLine("With implicit captures:");
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
      Console.WriteLine();
      Console.WriteLine("With explicit captures only:");
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.ExplicitCapture))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//    With implicit captures:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//       Group 1: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//       Group 2: sentence
//          Capture 0: This
//          Capture 1: is
//          Capture 2: the
//          Capture 3: first
//          Capture 4: sentence
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//       Group 1: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//       Group 2: masterpiece
//          Capture 0: Is
//          Capture 1: it
//          Capture 2: the
//          Capture 3: beginning
//          Capture 4: of
//          Capture 5: a
//          Capture 6: literary
//          Capture 7: masterpiece
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//       Group 1: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//       Group 2: not
//          Capture 0: I
//          Capture 1: think
//          Capture 2: not
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
//       Group 1: paragraph
//          Capture 0: Instead,
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//       Group 2: paragraph
//          Capture 0: Instead
//          Capture 1: it
//          Capture 2: is
//          Capture 3: a
//          Capture 4: nonsensical
//          Capture 5: paragraph
//    
//    With explicit captures only:
//    The match: This is the first sentence.
//       Group 0: This is the first sentence.
//          Capture 0: This is the first sentence.
//    The match: Is it the beginning of a literary masterpiece?
//       Group 0: Is it the beginning of a literary masterpiece?
//          Capture 0: Is it the beginning of a literary masterpiece?
//    The match: I think not.
//       Group 0: I think not.
//          Capture 0: I think not.
//    The match: Instead, it is a nonsensical paragraph.
//       Group 0: Instead, it is a nonsensical paragraph.
//          Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?((?>\w+),?\s?)+[\.!?]\)?"
      Console.WriteLine("With implicit captures:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
      Console.WriteLine()
      Console.WriteLine("With explicit captures only:")
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.ExplicitCapture)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'    With implicit captures:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'       Group 1: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'       Group 2: sentence
'          Capture 0: This
'          Capture 1: is
'          Capture 2: the
'          Capture 3: first
'          Capture 4: sentence
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'       Group 1: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'       Group 2: masterpiece
'          Capture 0: Is
'          Capture 1: it
'          Capture 2: the
'          Capture 3: beginning
'          Capture 4: of
'          Capture 5: a
'          Capture 6: literary
'          Capture 7: masterpiece
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'       Group 1: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'       Group 2: not
'          Capture 0: I
'          Capture 1: think
'          Capture 2: not
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
'       Group 1: paragraph
'          Capture 0: Instead,
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'       Group 2: paragraph
'          Capture 0: Instead
'          Capture 1: it
'          Capture 2: is
'          Capture 3: a
'          Capture 4: nonsensical
'          Capture 5: paragraph
'    
'    With explicit captures only:
'    The match: This is the first sentence.
'       Group 0: This is the first sentence.
'          Capture 0: This is the first sentence.
'    The match: Is it the beginning of a literary masterpiece?
'       Group 0: Is it the beginning of a literary masterpiece?
'          Capture 0: Is it the beginning of a literary masterpiece?
'    The match: I think not.
'       Group 0: I think not.
'          Capture 0: I think not.
'    The match: Instead, it is a nonsensical paragraph.
'       Group 0: Instead, it is a nonsensical paragraph.
'          Capture 0: Instead, it is a nonsensical paragraph.
```

Das Muster für reguläre Ausdrücke `\b\(?((?>\w+),?\s?)+[\.!?]\)?` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`\b` | Bei einer Wortgrenze beginnen.
`\(?` | Sucht nach einer Übereinstimmung mit null oder einem Vorkommen der öffnenden Klammer ("(").
`(?>\w+),?` | Sucht nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von keinem oder einem Komma. Bei übereinstimmenden Wortzeichen findet keine Rückverfolgung statt.
`\s?` | Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.
`((\w+),?\s?)+` | Entspricht der Kombination von mindestens einem Wortzeichen gefolgt von keinem oder einem Komma und keinem oder einem Leerzeichen (ein- oder mehrfach).
`[\.!?]\)?` | Entspricht jedem der drei Interpunktionszeichen, gefolgt von keiner oder einer schließenden Klammer (")").
 
Sie können auch das **(?n)**-Inlineelement verwenden, um automatische Erfassungen zu unterdrücken. Im folgenden Beispiel wird das vorherige Muster für reguläre Ausdrücke so geändert, dass das Inlineelement **(?n)** anstelle der Option [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture) verwendet wird.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?n)\b\(?((?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

Abschließend können Sie mit dem Inlinegruppenelement **(?n:)** automatische Erfassungen gruppenweise unterdrücken. Im folgenden Beispiel wird das vorherige Muster geändert, sodass unbenannte Erfassungen in der äußeren Gruppe `((?>\w+),?\s?)` unterdrückt werden. Beachten Sie, dass dadurch auch unbenannte Erfassungen in der inneren Gruppe unterdrückt werden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("The match: {0}", match.Value);
         int groupCtr = 0;
         foreach (Group group in match.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value);
            groupCtr++;
            int captureCtr = 0;
            foreach (Capture capture in group.Captures)
            {
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value);
               captureCtr++;
            }
         }
      }
   }
}
// The example displays the following output:
//       The match: This is the first sentence.
//          Group 0: This is the first sentence.
//             Capture 0: This is the first sentence.
//       The match: Is it the beginning of a literary masterpiece?
//          Group 0: Is it the beginning of a literary masterpiece?
//             Capture 0: Is it the beginning of a literary masterpiece?
//       The match: I think not.
//          Group 0: I think not.
//             Capture 0: I think not.
//       The match: Instead, it is a nonsensical paragraph.
//          Group 0: Instead, it is a nonsensical paragraph.
//             Capture 0: Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b\(?(?n:(?>\w+),?\s?)+[\.!?]\)?"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("The match: {0}", match.Value)
         Dim groupCtr As Integer = 0
         For Each group As Group In match.Groups
            Console.WriteLine("   Group {0}: {1}", groupCtr, group.Value)
            groupCtr += 1
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               Console.WriteLine("      Capture {0}: {1}", captureCtr, capture.Value)
               captureCtr += 1
            Next
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       The match: This is the first sentence.
'          Group 0: This is the first sentence.
'             Capture 0: This is the first sentence.
'       The match: Is it the beginning of a literary masterpiece?
'          Group 0: Is it the beginning of a literary masterpiece?
'             Capture 0: Is it the beginning of a literary masterpiece?
'       The match: I think not.
'          Group 0: I think not.
'             Capture 0: I think not.
'       The match: Instead, it is a nonsensical paragraph.
'          Group 0: Instead, it is a nonsensical paragraph.
'             Capture 0: Instead, it is a nonsensical paragraph.
```

## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke

Standardmäßig werden reguläre Ausdrücke in .NET interpretiert. Wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziiert oder eine statische [Regex](xref:System.Text.RegularExpressions.Regex)-Methode aufgerufen wird, wird das Muster für reguläre Ausdrücke in einen Satz benutzerdefinierter Opcodes analysiert, und ein Interpreter führt den regulären Ausdruck mithilfe dieser Opcodes aus. Dabei wird ein Kompromiss eingegangen: Der Aufwand für die Initialisierung des Moduls für reguläre Ausdrücke wird auf Kosten der Laufzeitleistung minimiert.

Sie können kompilierte statt interpretierter regulärer Ausdrücke mit der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option verwenden. Wenn in diesem Fall ein Muster an das Modul für reguläre Ausdrücke übergeben wird, wird es in einen Satz von Opcodes aufgeschlüsselt und dann nach MSIL (Microsoft Intermediate Language) konvertiert, sodass es direkt an die Common Language Runtime übergeben werden kann. Kompilierte reguläre Ausdrücke maximieren die Laufzeitleistung auf Kosten der Initialisierungszeit.

> [!NOTE]
> Ein regulärer Ausdruck kann nur kompiliert werden, indem der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Wert an den options-Parameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder einer statischen Mustervergleichsmethode übergeben wird. Es besteht keine Verfügbarkeit als Inlineoption. 
 

Sie können kompilierte reguläre Ausdrücke in Aufrufen von statischen regulären Ausdrücken und solchen für Instanzen verwenden. In statischen regulären Ausdrücken wird die [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option an den options-Parameter der Vergleichsmethode des regulären Ausdrucks übergeben. In regulären Instanzausdrücken wird sie an den options-Parameter des [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors übergeben. In beiden Fällen führt dies zu einer besseren Leistung. 

Diese Verbesserung der Leistung tritt jedoch nur unter den folgenden Bedingungen auf:

* Ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt, das einen bestimmten regulären Ausdruck darstellt, wird in mehreren Aufrufen regulärer Ausdrucksmuster-Vergleichsmethoden verwendet.

* Das [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt darf den Gültigkeitsbereich nicht verlassen, daher kann es wiederverwendet werden.

* Ein statischer regulärer Ausdruck wird in mehreren Aufrufen regulärer Ausdrucksmustervergleichsmethoden verwendet. (Die Leistungsverbesserung ist möglich, da reguläre in statischen Methodenaufrufen verwendete Ausdrücke vom Modul für reguläre Ausdrücke zwischengespeichert werden.) 

## <a name="ignore-white-space"></a>Leerstellen ignorieren

Standardmäßig werden Leerstellen in einem Muster eines regulären Ausdrucks interpretiert. Das Modul für reguläre Ausdrücke sucht dann nach einem entsprechenden Leerstellenzeichen in der Eingabezeichenfolge. Daher sind die regulären Ausdrücke `"\b\w+\s"` und `"\b\w+ "` in etwa äquivalente reguläre Ausdrücke. Außerdem wird das Nummernzeichen (**#**), wenn es in einem Muster für reguläre Ausdrücke gefunden wird, als Literalzeichen für den Abgleich interpretiert.

Die Option [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) oder die Inlineoption **x** ändert dieses Standardverhalten wie folgt:

* Leerstellen ohne Escapezeichen im Muster eines regulären Ausdrucks werden ignoriert. Um Teil eines Musters für reguläre Ausdrücke zu sein, müssen Leerzeichen mit Escapezeichen versehen werden (z.B. **\s** oder „**\** “).

* Das Nummernzeichen (**#**) wird als Anfang eines Kommentars interpretiert, nicht als Literalzeichen. Der gesamte Text im Muster für reguläre Ausdrücke vom Zeichen **#** bis zum Ende der Zeichenfolge wird als Kommentar interpretiert.

In den folgenden Fällen werden Leerzeichen in regulären Ausdrücken jedoch nicht ignoriert, auch wenn Sie die Option [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) verwenden: 

* Leerzeichen in einer Zeichenklasse werden stets literal interpretiert. Der reguläre Ausdruck `[ .,;:]` findet z. B. ein einzelnes Leerstellenzeichen, Punkt, Komma, Semikolon oder einen Doppelpunkt. 

* Leerzeichen sind innerhalb von in Klammern gesetzten Quantifizierern wie **{**_n_**}**, **{**_n_**,}** und **{**_n_**,**_m_**}** nicht zulässig. Das Muster für reguläre Ausdrücke **\d{1. 3}** findet z.B. keine Übereinstimmung mit Ziffernsequenzen von einer bis zu drei Ziffern, da es ein Leerzeichen enthält. 

* Leerzeichen sind in Zeichenfolgen, die Sprachelemente einleiten, nicht zulässig. Zum Beispiel: 

    * Das Sprachelement **(?:**_teilausdruck_**)** stellt eine nicht erfassende Gruppe dar, und der Teil **(?:** des Elements darf keine eingebetteten Leerzeichen enthalten. Das Muster **(? :**_teilausdruck_**)** löst zur Laufzeit [ArgumentException](xref:System.ArgumentException) aus, da das Modul für reguläre Ausdrücke das Muster nicht analysieren kann, und das Muster **(? :**_teilausdruck_**)** findet keine Übereinstimmung mit *teilausdruck*.

    * Das Sprachelement **\p{**_name_**}**, das für eine Unicode-Kategorie oder einen benannten Block steht, darf im Teil **\p{** des Elements kein eingebettetes Leerzeichen enthalten. Falls Sie trotzdem ein Leerzeichen einfügen, löst das Element zur Laufzeit eine [ArgumentException](xref:System.ArgumentException) aus. 

Durch das Aktivieren dieser Option werden reguläre Ausdrücke vereinfacht, die oft schwierig zu analysieren und zu verstehen sind. Dadurch wird Lesbarkeit verbessert, und es wird möglich, einen regulären Ausdruck zu dokumentieren. 

Im folgenden Beispiel wird das folgende Muster des regulären Ausdrucks definiert:

`\b \(? ( (?>\w+) ,?\s? )+ [\.!?] \)? # Matches an entire sentence`.

Dieses Muster ist dem im Abschnitt [Nur explizite Erfassungen](#explicit-captures-only) definierten Muster ähnlich, nur dass mithilfe der Option [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) Leerzeichen im Muster ignoriert werden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"\b\(?((?>\w+),?\s?)+[\.!?]\)?";

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnorePatternWhitespace)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

Im folgenden Beispiel wird die Inlineoption **(?x)** verwendet, um Leerzeichen im Muster zu ignorieren.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is the first sentence. Is it the beginning " + 
                     "of a literary masterpiece? I think not. Instead, " + 
                     "it is a nonsensical paragraph.";
      string pattern = @"(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence.";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       This is the first sentence.
//       Is it the beginning of a literary masterpiece?
//       I think not.
//       Instead, it is a nonsensical paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is the first sentence. Is it the beginning " + _
                            "of a literary masterpiece? I think not. Instead, " + _
                            "it is a nonsensical paragraph."
      Dim pattern As String = "(?x)\b \(? ( (?>\w+) ,?\s? )+  [\.!?] \)? # Matches an entire sentence."

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       This is the first sentence.
'       Is it the beginning of a literary masterpiece?
'       I think not.
'       Instead, it is a nonsensical paragraph.
```

## <a name="righttoleft-mode"></a>Rechts-nach-links-Modus

Standardmäßig sucht das Modul für reguläre Ausdrücke von links nach rechts. Sie können mit der Option [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft) die Suchrichtung umkehren. Die Suche startet automatisch bei der Position des letzten Zeichens der Zeichenfolge. Bei Mustervergleichsmethoden, die einen Parameter für die Anfangsposition enthalten, wie z.B. [Regex.Match(String, Int32)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.Int32)), ist die Anfangsposition der Index der am weitesten rechts stehenden Zeichenposition, bei der die Suche beginnt. 

> [!NOTE]
> Der Mustermodus von rechts nach links ist nur verfügbar, wenn der [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)-Wert an den options-Parameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder einer statischen Mustervergleichsmethode übergeben wird. Es besteht keine Verfügbarkeit als Inlineoption. 
 

Die [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)-Option ändert nur die Suchrichtung; sie interpretiert das Muster für reguläre Ausdrücke nicht von rechts nach links. Der reguläre Ausdruck `\bb\w+\s` findet z. B. eine Entsprechung für Wörter, die mit dem Buchstaben "b" beginnen und von einem Leerstellenzeichen gefolgt sind. Im folgenden Beispiel besteht die Eingabezeichenfolge aus drei Wörtern, die ein oder mehrere "b"-Zeichen enthalten. Das erste Wort beginnt mit "b", das zweite endet mit "b", und das dritte enthält zwei "b"-Zeichen im Wortinnern. Wie die Ausgabe des Beispiels zeigt, stimmt nur das erste Wort mit dem Muster des regulären Ausdrucks überein. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bb\w+\s";
      string input = "builder rob rabble";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.RightToLeft))
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);     
   }
}
// The example displays the following output:
//       'builder ' found at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bb\w+\s"
      Dim input As String = "builder rob rabble"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.RightToLeft)
         Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)     
      Next
   End Sub
End Module
' The example displays the following output:
'       'builder ' found at position 0.
```

Beachten Sie auch, dass die Lookaheadassertion (das **(?**=_teilausdruck_**)**-Sprachelement) und die Lookbehindassertion (das **(?<**=_subexpression_**)**-Sprachelement) die Richtung nicht ändern. Die Lookaheadassertionen prüfen nach rechts, die Lookbehindassertionen nach links. Der reguläre Ausdruck `(?<=\d{1,2}\s)\w+,?\s\d{4}` testet z. B. mithilfe der Lookbehindassertion auf ein Datum, das einem Monatsnamen vorausgeht. Der reguläre Ausdruck gleicht dann Monat und Jahr ab. Informationen zu Lookahead- und Lookbehindassertionen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "1 May 1917", "June 16, 2003" };
      string pattern = @"(?<=\d{1,2}\s)\w+,?\s\d{4}";

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern, RegexOptions.RightToLeft);
         if (match.Success)
            Console.WriteLine("The date occurs in {0}.", match.Value);
         else
            Console.WriteLine("{0} does not match.", input);
      }
   }
}
// The example displays the following output:
//       The date occurs in May 1917.
//       June 16, 2003 does not match.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "1 May 1917", "June 16, 2003" }
      Dim pattern As String = "(?<=\d{1,2}\s)\w+,?\s\d{4}"

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern, RegexOptions.RightToLeft)
         If match.Success Then
            Console.WriteLine("The date occurs in {0}.", match.Value)
         Else
            Console.WriteLine("{0} does not match.", input)
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       The date occurs in May 1917.
'       June 16, 2003 does not match.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`(?<=\d{1,2}\s)` | Dem Anfang der Übereinstimmung müssen eine oder zwei von einem Leerzeichen gefolgte Dezimalstellen vorangestellt sein.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`,?` | Entspricht keinem oder einem Kommazeichen.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`\d{4}` | Entsprechung für vier Dezimalstellen finden.
 
## <a name="ecmascript-matching-behavior"></a>ECMAScript-Vergleichsverhalten

Standardmäßig verwendet das Modul für reguläre Ausdrücke das kanonische Verhalten, wenn ein Muster eines regulären Ausdrucks mit dem Eingabetext verglichen wird. Sie können jedoch das Modul für reguläre Ausdrücke anweisen, das ECMAScript-Vergleichsverhalten zu verwenden, indem Sie die [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript)-Option angeben. 

> [!NOTE]
> Das ECMAScript-kompatible Verhalten ist nur verfügbar, wenn der [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript)-Wert an den options-Parameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder einer statischen Mustervergleichsmethode übergeben wird. Es besteht keine Verfügbarkeit als Inlineoption. 
 
Die Option [RegexOptions.ECMAScript](xref:System.Text.RegularExpressions.RegexOptions.ECMAScript) kann nur mit den Optionen [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) und [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) kombiniert werden. Die Verwendung einer anderen Option in einem regulären Ausdruck führt zu einer [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException).

Das Verhalten von ECMAScript und kanonischen regulären Ausdrücke unterscheidet sich in drei Bereichen: Zeichenklassensyntax, bei Selbstverweisen von Erfassungsgruppen sowie bei der Interpretation von Oktalwerten und Rückverweisen. 

* Zeichenklassensyntax. Da kanonische reguläre Ausdrücke im Gegensatz zu ECMAScript Unicode unterstützen, weisen Zeichenklassen in ECMAScript eine beschränktere Syntax auf, und einige Zeichenklassensprachelemente haben eine andere Bedeutung. ECMAScript unterstützt z.B. keine Sprachelemente wie die Kategorie- oder Blockelemente *\p* und **\P** von Unicode. Entsprechend ist das **\w**-Element, das einem Wortzeichen entspricht, äquivalent zur **[a-zA-Z_0-9]**-Zeichenklasse beim Verwenden von ECMAScript bzw. äquivalent zu **[\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]** beim Verwenden des kanonischen Verhaltens. Weitere Informationen finden Sie unter [Zeichenklassen in regulären Ausdrücken](classes.md).

  Im folgenden Beispiel wird der Unterschied zwischen kanonischen und ECMAScript-Mustervergleichen veranschaulicht. Dabei wird ein regulärer Ausdruck, `\b(\w+\s*)+`, definiert, der eine Entsprechung für Wörter findet, denen Leerstellenzeichen folgen. Die Eingabe besteht aus zwei Zeichenfolgen, einer mit dem lateinischen Zeichensatz und einer mit dem kyrillischen Zeichensatz. Wie die Ausgabe zeigt, findet der Aufruf der [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode, die den ECMAScript-Abgleich verwendet, keine Entsprechung für die kyrillischen Wörter, wohingegen der Methodenaufruf, der einen kanonischen Vergleich verwendet, eine Entsprechung für diese Wörter findet. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;
  
  public class Example
  {
     public static void Main()
     {
        string[] values = { "целый мир", "the whole world" };
        string pattern = @"\b(\w+\s*)+";
        foreach (var value in values)
        {
           Console.Write("Canonical matching: ");
           if (Regex.IsMatch(value, pattern))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
  
           Console.Write("ECMAScript matching: ");
           if (Regex.IsMatch(value, pattern, RegexOptions.ECMAScript))
              Console.WriteLine("'{0}' matches the pattern.", value);
           else
              Console.WriteLine("{0} does not match the pattern.", value);
           Console.WriteLine();
        }
     }
  }
  // The example displays the following output:
  //       Canonical matching: 'целый мир' matches the pattern.
  //       ECMAScript matching: целый мир does not match the pattern.
  //       
  //       Canonical matching: 'the whole world' matches the pattern.
  //       ECMAScript matching: 'the whole world' matches the pattern.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim values() As String = { "целый мир", "the whole world" }
        Dim pattern As String = "\b(\w+\s*)+"
        For Each value In values
           Console.Write("Canonical matching: ")
           If Regex.IsMatch(value, pattern)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If

           Console.Write("ECMAScript matching: ")
           If Regex.IsMatch(value, pattern, RegexOptions.ECMAScript)
              Console.WriteLine("'{0}' matches the pattern.", value)
           Else
              Console.WriteLine("{0} does not match the pattern.", value)
           End If
           Console.WriteLine()
        Next
     End Sub
  End Module
  ' The example displays the following output:
  '       Canonical matching: 'целый мир' matches the pattern.
  '       ECMAScript matching: целый мир does not match the pattern.
  '       
  '       Canonical matching: 'the whole world' matches the pattern.
  '       ECMAScript matching: 'the whole world' matches the pattern.
  ```

* Auf sich selbst verweisende Erfassungsgruppen. Eine Aufzeichnungsklasse für einen regulären Ausdruck mit einem Rückverweis auf sich selbst muss mit jeder Aufzeichnungsiteration aktualisiert werden. Wie das folgende Beispiel zeigt, aktiviert diese Funktion den regulären Ausdruck `((a+)(\1) ?)+`, um eine Entsprechung für die Eingabezeichenfolge " aa aaaa aaaaaa " zu finden, wenn ECMAScript verwendet wird, jedoch nicht, wenn kanonische Vergleiche verwendet werden. 

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     static string pattern;
  
     public static void Main()
     {
        string input = "aa aaaa aaaaaa "; 
        pattern = @"((a+)(\1) ?)+";
  
        // Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern));

        // Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript));
     }   

     private static void AnalyzeMatch(Match m)
     {
        if (m.Success)
        {
           Console.WriteLine("'{0}' matches {1} at position {2}.",  
                             pattern, m.Value, m.Index);
           int grpCtr = 0;
           foreach (Group grp in m.Groups)
           {
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value);
              grpCtr++;
              int capCtr = 0;
              foreach (Capture cap in grp.Captures)
              {
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value);
                 capCtr++;
              }
           }
        }
        else
        {
           Console.WriteLine("No match found.");
        }   
        Console.WriteLine();
     }
  }
  // The example displays the following output:
  //    No match found.
  //    
  //    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  //       0: 'aa aaaa aaaaaa '
  //          0: 'aa aaaa aaaaaa '
  //       1: 'aaaaaa '
  //          0: 'aa '
  //          1: 'aaaa '
  //          2: 'aaaaaa '
  //       2: 'aa'
  //          0: 'aa'
  //          1: 'aa'
  //          2: 'aa'
  //       3: 'aaaa '
  //          0: ''
  //          1: 'aa '
  //          2: 'aaaa '
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Dim pattern As String

     Public Sub Main()
        Dim input As String = "aa aaaa aaaaaa " 
        pattern = "((a+)(\1) ?)+"
  
        ' Match input using canonical matching.
        AnalyzeMatch(Regex.Match(input, pattern))

        ' Match input using ECMAScript.
        AnalyzeMatch(Regex.Match(input, pattern, RegexOptions.ECMAScript))
     End Sub   

     Private Sub AnalyzeMatch(m As Match)
        If m.Success
           Console.WriteLine("'{0}' matches {1} at position {2}.", _ 
                             pattern, m.Value, m.Index)
           Dim grpCtr As Integer = 0
           For Each grp As Group In m.Groups
              Console.WriteLine("   {0}: '{1}'", grpCtr, grp.Value)
              grpCtr += 1
              Dim capCtr As Integer = 0
              For Each cap As Capture In grp.Captures
                 Console.WriteLine("      {0}: '{1}'", capCtr, cap.Value)
                 capCtr += 1
              Next
           Next
        Else
           Console.WriteLine("No match found.")
        End If   
        Console.WriteLine()
     End Sub
  End Module
  ' The example displays the following output:
  '    No match found.
  '    
  '    '((a+)(\1) ?)+' matches aa aaaa aaaaaa  at position 0.
  '       0: 'aa aaaa aaaaaa '
  '          0: 'aa aaaa aaaaaa '
  '       1: 'aaaaaa '
  '          0: 'aa '
  '          1: 'aaaa '  
  '          2: 'aaaaaa '
  '       2: 'aa'
  '          0: 'aa'
  '          1: 'aa'
  '          2: 'aa'
  '       3: 'aaaa '
  '          0: ''
  '          1: 'aa '
  '          2: 'aaaa '
  ``

  The regular expression is defined as shown in the following table.

Pattern | Description
------- | ----------- 
`(a+)` | Match the letter "a" one or more times. This is the second capturing group.
`(\1)` | Match the substring captured by the first capturing group. This is the third capturing group.
`?` | Match zero or one space characters.
`((a+)(\1) ?)+` | Match the pattern of one or more "a" characters followed by a string that matches the first capturing group followed by zero or one space characters one or more times. This is the first capturing group.
  
* Resolution of ambiguities between octal escapes and backreferences. The following table summarizes the differences in octal versus backreference interpretation by canonical and ECMAScript regular expressions.

Regular expression | Canonical behavior | ECMAScript behavior
------------------ | ------------------ | ------------------- 
`\0` followed by 0 to 2 octal digits | Interpret as an octal. For example, `\044` is always interpreted as an octal value and means "**$**". | Same behavior.
**\** followed by a digit from 1 to 9, followed by no additional decimal digits | Interpret as a backreference. For example, \9 always means backreference 9, even if a ninth capturing group does not exist. If the capturing group does not exist, the regular expression parser throws an [ArgumentException](xref:System.ArgumentException). | If a single decimal digit capturing group exists, backreference to that digit. Otherwise, interpret the value as a literal.
**\** followed by a digit from 1 to 9, followed by additional decimal digits | Interpret the digits as a decimal value. If that capturing group exists, interpret the expression as a backreference. Otherwise, interpret the leading octal digits up to octal 377; that is, consider only the low 8 bits of the value. Interpret the remaining digits as literals. For example, in the expression `\3000`, if capturing group 300 exists, interpret as backreference 300; if capturing group 300 does not exist, interpret as octal 300 followed by 0. | Interpret as a backreference by converting as many digits as possible to a decimal value that can refer to a capture. If no digits can be converted, interpret as an octal by using the leading octal digits up to octal 377; interpret the remaining digits as literals.
 
## Comparison using the invariant culture

By default, when the regular expression engine performs case-insensitive comparisons, it uses the casing conventions of the current culture to determine equivalent uppercase and lowercase characters. 

However, this behavior is undesirable for some types of comparisons, particularly when comparing user input to the names of system resources, such as passwords, files, or URLs. The following example illustrates such as scenario. The code is intended to block access to any resource whose URL is prefaced with **FILE://**. The regular expression attempts a case-insensitive match with the string by using the regular expression `$FILE://`. However, when the current system culture is tr-TR (Turkish-Turkey), "I" is not the uppercase equivalent of "i". As a result, the call to the [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String)) method returns `false`, and access to the file is allowed. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-sensitive matching ({0} culture)...", 
                  Thread.CurrentThread.CurrentCulture.Name);
if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("URLs that access files are not allowed.");      
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-sensitive matching (tr-TR culture)...
//       Access to file://c:/Documents.MyReport.doc is allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-sensitive matching ({0} culture)...", _
                  Thread.CurrentThread.CurrentCulture.Name)
If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If

Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'       Culture-sensitive matching (tr-TR culture)...
'       Access to file://c:/Documents.MyReport.doc is allowed.
```

> [!NOTE]
>   Weitere Informationen zu Zeichenfolgenvergleichen, bei denen die Groß-/Kleinschreibung beachtet wird und die die invariante Kultur verwenden, finden Sie unter [Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](best-practices.md).
 
Statt die Vergleiche der aktuellen Kultur zu verwenden, bei denen nicht zwischen Groß- und Kleinschreibung unterschieden wird, können Sie die [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant)-Option angeben, um kulturelle Unterschiede in der Sprache zu ignorieren und die Konventionen der nicht varianten Kultur zu verwenden.

> [!NOTE]
> Vergleiche mit der nicht varianten Kultur sind nur möglich, indem der [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant)-Wert an den options-Parameter eines [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktors oder einer statischen Mustervergleichsmethode übergeben wird. Es besteht keine Verfügbarkeit als Inlineoption. 
 
Das folgende Beispiel ist mit dem vorherigen Beispiel identisch, abgesehen davon, dass die statische [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit Optionen aufgerufen wird, die [RegexOptions.CultureInvariant](xref:System.Text.RegularExpressions.RegexOptions.CultureInvariant) enthalten. Auch wenn die aktuelle Kultur auf "Türkisch (Türkei)" gesetzt ist, kann das Modul für reguläre Ausdrücke "FILE" und "file" erfolgreich zuordnen und den Zugriff auf die Dateiressource blockieren. 

```csharp
CultureInfo defaultCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("tr-TR");

string input = "file://c:/Documents.MyReport.doc";
string pattern = "FILE://";

Console.WriteLine("Culture-insensitive matching...");
if (Regex.IsMatch(input, pattern, 
                  RegexOptions.IgnoreCase | RegexOptions.CultureInvariant)) 
   Console.WriteLine("URLs that access files are not allowed.");
else
   Console.WriteLine("Access to {0} is allowed.", input);

Thread.CurrentThread.CurrentCulture = defaultCulture;
// The example displays the following output:
//       Culture-insensitive matching...
//       URLs that access files are not allowed.
```

```vb
Dim defaultCulture As CultureInfo = Thread.CurrentThread.CurrentCulture
Thread.CurrentThread.CurrentCulture = New CultureInfo("tr-TR")

Dim input As String = "file://c:/Documents.MyReport.doc"
Dim pattern As String = "$FILE://"

Console.WriteLine("Culture-insensitive matching...")
If Regex.IsMatch(input, pattern, _
               RegexOptions.IgnoreCase Or RegexOptions.CultureInvariant) Then
   Console.WriteLine("URLs that access files are not allowed.")      
Else
   Console.WriteLine("Access to {0} is allowed.", input)
End If
Thread.CurrentThread.CurrentCulture = defaultCulture
' The example displays the following output:
'        Culture-insensitive matching...
'        URLs that access files are not allowed.
```

## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


