---
title: "Rückverweiskonstrukte in regulären Ausdrücken"
description: "Rückverweiskonstrukte in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c453ed78-650f-4c3c-9ab4-9d89d250bf88
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: d6fdf23898cacc7ce569f868b3a31b71eff5c716
ms.lasthandoff: 03/02/2017

---

# <a name="backreference-constructs-in-regular-expressions"></a>Rückverweiskonstrukte in regulären Ausdrücken

Rückverweise bieten eine einfache Möglichkeit, ein wiederholtes Zeichen oder eine Teilzeichenfolge innerhalb einer Zeichenfolge zu identifizieren. Wenn z.B. die Eingabezeichenfolge mehrere Vorkommen einer beliebigen Teilzeichenfolge enthält, können Sie das erste Vorkommen mit einer Erfassungsgruppe abgleichen und dann mit einem Rückverweis nachfolgende Vorkommen der Teilzeichenfolge abgleichen. 

> [!NOTE]
> Eine separate Syntax wird verwendet, um auf benannte und nummerierte Erfassungsgruppen in Ersetzungszeichenfolgen zu verweisen. Weitere Informationen finden Sie unter [Ersetzungen in regulären Ausdrücken](substitutions.md).
 
.NET definiert separate Sprachelemente, um auf nummerierte und benannte Erfassungsgruppen zu verweisen. Weitere Informationen zu Erfassungsgruppen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

## <a name="numbered-backreferences"></a>Nummerierte Rückverweise

Ein nummerierter Rückverweis verwendet die folgende Syntax:

**\**_Nummer_

wobei *Nummer* die Ordnungsposition der Erfassungsgruppe im regulären Ausdruck ist. `\4` gleicht z.B. den Inhalt der vierten Erfassungsgruppe ab. Wenn *Nummer* nicht im Muster eines regulären Ausdrucks definiert ist, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke löst eine [ArgumentException](xref:System.ArgumentException) aus. Beispielsweise ist der reguläre Ausdruck `\b(\w+)\s\1` gültig, da `(\w+)` die erste und einzige Erfassungsgruppe im Ausdruck ist. Auf der anderen Seite ist `\b(\w+)\s\2` ungültig und löst eine Argumentausnahme aus, da es keine nummerierte Erfassungsgruppe `\2` gibt.

Beachten Sie die Mehrdeutigkeit zwischen oktalen Escapesequenzen (z.B. `\16`) und **\**_Nummer_ Rückverweisen mit der gleichen Notation. Diese Mehrdeutigkeit wird wie folgt aufgelöst:

* Die Ausdrücke `\1` bis `\9` werden immer als Rückverweise und nicht als oktale Codes interpretiert.

* Wenn die erste Ziffer eines mehrziffrigen Ausdrucks 8 oder 9 ist (z.B. `\80` oder `\91`), wird der Ausdruck als Literal interpretiert.

* Ausdrücke aus `\10` und höher werden als Rückverweise betrachtet, wenn ein Rückverweis vorhanden ist, der dieser Nummer entspricht; andernfalls werden sie als oktale Codes interpretiert.

* Wenn ein regulärer Ausdruck einen Rückverweis auf eine undefinierte Gruppennummer enthält, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke löst eine [ArgumentException](xref:System.ArgumentException) aus.

Wenn die Mehrdeutigkeit ein Problem ist, können Sie die Notation **\k<**_Name_**>** verwenden. Sie ist eindeutig und kann nicht mit oktalen Zeichencodes verwechselt werden. Auf ähnliche Weise sind hexadezimale Codes wie z.B. `\xdd` eindeutig und können nicht mit Rückverweisen verwechselt werden.

Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Es definiert einen regulären Ausdruck `(\w)\1,`, der aus den folgenden Elementen besteht.

Element | Beschreibung
------- | -----------
`(\w)` | Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zur ersten Erfassungsgruppe.
`\1` | Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der ersten Erfassungsgruppe identisch ist.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w)\1";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w)\1"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="named-backreferences"></a>Benannte Rückverweise

