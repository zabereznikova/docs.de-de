---
title: "Verschiedene Konstrukte in regulären Ausdrücken"
description: "Verschiedene Konstrukte in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 478901dc-db6c-4d90-9d3b-f5cfdca2cbf5
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 4205d2a318849a7b24ac0f1fd65f7e8a23ec7f55

---

# <a name="miscellaneous-constructs-in-regular-expressions"></a>Verschiedene Konstrukte in regulären Ausdrücken


Reguläre Ausdrücke in .NET umfassen drei verschiedene Sprachkonstrukte. Einer ermöglicht Ihnen das Aktivieren oder Deaktivieren bestimmter Vergleichsoptionen mitten in einem Muster für reguläre Ausdrücke. Mithilfe der beiden anderen können Sie Kommentare in einen regulären Ausdruck aufnehmen.

## <a name="inline-options"></a>Inlineoptionen

Sie können bestimmte Mustervergleichsoptionen für einen Teil eines regulären Ausdrucks festlegen oder deaktivieren. Verwenden Sie dazu folgende Syntax:

```
(?imnsx-imnsx)
```

Die Optionen, die Sie aktivieren möchten, werden nach dem Fragezeichen aufgeführt, und die Optionen, die Sie deaktivieren möchten, werden nach dem Minuszeichen eingefügt. In der folgenden Tabelle sind die einzelnen Optionen beschrieben. Weitere Informationen zu den einzelnen Optionen finden Sie unter [Optionen für reguläre Ausdrücke](options.md).

Option | Beschreibung
------ | ----------- 
**i** | Übereinstimmung ohne Berücksichtigung der Groß-/Kleinschreibung.
**m** | Mehrzeilenmodus.
**n** | Nur explizite Erfassungen. (Klammern fungieren nicht als Erfassungsgruppen.)
**s** | Einzeilenmodus.
**x** | Leerzeichen ohne Escapezeichen ignorieren und Kommentare im x-Modus zulassen. 
 
Alle Änderungen in Optionen für reguläre Ausdrücke, die über das Konstrukt **(?imnsx-imnsx)** definiert werden, bleiben bis zum Ende der einschließenden Gruppe gültig.

> [!NOTE]
> Das Gruppierungskonstrukt **(?imnsx-imnsx**:_subexpression_**)** bietet identische Funktionen für einen Teilausdruck. Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).
 
