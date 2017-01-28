---
title: "Ersetzungen in regulären Ausdrücken"
description: "Ersetzungen in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0fded615-1021-4468-a644-b491814305c6
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 4b2b547b6edd67590ad75851b8b287e55dc7d70c

---

# <a name="substitutions-in-regular-expressions"></a>Ersetzungen in regulären Ausdrücken

Ersetzungen sind Sprachelemente, die nur in Ersetzungsmustern erkannt werden. Sie definieren den gesamten Text oder einen Teil des Texts, der den entsprechenden Text in der Eingabezeichenfolge ersetzen soll, mithilfe eines Musters eines regulären Ausdrucks. Das Ersetzungsmuster kann zusammen mit Literalzeichen aus einer oder mehreren Ersetzungen bestehen. Ersetzungsmuster werden für Überladungen der [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode, die über einen *replacement*-Parameter verfügen, und für die [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methode bereitgestellt. Die Methoden ersetzen das übereinstimmende Muster durch das Muster, das durch den *replacement*-Parameter definiert wird.

.NET definiert die in der folgenden Tabelle aufgeführten Ersetzungselemente.

Substitution | Beschreibung
------------ | ----------- 
**$**_Zahl_ | Schließt die letzte mit der Erfassungsgruppe, die durch *Zahl* identifiziert wird, übereinstimmende Teilzeichenfolge in die Ersetzungszeichenfolge ein. Hierbei ist *Zahl* ein Dezimalwert. Weitere Informationen finden Sie unter [Ersetzen einer nummerierten Gruppe](#substituting-a-numbered-group).
**${**_name_**}** | Schließt die letzte Teilzeichenfolge in die Ersetzungszeichenfolge ein, die von der benannten Gruppe gefunden wird, die mit **(?<**_Name_**>)** angegeben wird. Weitere Informationen finden Sie unter [Ersetzen einer benannten Gruppe](#substituting-a-named-group).
**$$** | Schließt ein einzelnes "$"-Literal in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen eines $-Zeichens](#substituting-a--character).
**$&** | Schließt eine Kopie der gesamten Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der gesamten Übereinstimmung](#substituting-the-entire-match).
**$`** | Schließt den gesamten Text der Eingabezeichenfolge vor der Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen des Texts vor der Übereinstimmung](#substituting-the-text-before-the-match).
**$'** | Schließt den gesamten Text der Eingabezeichenfolge nach der Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen des Texts nach der Übereinstimmung](#substituting-the-text-after-the-match). 
**$+** | Schließt die letzte erfasste Gruppe in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der zuletzt erfassten Gruppe](#substituting-the-last-captured-group).
**$_** | Schließt die gesamte Eingabezeichenfolge in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der ganzen Eingabezeichenfolge](#substituting-the-entire-input-string).
 
## <a name="substitution-elements-and-replacement-patterns"></a>Ersetzungselemente und Ersetzungsmuster

Ersetzungen sind die einzigen Sonderkonstrukte, die in einem Ersetzungsmuster erkannt werden. Keines der anderen Sprachelemente für reguläre Ausdrücke, einschließlich Escapezeichen und Punkt (**.**), der einem beliebigen Zeichen entspricht, wird unterstützt. Auf ähnliche Weise werden Ersetzungssprachelemente nur in Ersetzungsmustern erkannt und sind in Mustern für reguläre Ausdrücke nie gültig. 

Das einzige Zeichen, das entweder in einem Muster für reguläre Ausdrücke oder in einer Ersetzung vorkommen kann, ist das **$**-Zeichen, obwohl es in jedem Kontext eine andere Bedeutung hat. In einem Muster für reguläre Ausdrücke ist **$** ein Anker, der dem Ende der Zeichenfolge entspricht. In einem Ersetzungsmuster gibt **$** den Anfang einer Ersetzung an. 

> [!NOTE]
> Für die Funktionalität, die mit einem Ersetzungsmuster innerhalb eines regulären Ausdrucks vergleichbar ist, verwenden Sie einen Rückverweis. Weitere Informationen zu Rückverweisen finden Sie unter [Rückverweiskonstrukte](backreference.md).
 
## <a name="substituting-a-numbered-group"></a>Ersetzen einer nummerierten Gruppe

Das **$**_Zahl_-Sprachelement schließt die letzte Teilzeichenfolge ein, die mit der Zahlenerfassungsgruppe in der Ersetzungszeichenfolge übereinstimmt, wobei *Zahl* der Index der Erfassungsgruppe ist. Beispielsweise gibt das Ersetzungsmuster `$1` an, dass die übereinstimmende Teilzeichenfolge durch die erste erfasste Gruppe ersetzt werden soll. Weitere Informationen zu nummerierten Erfassungsgruppen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

Alle Ziffern, die auf **$** folgen, werden als zur Zahlengruppe gehörend interpretiert. Wenn dies nicht Ihre Absicht ist, können Sie stattdessen eine benannte Gruppe ersetzen. Sie können z.B. die Ersetzungszeichenfolge **${1}1** anstelle von **$11** verwenden, um die Ersetzungszeichenfolge als Wert der ersten erfassten Gruppe zusammen mit der Nummer „1“ zu definieren. Weitere Informationen finden Sie unter [Ersetzen einer benannten Gruppe](#substituting-a-named-group). 

Erfassungsgruppen, denen mit der Syntax **(?<**_Name-**>)** keine Namen explizit zugewiesen sind, werden beginnend mit eins von links nach rechts durchnummeriert. Auch benannte Gruppen werden von links nach rechts durchnummeriert, wobei der Startwert um eins größer ist als der Index der letzten unbenannten Gruppe. Im regulären Ausdruck `(\w)(?<digit>\d)` ist z. B. der Index der benannten Gruppe `digit` 2.

Wenn *Zahl* keine gültige Erfassungsgruppe angibt, die in den Mustern für reguläre Ausdrücke definiert ist, wird **$**_Zahl_ als Literalzeichensequenz interpretiert, die zum Ersetzen der einzelnen Übereinstimmungen verwendet wird.

Das folgende Beispiel verwendet die **$**_Zahl_-Ersetzung, um das Währungssymbol aus einem Dezimalwert zu extrahieren. Sie entfernt am Anfang oder Ende eines Währungswerts gefundene Währungssymbole und erkennt die zwei häufigsten Dezimaltrennzeichen ("." und ","). 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "$1";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "$1"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

Das Muster für reguläre Ausdrücke `\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\p{Sc}*` | Übereinstimmung mit keinem oder mehreren Währungssymbolzeichen.
`\s?` | Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
`[.,]?` | Übereinstimmung mit keinem oder einem Punkt oder Komma.
`\d*` | 0 (null) oder mehr Dezimalstellen sollen übereinstimmen.
`(\s?\d+[.,]?\d*)` | Übereinstimmung mit einem Leerzeichen, gefolgt von mindestens einer Dezimalstelle, gefolgt von keinem oder einem Punkt oder Komma, gefolgt von keiner oder mehreren Dezimalstellen. Dies ist die erste Erfassungsgruppe. Da das Ersetzungsmuster `$1` ist, ersetzt der Aufruf der [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode die gesamte übereinstimmende Teilzeichenfolge durch diese erfasste Gruppe. 
 
## <a name="substituting-a-named-group"></a>Ersetzen einer benannten Gruppe

Das **${**_Name_**}**-Sprachelement ersetzt die letzte mit der Erfassungsgruppe *Name* übereinstimmende Teilzeichenfolge, wobei *Name* der Name einer Erfassungsgruppe ist, die durch das Sprachelement **(?<**_Name_**>)** definiert wird. Weitere Informationen zu benannten Erfassungsgruppen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

Wenn *Name* keine im Muster für reguläre Ausdrücke definierte gültige benannte Erfassungsgruppe angibt, aber aus Ziffern besteht, wird **${**_Name_**}** als eine nummerierte Gruppe interpretiert. 

Wenn *Name* weder eine im Muster für reguläre Ausdrücke definierte gültige benannte Erfassungsgruppe noch eine gültige nummerierte Erfassungsgruppe angibt, wird **${**_Name_**}** als Literalzeichensequenz interpretiert, die verwendet wird, um alle Übereinstimmungen zu ersetzen.

Im folgenden Beispiel wird die **${**_Name_**}**-Ersetzung verwendet, um das Währungssymbol aus einem Dezimalwert zu entfernen. Sie entfernt am Anfang oder Ende eines Währungswerts gefundene Währungssymbole und erkennt die zwei häufigsten Dezimaltrennzeichen ("." und ",").

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*";
      string replacement = "${amount}";
      string input = "$16.32 12.19 £16.29 €18.29  €18,29";
      string result = Regex.Replace(input, pattern, replacement);
      Console.WriteLine(result);
   }
}
// The example displays the following output:
//       16.32 12.19 16.29 18.29  18,29
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\p{Sc}*(?<amount>\s?\d+[.,]?\d*)\p{Sc}*"
      Dim replacement As String = "${amount}"
      Dim input As String = "$16.32 12.19 £16.29 €18.29  €18,29"
      Dim result As String = Regex.Replace(input, pattern, replacement)
      Console.WriteLine(result)
   End Sub
End Module
' The example displays the following output:
'       16.32 12.19 16.29 18.29  18,29
```

Das Muster für reguläre Ausdrücke `\p{Sc}*(?<amount>\s?\d[.,]?\d*)\p{Sc}*` wird entsprechend der folgenden Tabelle definiert: 

Muster | Beschreibung
------- | -----------
`\p{Sc}*` | Übereinstimmung mit keinem oder mehreren Währungssymbolzeichen.
`\s?` | Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
`[.,]?` | Übereinstimmung mit keinem oder einem Punkt oder Komma.
`\d*` | 0 (null) oder mehr Dezimalstellen sollen übereinstimmen.
`(?<amount>\s?\d[.,]?\d*)` | Übereinstimmung mit einem Leerzeichen, gefolgt von mindestens einer Dezimalstelle, gefolgt von keinem oder einem Punkt oder Komma, gefolgt von keiner oder mehreren Dezimalstellen. Dies ist die Erfassungsgruppe mit dem Namen „amount“. Da das Ersetzungsmuster `${amount}` ist, ersetzt der Aufruf der [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode die gesamte übereinstimmende Teilzeichenfolge durch diese erfasste Gruppe. 
 
## <a name="substituting-a-character"></a>Ersetzen eines $-Zeichens

Die **$$**-Ersetzung fügt ein literales $-Zeichen in der ersetzten Zeichenfolge ein. 

Im folgenden Beispiel werden das Währungssymbol der aktuellen Kultur und seine Platzierung in einer Währungszeichenfolge mithilfe des [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo)-Objekts bestimmt. Anschließend werden sowohl ein Muster eines regulären Ausdrucks als auch ein Ersetzungsmuster dynamisch erstellt. Wenn das Beispiel auf einem Computer ausgeführt wird, dessen aktuelle Kultur en-US ist, werden das Muster eines regulären Ausdrucks `\b(\d+)(\.(\d+))?` und das Ersetzungsmuster `$$ $1$2` generiert. Das Ersetzungsmuster ersetzt den übereinstimmenden Text durch ein Währungssymbol und ein Leerzeichen, gefolgt von der ersten und zweiten erfassten Gruppe.

```csharp
using System;
using System.Globalization;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Define array of decimal values.
      string[] values= { "16.35", "19.72", "1234", "0.99"};
      // Determine whether currency precedes (True) or follows (False) number.
      bool precedes = NumberFormatInfo.CurrentInfo.CurrencyPositivePattern % 2 == 0;
      // Get decimal separator.
      string cSeparator = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator;
      // Get currency symbol.
      string symbol = NumberFormatInfo.CurrentInfo.CurrencySymbol;
      // If symbol is a "$", add an extra "$".
      if (symbol == "$") symbol = "$$";

      // Define regular expression pattern and replacement string.
      string pattern = @"\b(\d+)(" + cSeparator + @"(\d+))?"; 
      string replacement = "$1$2";
      replacement = precedes ? symbol + " " + replacement : replacement + " " + symbol;
      foreach (string value in values)
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement));
   }
}
// The example displays the following output:
//       16.35 --> $ 16.35
//       19.72 --> $ 19.72
//       1234 --> $ 1234
//       0.99 --> $ 0.99
```

```vb
Imports System.Globalization
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Define array of decimal values.
      Dim values() As String = { "16.35", "19.72", "1234", "0.99"}
      ' Determine whether currency precedes (True) or follows (False) number.
      Dim precedes As Boolean = (NumberFormatInfo.CurrentInfo.CurrencyPositivePattern Mod 2 = 0)
      ' Get decimal separator.
      Dim cSeparator As String = NumberFormatInfo.CurrentInfo.CurrencyDecimalSeparator
      ' Get currency symbol.
      Dim symbol As String = NumberFormatInfo.CurrentInfo.CurrencySymbol
      ' If symbol is a "$", add an extra "$".
      If symbol = "$" Then symbol = "$$"

      ' Define regular expression pattern and replacement string.
      Dim pattern As String = "\b(\d+)(" + cSeparator + "(\d+))?" 
      Dim replacement As String = "$1$2"
      replacement = If(precedes, symbol + " " + replacement, replacement + " " + symbol)
      For Each value In values
         Console.WriteLine("{0} --> {1}", value, Regex.Replace(value, pattern, replacement))
      Next
   End Sub
End Module
' The example displays the following output:
'       16.35 --> $ 16.35
'       19.72 --> $ 19.72
'       1234 --> $ 1234
'       0.99 --> $ 0.99
```

Das Muster für reguläre Ausdrücke `\b(\d+)(\.(\d+))?` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Beginnt den Abgleich am Anfang einer Wortgrenze.
`(\d+)` | Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die erste Erfassungsgruppe.
`\.` | Übereinstimmung mit einem Punkt (dem Dezimaltrennzeichen).
`(\d+)` | Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die dritte Erfassungsgruppe.
`(\.(\d+))?` | Übereinstimmung mit keinem oder einem Vorkommen eines Punkts gefolgt von mindestens einer Dezimalzahl. Dies ist die zweite Erfassungsgruppe.
 
## <a name="substituting-the-entire-match"></a>Ersetzen der gesamten Übereinstimmung

Die Ersetzung **$&** schließt die gesamte Übereinstimmung in die Ersetzungszeichenfolge ein. Sie wird häufig dazu verwendet, dem Anfang oder Ende der übereinstimmenden Zeichenfolge eine Teilzeichenfolge hinzuzufügen. Das Ersetzungsmuster `($&)` fügt z. B. dem Anfang und Ende jeder Übereinstimmung Klammern hinzu. Wenn keine Übereinstimmung vorhanden ist, wirkt sich die Ersetzung **$&** nicht aus.

Im folgenden Beispiel werden mithilfe der Ersetzung **$&** Anführungszeichen am Anfang und Ende von Buchtiteln hinzugefügt, die in einem Zeichenfolgenarray gespeichert wurden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^(\w+\s?)+$";
      string[] titles = { "A Tale of Two Cities", 
                          "The Hound of the Baskervilles", 
                          "The Protestant Ethic and the Spirit of Capitalism", 
                          "The Origin of Species" };
      string replacement = "\"$&\"";
      foreach (string title in titles)
         Console.WriteLine(Regex.Replace(title, pattern, replacement));
   }
}
// The example displays the following output:
//       "A Tale of Two Cities"
//       "The Hound of the Baskervilles"
//       "The Protestant Ethic and the Spirit of Capitalism"
//       "The Origin of Species"
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(\w+\s?)+$"
      Dim titles() As String = { "A Tale of Two Cities", _
                                 "The Hound of the Baskervilles", _
                                 "The Protestant Ethic and the Spirit of Capitalism", _
                                 "The Origin of Species" }
      Dim replacement As String = """$&"""
      For Each title As String In titles
         Console.WriteLine(Regex.Replace(title, pattern, replacement))
      Next  
   End Sub
End Module
' The example displays the following output:
'       "A Tale of Two Cities"
'       "The Hound of the Baskervilles"
'       "The Protestant Ethic and the Spirit of Capitalism"
'       "The Origin of Species"
```

Das Muster für reguläre Ausdrücke `^(\w+\s?)+$` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`^` | Beginnt den Abgleich am Anfang der Eingabezeichenfolge.
`(\w+\s?)+` | Übereinstimmung mit dem Muster mindestens eines Wortzeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen. 
`$` | Entsprechung für das Ende der Eingabezeichenfolge finden.

Das Ersetzungsmuster `"$&"` fügt dem Anfang und Ende jeder Übereinstimmung ein literales Anführungszeichen hinzu.

## <a name="substituting-the-text-before-the-match"></a>Ersetzen des Texts vor der Übereinstimmung

Die Ersetzung **$`** substitution replaces the matched string with the entire input string before the match. That is, it duplicates the input string up to the match while removing the matched text. Any text that follows the matched text is unchanged in the result string. If there are multiple matches in an input string, the replacement text is derived from the original input string, rather than from the string in which text has been replaced by earlier matches. (The example provides an illustration.) If there is no match, the **$`** hat keine Auswirkungen.

Im folgenden Beispiel wird eine Sequenz von einer oder mehreren Dezimalstellen in der Eingabezeichenfolge mithilfe des Muster eines regulären Ausdrucks `\d+` abgeglichen. Die Ersetzungszeichenfolge **$`** ersetzt diese Ziffern durch den Text, der der Übereinstimmung vorausgeht. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$`";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);

      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$`"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

In diesem Beispiel enthält die Eingabezeichenfolge `"aa1bb2cc3dd4ee5"` fünf Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung $` bewirkt, dass das Modul für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Spalte mit der Ergebniszeichenfolge in Fettdruck angezeigt.

Match | Position | Zeichenfolge vor Übereinstimmung | Ergebniszeichenfolge
----- | -------- | ------------------- | -------------
1 | 2 | aa | aa**aa**bb2cc3dd4ee5
2 | 5 | aa1bb | aaaabb**aa1bb**cc3dd4ee5
3 | 8 | aa1bb2cc | aaaabbaa1bbcc**aa1bb2cc**dd4ee5
4 | 11 | aa1bb2cc3dd | aaaabbaa1bbccaa1bb2ccdd**aa1bb2cc3dd**ee5
5 | 14 | aa1bb2cc3dd4ee | aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddee **aa1bb2cc3dd4ee**
 
## <a name="substituting-the-text-after-the-match"></a>Ersetzen des Texts nach der Übereinstimmung

Die Ersetzung **$'** ersetzt die übereinstimmende Zeichenfolge nach der Übereinstimmung durch die gesamte Eingabezeichenfolge. Das heißt, die Eingabezeichenfolge wird nach der Übereinstimmung dupliziert, während der übereinstimmende Text entfernt wird. Jeder Text, der dem übereinstimmenden Text vorausgeht, bleibt in der Ergebniszeichenfolge unverändert. Wenn keine Übereinstimmung vorhanden ist, wirkt sich die Ersetzung **$'** nicht aus.

Im folgenden Beispiel wird eine Sequenz von einer oder mehreren Dezimalstellen in der Eingabezeichenfolge mithilfe des Muster eines regulären Ausdrucks `\d+` abgeglichen. Der Ersetzungszeichenfolge **$'** ersetzt diese Ziffern durch den Text, der der Übereinstimmung folgt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aa1bb2cc3dd4ee5";
      string pattern = @"\d+";
      string substitution = "$'";
      Console.WriteLine("Matches:");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
      Console.WriteLine("Input string:  {0}", input);
      Console.WriteLine("Output string: " + 
                        Regex.Replace(input, pattern, substitution));
   }
}
// The example displays the following output:
//    Matches:
//       1 at position 2
//       2 at position 5
//       3 at position 8
//       4 at position 11
//       5 at position 14
//    Input string:  aa1bb2cc3dd4ee5
//    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aa1bb2cc3dd4ee5"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$'"
      Console.WriteLine("Matches:")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
      Console.WriteLine("Input string:  {0}", input)
      Console.WriteLine("Output string: " + _
                        Regex.Replace(input, pattern, substitution))
   End Sub
End Module
' The example displays the following output:
'    Matches:
'       1 at position 2
'       2 at position 5
'       3 at position 8
'       4 at position 11
'       5 at position 14
'    Input string:  aa1bb2cc3dd4ee5
'    Output string: aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddeeaa1bb2cc3dd4ee
```

In diesem Beispiel enthält die Eingabezeichenfolge `"aa1bb2cc3dd4ee5"` fünf Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung **$'** bewirkt, dass das Modul für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Spalte mit der Ergebniszeichenfolge in Fettdruck angezeigt.

Match | Position | Zeichenfolge vor Übereinstimmung | Ergebniszeichenfolge
----- | -------- | ------------------- | -------------
1 | 2 | bb2cc3dd4ee5 | aa**bb2cc3dd4ee5**bb2cc3dd4ee5
2 | 5 | cc3dd4ee5 | aabb2cc3dd4ee5bb**cc3dd4ee5**cc3dd4ee5
3 | 8 | dd4ee5 | aabb2cc3dd4ee5bbcc3dd4ee5cc**dd4ee5**dd4ee5
4 | 11 | ee5 | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5dd**ee5**ee5
5 | 14 | [String.Empty](xref:System.String.Empty) | aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5ddee5ee
 
## <a name="substituting-the-last-captured-group"></a>Ersetzen der zuletzt erfassten Gruppe

Die Ersetzung **$+** ersetzt die übereinstimmende Zeichenfolge durch die zuletzt erfasste Gruppe. Wenn keine erfassten Gruppen vorhanden sind oder der Wert der zuletzt erfassten Gruppe [String.Empty](xref:System.String.Empty) ist, hat die Ersetzung **$+** keine Auswirkungen.

Im folgenden Beispiel werden doppelte Wörter in einer Zeichenfolge identifiziert, und es wird die Ersetzung **$+** verwendet, um sie durch ein einzelnes Vorkommen des Worts zu ersetzen. Die [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option wird verwendet, um sicherzustellen, dass Wörter, die sich ausschließlich in der Groß-/Kleinschreibung unterscheiden, als Duplikate betrachtet werden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s\1\b";
      string substitution = "$+";
      string input = "The the dog jumped over the fence fence.";
      Console.WriteLine(Regex.Replace(input, pattern, substitution, 
                        RegexOptions.IgnoreCase));
   }
}
// The example displays the following output:
//      The dog jumped over the fence.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s\1\b"
      Dim substitution As String = "$+"
      Dim input As String = "The the dog jumped over the fence fence."
      Console.WriteLine(Regex.Replace(input, pattern, substitution, _
                                      RegexOptions.IgnoreCase))
   End Sub
End Module
' The example displays the following output:
'      The dog jumped over the fence.
```

Das Muster für reguläre Ausdrücke `\b(\w+)\s\1\b` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`\1` | Übereinstimmung mit der ersten erfassten Gruppe.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
## <a name="substituting-the-entire-input-string"></a>Ersetzen der gesamten Eingabezeichenfolge

Die Ersetzung **$_** ersetzt die übereinstimmende Zeichenfolge durch die gesamte Eingabezeichenfolge. Das heißt, dass der übereinstimmende Text entfernt und durch die gesamte Zeichenfolge, einschließlich des übereinstimmenden Texts, ersetzt wird.

Im folgenden Beispiel werden eine oder mehrere Dezimalstellen in der Eingabezeichenfolge abgeglichen. Mithilfe der Ersetzung **$_** werden diese durch die gesamte Eingabezeichenfolge ersetzt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "ABC123DEF456";
      string pattern = @"\d+";
      string substitution = "$_";
      Console.WriteLine("Original string:          {0}", input);
      Console.WriteLine("String with substitution: {0}", 
                        Regex.Replace(input, pattern, substitution));      
   }
}
// The example displays the following output:
//       Original string:          ABC123DEF456
//       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "ABC123DEF456"
      Dim pattern As String = "\d+"
      Dim substitution As String = "$_"
      Console.WriteLine("Original string:          {0}", input)
      Console.WriteLine("String with substitution: {0}", _
                        Regex.Replace(input, pattern, substitution))      
   End Sub
End Module
' The example displays the following output:
'       Original string:          ABC123DEF456
'       String with substitution: ABCABC123DEF456DEFABC123DEF456
```

In diesem Beispiel enthält die Eingabezeichenfolge `"ABC123DEF456"` zwei Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung **$_** bewirkt, dass das Modul für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Spalte mit der Ergebniszeichenfolge in Fettdruck angezeigt.

Match | Position | Zeichenfolge vor Übereinstimmung | Ergebniszeichenfolge
----- | -------- | ------------------- | -------------
1 | 3 | 123 | ABC**ABC123DEF456**DEF456
2 | 5 | 456 | ABCABC123DEF456DEF**ABC123DEF456**
 
## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