Ein benannter Rückverweis wird mit der folgenden Syntax definiert:

**\k<**_Name_**>**

oder:

**\k'**_Name_**'**

wobei *Name* der Name einer Erfassungsgruppe ist, die im Muster eines regulären Ausdrucks definiert ist. Wenn *Name* nicht im Muster eines regulären Ausdrucks definiert ist, tritt ein Analysefehler auf, und das Modul für reguläre Ausdrücke löst eine [ArgumentException](xref:System.ArgumentException) aus.

Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Ein regulärer Ausdruck `(?<char>\w)\k<char>` wird definiert, der aus den folgenden Elementen besteht.

Element | Beschreibung
------- | -----------
`(?<char>\w)` | Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zu einer Erfassungsgruppe mit dem Namen „char“.
`\k<char>` | Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der char-Erfassungsgruppe identisch ist.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<char>\w)\k<char>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<char>\w)\k<char>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

Beachten Sie, dass *Name* auch die Zeichenfolgendarstellung einer Zahl sein kann. Im folgenden Beispiel werden mit dem regulären Ausdruck `(?<2>\w)\k<2>` doppelte Wortzeichen in einer Zeichenfolge gesucht.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<2>\w)\k<2>";
      string input = "trellis llama webbing dresser swagger";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Found '{0}' at position {1}.", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Found 'll' at position 3.
//       Found 'll' at position 8.
//       Found 'bb' at position 16.
//       Found 'ss' at position 25.
//       Found 'gg' at position 33.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<2>\w)\k<2>"
      Dim input As String = "trellis llama webbing dresser swagger"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Found '{0}' at position {1}.", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Found 'll' at position 3.
'       Found 'll' at position 8.
'       Found 'bb' at position 16.
'       Found 'ss' at position 25.
'       Found 'gg' at position 33.
```

## <a name="what-backreferences-match"></a>Übereinstimmende Rückverweise

Ein Rückverweis bezieht sich auf die aktuellste Definition einer Gruppe (beim Abgleichen von links nach rechts die am weitesten links befindliche Definition). Wenn eine Gruppe mehrere Erfassungen durchführt, bezieht sich ein Rückverweis auf die aktuellste Erfassung. 

Das folgende Beispiel enthält ein Muster für reguläre Ausdrücke, `(?<1>a)(?<1>\1b)*`, das die Gruppe namens „\1“ neu definiert. Die folgende Tabelle beschreibt jedes Muster im regulären Ausdruck. 

Muster | Beschreibung
------- | -----------
`(?<1>a)` | Übereinstimmung mit dem Zeichen „a“ und Zuweisen des Ergebnisses zur Erfassungsgruppe 1.
`(?<1>\1b)*` |Übereinstimmung mit null oder einem Vorkommen der Gruppe 1 zusammen mit einem „b“ und Zuweisen des Ergebnisses zur Erfassungsgruppe 1. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<1>a)(?<1>\1b)*";
      string input = "aababb";
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine("Match: " + match.Value);
         foreach (Group group in match.Groups)
            Console.WriteLine("   Group: " + group.Value);
      }
   }
}
// The example displays the following output:
//          Group: aababb
//          Group: abb
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<1>a)(?<1>\1b)*"
      Dim input As String = "aababb"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Match: " + match.Value)
         For Each group As Group In match.Groups
            Console.WriteLIne("   Group: " + group.Value)
         Next
      Next
   End Sub
End Module
' The example display the following output:
'          Group: aababb
'          Group: abb
```

Beim Vergleich des regulären Ausdrucks mit der Eingabezeichenfolge („aababb“) führt das Modul für reguläre Ausdrücke die folgenden Vorgänge aus:

1. Begonnen wird am Anfang der Zeichenfolge, und „a“ wird erfolgreich mit dem Ausdruck `(?<1>a)` abgeglichen. Der Wert der 1-Gruppe ist nun „a“.

