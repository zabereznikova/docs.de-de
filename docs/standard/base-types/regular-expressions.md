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
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 1fc1edd64c330fe579f389750432665ed982976e

---

# <a name="regular-expressions-in-net"></a>Reguläre Ausdrücke in .NET

Der Einsatz regulärer Ausdrücke stellt eine leistungsstarke, flexible und effiziente Methode zur Verarbeitung von Text dar. Durch die umfangreiche Notation regulärer Ausdrücke für den Mustervergleich können folgende Aufgaben ausgeführt werden: schnelle Auswertung großer Textmengen zur Suche nach speziellen Zeichenmustern; Validieren von Text, um sicherzustellen, dass er einem vordefinierten Muster entspricht (z. B. eine E-Mail-Adresse); Extrahieren, Bearbeiten, Ersetzen oder Löschen von Textzeichenfolgen; Hinzufügen der extrahierten Zeichenfolgen zu einer Auflistung, um einen Bericht zu erstellen. Für viele Anwendungen, die mit Zeichenfolgen arbeiten oder große Textblöcke analysieren, sind reguläre Ausdrücke ein unverzichtbares Tool.

## <a name="how-regular-expressions-work"></a>Funktionsweise von regulären Ausdrücken

Das Kernstück der Textverarbeitung mit regulären Ausdrücken ist das Modul für reguläre Ausdrücke, das durch das [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Objekt in .NET dargestellt wird. Für die Textverarbeitung mit regulären Ausdrücken ist mindestens erforderlich, dass das Modul für reguläre Ausdrücke mit den folgenden zwei Informationen bereitgestellt wird:

* Das Muster des regulären Ausdrucks, das im Text identifiziert werden soll. 
  
  In .NET werden Muster für reguläre Ausdrücke durch eine spezielle Syntax oder Sprache definiert, die mit regulären Ausdrücken in Perl 5 kompatibel ist und einige zusätzliche Funktionen wie Mustervergleiche von rechts nach links bietet. Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md).
  
* Der Text, der nach dem Muster des regulären Ausdrucks analysiert werden soll.

Mit den Methoden der [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse können Sie die folgenden Vorgänge durchführen:

* Ermitteln, ob das Muster für reguläre Ausdrücke im Eingabetext vorkommt, indem die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode aufgerufen wird. Ein Beispiel für die Validierung von Text mit der [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode finden Sie unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](verify-format.md).

* Abrufen eines oder aller Vorkommen des Texts, die dem Muster für reguläre Ausdrücke entsprechen, indem die [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String))-Methode oder die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode aufgerufen wird. Die erste Methode gibt ein [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match)-Objekt zurück, das Informationen über den übereinstimmenden Text bereitstellt. Die zweite gibt ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt zurück, das ein [System.Text.RegularExpressions.Match](xref:System.Text.RegularExpressions.Match)-Objekt für jede im analysierten Text gefundene Übereinstimmung enthält. 

* Ersetzen von Text, der das Muster für reguläre Ausdrücke abgleicht, indem die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode aufgerufen wird. Beispiele, in denen die [Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode verwendet wird, um Datumsformate zu ändern und ungültige Zeichen aus einer Zeichenfolge zu entfernen, finden Sie unter [Gewusst wie: Entfernen von ungültigen Zeichen aus einer Zeichenfolge](strip-characters.md) und unter [Beispiel für reguläre Ausdrücke: Ändern von Datumsformaten](changing-formats.md).

Eine Übersicht über das Objektmodell für reguläre Ausdrücke finden Sie unter [Das Objektmodell für reguläre Ausdrücke](object-model.md).

Weitere Informationen über die Sprache für reguläre Ausdrücke finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md).

## <a name="regular-expression-examples"></a>Beispiele für reguläre Ausdrücke

Die [String](xref:System.String)-Klasse enthält eine Reihe von Such- und Ersetzungsmethoden für Zeichenfolgen, die Sie verwenden können, wenn Sie Literalzeichenfolgen in einer größeren Zeichenfolge suchen möchten. Reguläre Ausdrücke sind besonders hilfreich, wenn Sie eine von mehreren Teilzeichenfolgen in einer größeren Zeichenfolge suchen oder wenn Sie Muster in einer Zeichenfolge identifizieren möchten, wie in den folgenden Beispielen veranschaulicht wird. 

### <a name="example-1-replacing-substrings"></a>Beispiel 1: Ersetzen von Teilzeichenfolgen

Angenommen, eine Mailingliste enthält neben dem Vor- und Nachnamen bei einigen Personen auch Angaben zur Anrede (Mr., Mrs., Miss oder Ms.). Wenn Sie Adressaufkleber aus der Liste generieren, die Anrede dabei jedoch unberücksichtigt lassen möchten, können Sie diese mithilfe eines regulären Ausdrucks entfernen, wie im folgenden Beispiel veranschaulicht wird.

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

Das Muster für reguläre Ausdrücke `(Mr\.? |Mrs\.? |Miss |Ms\.? )` entspricht jedem Vorkommen von „Mr “, „Mr. “, „Mrs “, „Mrs. “, „Miss “, „Ms “ oder „Ms. “. Wenn Sie die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode aufrufen, wird die entsprechende Zeichenfolge durch [String.Empty](xref:System.String.Empty) ersetzt, d.h., die Zeichenfolge wird aus der ursprünglichen Zeichenfolge entfernt.

### <a name="example-2-identifying-duplicated-words"></a>Beispiel 2: Identifizieren von doppelten Wörtern