Im folgenden Beispiel werden die Optionen **i**, **n** und **x** verwendet, um die Groß-/Kleinschreibung zu ignorieren, explizite Erfassungen zu ermöglichen und Leerzeichen im Muster für reguläre Ausdrücke in der Mitte eines regulären Ausdrucks zu ignorieren. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern; 
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      pattern = @"\b(D\w+)\s(d\w+)\b";
      // Match pattern using default options.
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
      }
      Console.WriteLine();

      // Change regular expression pattern to include options.
      pattern = @"\b(D\w+)(?ixn) \s (d\w+) \b";
      // Match new pattern with options. 
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
            for (int ctr = 1; ctr < match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Drooling dog
//          Group 1: Drooling
//          Group 2: dog
//       
//       Drooling dog
//          Group 1: 'Drooling'
//       Dreaded Deep
//          Group 1: 'Dreaded'
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String 
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      pattern = "\b(D\w+)\s(d\w+)\b"
      ' Match pattern using default options.
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
      Console.WriteLine()

      ' Change regular expression pattern to include options.
      pattern = "\b(D\w+)(?ixn) \s (d\w+) \b"
      ' Match new pattern with options. 
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'       Drooling dog
'          Group 1: Drooling
'          Group 2: dog
'       
'       Drooling dog
'          Group 1: 'Drooling'
'       Dreaded Deep
'          Group 1: 'Dreaded'
```

Im Beispiel werden zwei reguläre Ausdrücke definiert. Der erste, `\b(D\w+)\s(d\w+)\b`, entspricht zwei aufeinander folgenden Wörtern, die mit dem Großbuchstaben „D“ und dem Kleinbuchstaben „d“ beginnen. Der zweite reguläre Ausdruck, `\b(D\w+)(?ixn) \s (d\w+) \b`, verwendet Inlineoptionen, um dieses Muster entsprechend der folgenden Tabelle zu ändern. Ein Vergleich der Ergebnisse bestätigt den Effekt des `(?ixn)`-Konstrukts.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`(D\w+)` | Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen. Dies ist die erste Erfassungsgruppe.
`(?ixn)` | Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(d\w+)` | Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen. Diese Gruppe wird nicht erfasst, da die Option „n“ (explizite Erfassung) aktiviert wurde.
`\b` | Übereinstimmung mit einer Wortgrenze.
 
## <a name="inline-comment"></a>Inlinekommentar

Das Konstrukt **(?#** _Kommentar_**)** ermöglicht das Aufnehmen eines Inlinekommentars in einen regulären Ausdruck. Das Modul für reguläre Ausdrücke verwendet keinen Teil des Kommentars beim Mustervergleich, obwohl der Kommentar in der von der Methode [Regex.ToString](xref:System.Text.RegularExpressions.Regex.Unescape(System.String)) zurückgegeben Zeichenfolge enthalten ist. Der Kommentar endet bei der ersten schließenden Klammer.

Im folgenden Beispiel wird das erste Muster für reguläre Ausdrücke aus dem Beispiel im vorherigen Abschnitt wiederholt. Dem regulären Ausdruck werden zwei Inlinekommentare hinzugefügt, um anzugeben, ob beim Vergleich die Groß-/Kleinschreibung berücksichtigt wird. Das Muster für reguläre Ausdrücke, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, ist wie folgt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`(?# case-sensitive comparison)` | Ein Kommentar. Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus.
`(D\w+)` | Übereinstimmung mit dem Großbuchstaben „D“, gefolgt von einem oder mehreren Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(?ixn)` |Ab diesem Punkt werden Vergleiche ohne Berücksichtigung der Groß-/Kleinschreibung und nur explizite Erfassungen durchgeführt sowie Leerzeichen im Muster für reguläre Ausdrücke ignoriert.
`(?#case-insensitive comparison)` | Ein Kommentar. Dieser wirkt sich nicht auf das Verhalten des Mustervergleichs aus. 
`(d\w+)` | Übereinstimmung mit dem Groß- oder Kleinbuchstaben „d“, gefolgt von mindestens einem Wortzeichen. Dies ist die zweite Erfassungsgruppe.
`\b` | Übereinstimmung mit einer Wortgrenze.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b";
      Regex rgx = new Regex(pattern);
      string input = "double dare double Double a Drooling dog The Dreaded Deep";

      Console.WriteLine("Pattern: " + pattern.ToString());
      // Match pattern using default options.
      foreach (Match match in rgx.Matches(input))
      {
         Console.WriteLine(match.Value);
         if (match.Groups.Count > 1)
         {
            for (int ctr = 1; ctr <match.Groups.Count; ctr++) 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
         }
      }
   }
}
// The example displays the following output:
//    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
//    arison)d\w+)\b
//    Drooling dog
//       Group 1: Drooling
//    Dreaded Deep
//       Group 1: Dreaded
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comparison)d\w+)\b"
      Dim rgx As New Regex(pattern)
      Dim input As String = "double dare double Double a Drooling dog The Dreaded Deep"

      Console.WriteLine("Pattern: " + pattern.ToString())
      ' Match pattern using default options.
      For Each match As Match In rgx.Matches(input)
         Console.WriteLine(match.Value)
         If match.Groups.Count > 1 Then
            For ctr As Integer = 1 To match.Groups.Count - 1 
               Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
            Next
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'    Pattern: \b((?# case sensitive comparison)D\w+)\s(?ixn)((?#case insensitive comp
'    arison)d\w+)\b
'    Drooling dog
'       Group 1: Drooling
'    Dreaded Deep
'       Group 1: Dreaded
```

## <a name="endofline-comment"></a>Zeilenendekommentar

Ein Nummernzeichen (**#**) markiert einen x-Modus-Kommentar, der bei dem #-Zeichen ohne Escapezeichen am Ende des Musters für reguläre Ausdrücke beginnt und bis zum Zeilenende fortgesetzt wird. Um dieses Konstrukt zu verwenden, müssen Sie entweder die **x**-Option (durch Inlineoptionen) aktivieren oder beim Instanziieren des [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts bzw. beim Aufrufen einer statischen [Regex](xref:System.Text.RegularExpressions.Regex)-Methode den Wert [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace) an den *option*-Parameter übergeben. 

Das folgende Beispiel veranschaulicht das Konstrukt für Zeilenendekommentare. Dabei wird bestimmt, ob es sich bei einer Zeichenfolge um eine zusammengesetzte Formatzeichenfolge handelt, die mindestens ein Formatelement einschließt. Die folgende Tabelle beschreibt die Konstrukte im Muster für reguläre Ausdrücke: 

`\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item`. 

Muster | Beschreibung
------- | ----------- 
`\{` | Übereinstimmung mit einer öffnenden geschweiften Klammer.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
`(,-*\d+)*` | Übereinstimmung mit keinem oder einem Vorkommen eines Kommas, gefolgt von einem optionalen Minuszeichen, gefolgt von mindestens einer Dezimalzahl.
`(\:\w{1,4}?)*` | Übereinstimmung mit keinem oder einem Doppelpunkt, gefolgt von einem bis vier Leerzeichen (jedoch so wenigen wie möglich).
`(?#case insensitive comparison)` | Ein Inlinekommentar. Wirkt sich nicht auf das Verhalten zum Musterabgleich aus.
`\}` | Übereinstimmung mit einer schließenden geschweiften Klammer.
`(?x)` | Aktivieren der Option zum Ignorieren von Leerzeichen im Muster, sodass der Zeilenendekommentar erkannt wird.
`# Looks for a composite format item.` | Ein Zeilenendekommentar.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.";
      string input = "{0,-3:F}";
      Console.WriteLine("'{0}':", input);
      if (Regex.IsMatch(input, pattern))
         Console.WriteLine("   contains a composite format item.");
      else
         Console.WriteLine("   does not contain a composite format item.");
   }
}
// The example displays the following output:
//       '{0,-3:F}':
//          contains a composite format item.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item."
      Dim input As String = "{0,-3:F}"
      Console.WriteLine("'{0}':", input)
      If Regex.IsMatch(input, pattern) Then
         Console.WriteLine("   contains a composite format item.")
      Else
         Console.WriteLine("   does not contain a composite format item.")
      End If
   End Sub
End Module
' The example displays the following output:
'       '{0,-3:F}':
'          contains a composite format item.
```

Anstelle der Bereitstellung des `(?x)`-Konstrukts im regulären Ausdruck wird der Kommentar ebenso erkannt, indem die [Regex.IsMatch(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode aufgerufen und der [RegexOptions.IgnorePatternWhitespace](xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace)-Enumerationswert übergeben wird.

## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