2. Es wird zum zweiten Zeichen gewechselt, und die Zeichenfolge „ab“ wird erfolgreich mit dem Ausdruck `\1b` bzw. „ab“ abgeglichen. Anschließend wird `\1` das Ergebnis „ab“ zugewiesen.

3. Es wird zum vierten Zeichen gewechselt. Der Ausdruck `(?<1>\1b)` muss nullmal oder mehrfach abgeglichen werden, damit er der Zeichenfolge „abb“ mit dem Ausdruck `\1b` entspricht. Das Ergebnis „abb“ wird wieder `\1` zugewiesen.

In diesem Beispiel ist \* ein Schleifenquantifizierer – er wird wiederholt ausgewertet, bis das Modul für reguläre Ausdrücke keine Entsprechung für das Muster finden kann, das es definiert. Quantifizierer, die in Schleifen durchlaufen werden, löschen keine Gruppendefinitionen.

Wurden durch eine Gruppe keine Teilzeichenfolgen gefunden, ist der Rückverweis auf diese Gruppe nicht definiert und führt niemals zu einer Übereinstimmung. Dies wird durch das Muster des regulären Ausdrucks `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b,` veranschaulicht, der folgendermaßen definiert ist:

Muster | Beschreibung
------- | -----------
`\b` | Beginnt den Vergleich an einer Wortgrenze.
`(\p{Lu}{2})` | Übereinstimmung mit zwei Großbuchstaben. Dies ist die erste Erfassungsgruppe.
`(\d{2})?` | Übereinstimmung mit null oder einem Vorkommen von zwei Dezimalziffern. Dies ist die zweite Erfassungsgruppe.
`(\p{Lu}{2})` | Übereinstimmung mit zwei Großbuchstaben. Dies ist die dritte Erfassungsgruppe.
`\b` | Beendet den Vergleich an einer Wortgrenze.

Eine Eingabezeichenfolge kann auch dann mit diesem regulären Ausdruck übereinstimmen, wenn die von der zweiten Erfassungsgruppe definierten zwei Dezimalziffern nicht vorhanden sind. Das folgende Beispiel zeigt, dass trotz Übereinstimmung eine leere Erfassungsgruppe zwischen zwei erfolgreichen Erfassungsgruppen gefunden wird.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b";
      string[] inputs = { "AA22ZZ", "AABB" };
      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
         {
            Console.WriteLine("Match in {0}: {1}", input, match.Value);
            if (match.Groups.Count > 1)
            {
               for (int ctr = 1; ctr <= match.Groups.Count - 1; ctr++)
               {
                  if (match.Groups[ctr].Success)
                     Console.WriteLine("Group {0}: {1}", 
                                       ctr, match.Groups[ctr].Value);
                  else
                     Console.WriteLine("Group {0}: <no match>", ctr);
               }
            }
         }
         Console.WriteLine();
      }      
   }
}
// The example displays the following output:
//       Match in AA22ZZ: AA22ZZ
//       Group 1: AA
//       Group 2: 22
//       Group 3: ZZ
//       
//       Match in AABB: AABB
//       Group 1: AA
//       Group 2: <no match>
//       Group 3: BB
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b"
      Dim inputs() As String = { "AA22ZZ", "AABB" }
      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("Match in {0}: {1}", input, match.Value)
            If match.Groups.Count > 1 Then
               For ctr As Integer = 1 To match.Groups.Count - 1
                  If match.Groups(ctr).Success Then
                     Console.WriteLine("Group {0}: {1}", _
                                       ctr, match.Groups(ctr).Value)
                  Else
                     Console.WriteLine("Group {0}: <no match>", ctr)
                  End If      
               Next
            End If
         End If
         Console.WriteLine()
      Next      
   End Sub
End Module
' The example displays the following output:
'       Match in AA22ZZ: AA22ZZ
'       Group 1: AA
'       Group 2: 22
'       Group 3: ZZ
'       
'       Match in AABB: AABB
'       Group 1: AA
'       Group 2: <no match>
'       Group 3: BB
```

## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)