Das versehentliche Erstellen doppelter Wörter ist ein Fehler, der häufig von Entwicklern gemacht wird. Mithilfe eines regulären Ausdrucks können Sie doppelte Wörter identifizieren, wie im folgenden Beispiel veranschaulicht wird.

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

Das Muster des regulären Ausdrucks `\b(\w+?)\s\1\b` kann wie folgt interpretiert werden:

Syntax | Bedeutung
------ | -------
`\b` | An einer Wortgrenze beginnen.
`(\w+?)` | Entspricht einem oder mehreren Wortzeichen, aber so wenigen Zeichen wie möglich. Zusammen bilden diese eine Gruppe, auf die mit `\1` verwiesen werden kann.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`\1` | Entsprechung für die Teilzeichenfolge finden, die gleich der Gruppe `\1` ist.
`\b` | Übereinstimmung mit einer Wortgrenze.

Die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode wird aufgerufen, wobei die Optionen für reguläre Ausdrücke auf [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase) festgelegt sind. Beim Abgleichvorgang spielt die Groß- und Kleinschreibung daher keine Rolle, und die Teilzeichenfolge "This this" wird im Beispiel als Duplikat identifiziert.

Beachten Sie, dass die Eingabezeichenfolge die Teilzeichenfolge "this? This" enthält. Aufgrund des dazwischenliegenden Satzzeichens wird diese jedoch nicht als Duplikat identifiziert.

### <a name="example-3-dynamically-building-a-culture-sensitive-regular-expression"></a>Beispiel 3: Dynamisches Erstellen eines kulturabhängigen regulären Ausdrucks

Das folgende Beispiel veranschaulicht die Leistungsfähigkeit regulärer Ausdrücke in Kombination mit der Flexibilität der .NET-Globalisierungsfunktionen. Mit dem [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekt wird das Format von Währungswerten in der aktuellen Kultur des Systems bestimmt. Anschließend wird anhand dieser Informationen dynamisch ein regulärer Ausdruck erstellt, der Währungswerte aus dem Text extrahiert. Für jede Übereinstimmung wird die Untergruppe extrahiert, die nur die numerische Zeichenfolge enthält. Diese wird in einen [Decimal](xref:System.Decimal)-Wert konvertiert, und dann wird ein laufender Gesamtbetrag berechnet. 

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

Im Beispiel wird dynamisch der reguläre Ausdruck `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` auf einem Computer mit der aktuellen Kultur Englisch - USA (en-US) erstellt. Dieses Muster des regulären Ausdrucks kann wie folgt interpretiert werden:

Syntax | Bedeutung
------ | -------
`\$` | Suche nach einem einzelnen Vorkommen des Dollarsymbols ($) in der Eingabezeichenfolge. Die Musterzeichenfolge des regulären Ausdrucks schließt einen umgekehrten Schrägstrich ein, der angibt, dass das Dollarsymbol nicht als Anchor des regulären Ausdrucks, sondern wörtlich interpretiert werden soll. (Das $-Symbol allein würde angeben, dass das Modul für reguläre Ausdrücke versuchen soll, mit der Suche nach Übereinstimmungen am Ende einer Zeichenfolge zu beginnen.) Um sicherzustellen, dass das Währungssymbol der aktuellen Kultur nicht als reguläres Ausdruckssymbol fehlinterpretiert wird, wird im Beispiel die [Escape](xref:System.Text.RegularExpressions.Regex.Escape(System.String))-Methode aufgerufen, um das Zeichen mit Escapezeichen zu versehen.
`\s*` | Suche nach 0 (null) oder mehr Vorkommen eines Leerstellenzeichens.
`[-+]?` | Suche nach 0 (null) oder einem Vorkommen entweder eines positiven oder eines negativen Vorzeichens.
`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` | Die äußeren Klammern um diesen Ausdruck definieren ihn als Erfassungsgruppe oder Teilausdruck. Wenn eine Übereinstimmung gefunden wird, können Informationen über diesen Teil der übereinstimmenden Zeichenfolge aus dem zweiten [Group](xref:System.Text.RegularExpressions.Group)-Objekt in dem [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt abgerufen werden, das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegeben wird. (Das erste Element in der Auflistung stellt die gesamte Übereinstimmung dar.)
`[0-9]{0,3}` | Suche nach 0 (null) bis drei Vorkommen der Dezimalstellen 0 bis 9.
`(,[0-9]{3})*` | Suche nach 0 (null) oder mehr Vorkommen eines Gruppentrennzeichens gefolgt von drei Dezimalstellen.
`\.` | Suche nach einem einzelnen Vorkommen des Dezimaltrennzeichens.
`[0-9]+` | Suche nach einer oder mehr Dezimalstellen.
`(\.[0-9]+)?` | Suche nach 0 (null) oder einem Vorkommen des Dezimaltrennzeichens, auf das mindestens eine Dezimalstelle folgt.

## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | -----------
[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md) | Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.
[Das Objektmodell für reguläre Ausdrücke](object-model.md) | Ausführliche Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.
[Einzelheiten zum Verhalten regulärer Ausdrücke](regex-behavior.md) | Ausführliche Informationen zu den Funktionen und dem Verhalten von regulären Ausdrücken in .NET.
[Beispiele für reguläre Ausdrücke](regex-examples.md) | Codebeispiele, die typische Anwendungen regulärer Ausdrücke veranschaulichen.


## <a name="reference"></a>Verweis

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)




<!--HONumber=Nov16_HO3-->


