---
title: "Anker in regulären Ausdrücken"
description: "Anker in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 96dff1be-3005-4ba5-af1b-323182a26085
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: ef2a63115f1efbe2418c348a3379fe7dd2face86

---

# <a name="anchors-in-regular-expressions"></a>Anker in regulären Ausdrücken

Anker, auch als atomische Nullbreitenassertionen bezeichnet, geben eine Position in der Zeichenfolge an, an der eine Übereinstimmung auftreten muss. Wenn Sie im Suchausdruck einen Anker verwenden, durchsucht das Modul für reguläre Ausdrücke nicht die Zeichenfolge oder durchläuft Zeichen, sondern sucht nur an der angegebenen Position nach einer Übereinstimmung. Beispielsweise gibt **^** an, dass die Übereinstimmung am Anfang einer Zeile oder Zeichenfolge beginnen muss. Daher stimmt der reguläre Ausdruck `^http:` nur mit "http:" überein, wenn dies am Anfang einer Zeile steht. In der folgenden Tabelle werden die von den regulären .NET-Ausdrücken unterstützten Anker aufgeführt. 

Anker | Beschreibung
------ | ----------- 
**^** | Die Übereinstimmung muss am Anfang der Zeichenfolge oder Zeile vorliegen.
**$** | Die Übereinstimmung muss am Ende der Zeichenfolge oder Zeile oder vor \n am Ende der Zeile oder Zeichenfolge vorliegen.
**\A** | Die Übereinstimmung darf nur am Anfang der Zeichenfolge vorliegen (mehrere Zeilen werden nicht unterstützt).
**\Z** | Die Übereinstimmung muss am Ende der Zeichenfolge oder vor \n am Ende der Zeichenfolge vorliegen.
**\z** | Die Übereinstimmung darf nur am Ende der Zeichenfolge vorliegen. 
**\G** | Die Übereinstimmung muss an dem Punkt beginnen, an dem die vorherige Übereinstimmung endete.
**\b** | Die Übereinstimmung muss an einer Wortgrenze vorliegen.
**\B** | Die Übereinstimmung darf nicht an einer Wortgrenze vorliegen.
 
## <a name="start-of-string-or-line-"></a>Anfang der Zeichenfolge oder Zeile: ^

Der **^**-Anker gibt an, dass das folgende Muster an der ersten Zeichenposition der Zeichenfolge beginnen muss. Wenn Sie **^** mit der Option [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) (siehe [Optionen für reguläre Ausdrücke](options.md)) verwenden, muss die Übereinstimmung am Anfang jeder Zeile vorliegen.

Im folgenden Beispiel wird der **^**-Anker in einem regulären Ausdruck verwendet, der Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Im Beispiel werden zwei Überladungen der `Regex.Matches`-Methode aufgerufen: 

* Der Aufruf der [Matches(String, String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String))-Überladung sucht nur die erste Teilzeichenfolge in der Eingabezeichenfolge, die mit dem Muster des regulären Ausdrucks übereinstimmt. 

* Der Aufruf der [Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Überladung mit Festlegung des Parameters „options“ auf [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline) sucht alle fünf Teilzeichenfolgen.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957\n" +
                     "Chicago Cubs, National League, 1903-present\n" + 
                     "Detroit Tigers, American League, 1901-present\n" + 
                     "New York Giants, National League, 1885-1957\n" +  
                     "Washington Senators, American League, 1901-1960\n";   
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      Match match;

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      

      startPos = 0
      endPos = 70
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      


'       For Each match As Match in Regex.Matches(input, pattern, RegexOptions.Multiline)
'          Console.Write("The {0} played in the {1} in", _
'                            match.Groups(1).Value, match.Groups(4).Value)
'          For Each capture As Capture In match.Groups(5).Captures
'             Console.Write(capture.Value)
'          Next
'          Console.WriteLine(".")
'       Next
   End Sub
End Module
' The example displays the following output:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
```

Das Muster für reguläre Ausdrücke `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`^` | Suchen Sie nach einer Übereinstimmung am Anfang der Eingabezeichenfolge (oder am Anfang der Zeile, wenn die Methode mit der `RegexOptions.Multiline`-Option aufgerufen wird).
`((\w+(\s?)){2,}` | Suchen Sie nach einer Übereinstimmung mit mindestens einem Wortzeichen, auf das genau zwei Mal eine 0 (Null) oder ein Leerzeichen folgt. Dies ist die erste Erfassungsgruppe. Durch diesen Ausdruck werden auch eine zweite und dritte Erfassungsgruppe definiert: Die zweite Gruppe besteht aus dem erfassten Wort, die dritte aus den erfassten Leerzeichen. 
`,\s` | Suchen Sie nach einer Übereinstimmung mit einem Komma gefolgt von einem Leerzeichen.
`(\w+\s\w+)` | Suchen Sie nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von mindestens einem Wortzeichen. Dies ist die vierte Erfassungsgruppe.
`,` | Entsprechung für ein Komma finden.
`\s\d{4}` | Suchen Sie nach einer Übereinstimmung mit einem von vier Dezimalzahlen gefolgten Leerzeichen.
`(-(\d{4}`&#124;`present))?` |  Suchen Sie nach einer Übereinstimmung mit 0 (Null) oder einem Bindestrich gefolgt von vier Dezimalzahlen oder der Zeichenfolge "present". Dies ist die sechste Erfassungsgruppe. Diese Gruppe enthält auch eine siebte Erfassungsgruppe. 
`,?` | Suchen Sie nach einer Übereinstimmung mit 0 (null) oder einem Komma.
`(\s\d{4}(-(\d{4}`&#124;`present))?,?)+` | Suchen Sie nach einer Übereinstimmung mit mindestens einem Vorkommen der folgenden Elemente: ein Leerzeichen, vier Dezimalzahlen, 0 (Null) oder ein Bindestrich gefolgt von vier Dezimalzahlen oder der Zeichenfolge "present" sowie 0 (Null) oder ein Komma. Dies ist die fünfte Erfassungsgruppe.
 
## <a name="end-of-string-or-line-"></a>Ende der Zeichenfolge oder Zeile: $

Der **$**-Anker gibt an, dass das vorangehende Muster am Ende der Eingabezeichenfolge oder vor \n am Ende der Eingabezeichenfolge vorliegen muss. 

Wenn Sie **$** mit der [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)-Option verwenden, kann die Übereinstimmung auch am Ende einer Zeile vorliegen. Beachten Sie, dass **$** mit **\n** übereinstimmt, nicht jedoch mit **\r\n** (der Kombination aus Wagenrücklauf- und Zeilenumbruchzeichen oder CR/LF). Zum Suchen einer Übereinstimmung mit der CR/LF-Zeichenkombination schließen Sie **\r?$** in das Muster des regulären Ausdrucks ein.

Im folgenden Beispiel wird der **$**-Anker dem Muster des regulären Ausdrucks hinzugefügt, der im Beispiel im vorherigen Abschnitt „Anfang der Zeichenfolge oder Zeile“ verwendet wurde. Bei Verwendung mit der ursprünglichen Eingabezeichenfolge von fünf Textzeilen findet die [Regex.Matches(String, String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String))-Methode keine Übereinstimmung, da das Ende der ersten Zeile nicht mit dem **$**-Muster übereinstimmt. Wenn die ursprüngliche Eingabezeichenfolge in ein Zeichenfolgenarray geteilt wird, findet die `Regex.Matches(String, String)`-Methode eine Übereinstimmung mit jeder der fünf Zeilen. Wenn die [Regex.Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit dem auf `RegexOptions.Multiline` festgelegten Parameter *options* aufgerufen wird, werden keine Übereinstimmungen gefunden, da das Wagenrücklaufelement (\u+000D) nicht Teil des Musters des regulären Ausdrucks ist. Wenn das Muster des regulären Ausdrucks jedoch geändert wird, indem **$** durch **\r?$** ersetzt wird, ergibt der Aufruf der `Regex.Matches(String, String, RegexOptions)`-Methode wieder fünf Übereinstimmungen, sofern der Parameter *options* auf `RegexOptions.Multiline` festgelegt ist.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string cr = Environment.NewLine;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + cr +
                     "Chicago Cubs, National League, 1903-present" + cr + 
                     "Detroit Tigers, American League, 1901-present" + cr + 
                     "New York Giants, National League, 1885-1957" + cr +  
                     "Washington Senators, American League, 1901-1960" + cr;   
      Match match;

      string basePattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      string pattern = basePattern + "$";
      Console.WriteLine("Attempting to match the entire input string:");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      string[] teams = input.Split(new String[] { cr }, StringSplitOptions.RemoveEmptyEntries);
      Console.WriteLine("Attempting to match each element in a string array:");
      foreach (string team in teams)
      {
         if (team.Length > 70) continue;

         match = Regex.Match(team, pattern);
         if (match.Success)
         {
            Console.Write("The {0} played in the {1} in", 
                          match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);
            Console.WriteLine(".");
         }
      }
      Console.WriteLine();

      startPos = 0;
      endPos = 70;
      Console.WriteLine("Attempting to match each line of an input string with '$':");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }

      startPos = 0;
      endPos = 70;
      pattern = basePattern + "\r?$"; 
      Console.WriteLine(@"Attempting to match each line of an input string with '\r?$':");
      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Attempting to match the entire input string:
//    
//    Attempting to match each element in a string array:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
//    
//    Attempting to match each line of an input string with '$':
//    
//    Attempting to match each line of an input string with '\r+$':
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
//    The Chicago Cubs played in the National League in 1903-present.
//    The Detroit Tigers played in the American League in 1901-present.
//    The New York Giants played in the National League in 1885-1957.
//    The Washington Senators played in the American League in 1901-1960.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim basePattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      Dim pattern As String = basePattern + "$"
      Console.WriteLine("Attempting to match the entire input string:")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      

      Dim teams() As String = input.Split(New String() { vbCrLf }, StringSplitOptions.RemoveEmptyEntries)
      Console.WriteLine("Attempting to match each element in a string array:")
      For Each team As String In teams
         If team.Length > 70 Then Continue For
         match = Regex.Match(team, pattern)
         If match.Success Then
            Console.Write("The {0} played in the {1} in", _
                           match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
         End If
      Next
      Console.WriteLine()

      startPos = 0
      endPos = 70
      Console.WriteLine("Attempting to match each line of an input string with '$':")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      


      startPos = 0
      endPos = 70
      pattern = basePattern + "\r?$" 
      Console.WriteLine("Attempting to match each line of an input string with '\r?$':")
      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      
   End Sub
End Module
' The example displays the following output:
'    Attempting to match the entire input string:
'    
'    Attempting to match each element in a string array:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
'    
'    Attempting to match each line of an input string with '$':
'    
'    Attempting to match each line of an input string with '\r+$':
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
'    The Chicago Cubs played in the National League in 1903-present.
'    The Detroit Tigers played in the American League in 1901-present.
'    The New York Giants played in the National League in 1885-1957.
'    The Washington Senators played in the American League in 1901-1960.
```

## <a name="start-of-string-only-a"></a>Nur Anfang der Zeichenfolge: \A

Der **\A**-Anker gibt an, dass eine Übereinstimmung am Anfang der Eingabezeichenfolge vorliegen muss. Dies ist mit dem **^**-Anker identisch, jedoch ignoriert **\A** die [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)-Option. Daher kann hiermit in einer mehrzeiligen Eingabezeichenfolge nur eine Übereinstimmung nur am Anfang der ersten Zeile gesucht werden.

Das folgende Beispiel ähnelt den Beispielen für den **^**-Anker und den **$**-Anker. Der **\A**-Anker wird in einem regulären Ausdruck verwendet, der Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Die Eingabezeichenfolge weist fünf Zeilen auf. Der Aufruf der [Regex.Matches(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Matches(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Überladung sucht nur die erste Teilzeichenfolge in der Eingabezeichenfolge, die mit dem Muster des regulären Ausdrucks übereinstimmt. Wie im Beispiel dargestellt, hat die `Multiline`-Option keine Auswirkungen.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      int startPos = 0, endPos = 70;
      string input = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957\n" +
                     "Chicago Cubs, National League, 1903-present\n" + 
                     "Detroit Tigers, American League, 1901-present\n" + 
                     "New York Giants, National League, 1885-1957\n" +  
                     "Washington Senators, American League, 1901-1960\n";   

      string pattern = @"\A((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+";
      Match match;

      if (input.Substring(startPos, endPos).Contains(",")) {
         match = Regex.Match(input, pattern, RegexOptions.Multiline);
         while (match.Success) {
            Console.Write("The {0} played in the {1} in", 
                              match.Groups[1].Value, match.Groups[4].Value);
            foreach (Capture capture in match.Groups[5].Captures)
               Console.Write(capture.Value);

            Console.WriteLine(".");
            startPos = match.Index + match.Length;
            endPos = startPos + 70 <= input.Length ? 70 : input.Length - startPos;
            if (! input.Substring(startPos, endPos).Contains(",")) break;
            match = match.NextMatch();
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim startPos As Integer = 0
      Dim endPos As Integer = 70
      Dim input As String = "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957" + vbCrLf + _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf + _
                            "Detroit Tigers, American League, 1901-present" + vbCrLf + _
                            "New York Giants, National League, 1885-1957" + vbCrLf + _
                            "Washington Senators, American League, 1901-1960" + vbCrLf  

      Dim pattern As String = "\A((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+"
      Dim match As Match

      ' Provide minimal validation in the event the input is invalid.
      If input.Substring(startPos, endPos).Contains(",") Then
         match = Regex.Match(input, pattern, RegexOptions.Multiline)
         Do While match.Success
            Console.Write("The {0} played in the {1} in", _
                              match.Groups(1).Value, match.Groups(4).Value)
            For Each capture As Capture In match.Groups(5).Captures
               Console.Write(capture.Value)
            Next
            Console.WriteLine(".")
            startPos = match.Index + match.Length 
            endPos = CInt(IIf(startPos + 70 <= input.Length, 70, input.Length - startPos))
            If Not input.Substring(startPos, endPos).Contains(",") Then Exit Do
            match = match.NextMatch()            
         Loop
         Console.WriteLine()                               
      End If      
   End Sub   
End Module
' The example displays the following output:
'    The Brooklyn Dodgers played in the National League in 1911, 1912, 1932-1957.
```

## <a name="end-of-string-or-before-ending-newline-z"></a>Ende der Zeichenfolge oder vor dem abschließenden Zeilenumbruch: \Z

Der **\Z**-Anker gibt an, dass eine Übereinstimmung am Ende der Eingabezeichenfolge oder vor **\n** am Ende der Eingabezeichenfolge vorliegen muss. Dies ist mit dem **$**-Anker identisch, jedoch ignoriert **\Z** die [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)-Option. Daher kann hiermit in einer mehrzeiligen Zeichenfolge nur nach einer Übereinstimmung mit dem Ende der letzten Zeile oder der letzten Zeile vor **\n** gesucht werden.

Beachten Sie, dass **\Z** mit **\n**, aber nicht mit **\r\n** übereinstimmt (der CR/LF-Zeichenkombination). Zum Suchen einer Übereinstimmung mit CR/LF schließen Sie **\r \Z** in das Muster des regulären Ausdrucks ein.

Im folgenden Beispiel wird der **\Z**-Anker in einem regulären Ausdruck verwendet, der ähnlich wie das Beispiel aus dem vorherigen Abschnitt „Anfang der Zeichenfolge oder Zeile“ Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Der Teilausdruck `\r?\Z` im regulären Ausdruck `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` stimmt sowohl mit dem Ende einer Zeichenfolge als auch mit einer Zeichenfolge überein, die mit **\n** oder **\r\n** endet. Folglich stimmt jedes Element im Array mit dem Muster des regulären Ausdrucks überein.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  
                          "Chicago Cubs, National League, 1903-present" + Environment.NewLine, 
                          "Detroit Tigers, American League, 1901-present" + Regex.Unescape(@"\n"), 
                          "New York Giants, National League, 1885-1957", 
                          "Washington Senators, American League, 1901-1960" + Environment.NewLine}; 
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z";

      foreach (string input in inputs)
      {
         if (input.Length > 70 || ! input.Contains(",")) continue;

         Console.WriteLine(Regex.Escape(input));
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine("   Match succeeded.");
         else
            Console.WriteLine("   Match failed.");
      }   
   }
}
// The example displays the following output:
//    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
//       Match succeeded.
//    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
//       Match succeeded.
//    Detroit\ Tigers,\ American\ League,\ 1901-present\n
//       Match succeeded.
//    New\ York\ Giants,\ National\ League,\ 1885-1957
//       Match succeeded.
//    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
//       Match succeeded.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf, _
                            "Detroit Tigers, American League, 1901-present" + vbLf, _
                            "New York Giants, National League, 1885-1957", _
                            "Washington Senators, American League, 1901-1960" + vbCrLf }  
      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z"

      For Each input As String In inputs
         If input.Length > 70 Or Not input.Contains(",") Then Continue For

         Console.WriteLine(Regex.Escape(input))
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("   Match succeeded.")
         Else
            Console.WriteLine("   Match failed.")
         End If
      Next   
   End Sub
End Module
' The example displays the following output:
'    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
'       Match succeeded.
'    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
'       Match succeeded.
'    Detroit\ Tigers,\ American\ League,\ 1901-present\n
'       Match succeeded.
'    New\ York\ Giants,\ National\ League,\ 1885-1957
'       Match succeeded.
'    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
'       Match succeeded.
```

## <a name="end-of-string-only-z"></a>Nur Ende der Zeichenfolge: \z

Der **\z**-Anker gibt an, dass eine Übereinstimmung am Ende der Eingabezeichenfolge vorliegen muss. Wie das **$**-Sprachelement ignoriert **\z** die [RegexOptions.Multiline](xref:System.Text.RegularExpressions.RegexOptions.Multiline)-Option. Im Gegensatz zum **\Z**-Sprachelement stimmt **\z** nicht mit einem **\n**-Zeichen am Ende einer Zeichenfolge überein. Daher kann hiermit nur eine Übereinstimmung mit der letzten Zeile der Eingabezeichenfolge gesucht werden.

Im folgenden Beispiel wird der **\z**-Anker in einem regulären Ausdruck verwendet, der ansonsten mit dem Beispiel aus dem vorherigen Abschnitt übereinstimmt und Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Im Beispiel wird versucht, eine Übereinstimmung mit dem Muster eines regulären Ausdrucks `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z` für jedes der fünf Elemente in einem Zeichenfolgenarray zu finden. Zwei der Zeichenfolgen enden mit Wagenrücklauf- und Zeilenvorschubzeichen, eine endet mit einem Zeilenvorschubzeichen, und zwei enden weder mit einem Wagenrücklauf- noch mit einem Zeilenvorschubzeichen. Wie die Ausgabe ergibt, stimmen nur die Zeichenfolgen ohne Wagenrücklauf oder Zeilenvorschub mit dem Muster überein. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957", 
                          "Chicago Cubs, National League, 1903-present" + Environment.NewLine,
                          "Detroit Tigers, American League, 1901-present\\r",
                          "New York Giants, National League, 1885-1957",
                          "Washington Senators, American League, 1901-1960" + Environment.NewLine };  
      string pattern = @"^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z";

      foreach (string input in inputs)
      {
         if (input.Length > 70 || ! input.Contains(",")) continue;

         Console.WriteLine(Regex.Escape(input));
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine("   Match succeeded.");
         else
            Console.WriteLine("   Match failed.");
      }   
   }
}
// The example displays the following output:
//    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
//       Match succeeded.
//    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
//       Match failed.
//    Detroit\ Tigers,\ American\ League,\ 1901-present\n
//       Match failed.
//    New\ York\ Giants,\ National\ League,\ 1885-1957
//       Match succeeded.
//    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
//       Match failed.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "Brooklyn Dodgers, National League, 1911, 1912, 1932-1957",  _
                            "Chicago Cubs, National League, 1903-present" + vbCrLf, _
                            "Detroit Tigers, American League, 1901-present" + vbLf, _
                            "New York Giants, National League, 1885-1957", _
                            "Washington Senators, American League, 1901-1960" + vbCrLf }  
      Dim pattern As String = "^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z"

      For Each input As String In inputs
         If input.Length > 70 Or Not input.Contains(",") Then Continue For

         Console.WriteLine(Regex.Escape(input))
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("   Match succeeded.")
         Else
            Console.WriteLine("   Match failed.")
         End If
      Next   
   End Sub
End Module
' The example displays the following output:
'    Brooklyn\ Dodgers,\ National\ League,\ 1911,\ 1912,\ 1932-1957
'       Match succeeded.
'    Chicago\ Cubs,\ National\ League,\ 1903-present\r\n
'       Match failed.
'    Detroit\ Tigers,\ American\ League,\ 1901-present\n
'       Match failed.
'    New\ York\ Giants,\ National\ League,\ 1885-1957
'       Match succeeded.
'    Washington\ Senators,\ American\ League,\ 1901-1960\r\n
'       Match failed.
```

## <a name="contiguous-matches-g"></a>Aufeinander folgende Übereinstimmungen: \G

Der **\G**-Anker gibt an, dass eine Übereinstimmung an dem Punkt vorliegen muss, an dem die vorherige Übereinstimmung endet. Wenn Sie diesen Anker mit der [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode oder [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode verwenden, wird sichergestellt, dass alle Übereinstimmungen zusammenhängend sind. 

Im folgenden Beispiel werden mithilfe eines regulären Ausdrucks die Namen von Nagetierspezies aus einer durch Trennzeichen getrennten Zeichenfolge extrahiert. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "capybara,squirrel,chipmunk,porcupine,gopher," + 
                     "beaver,groundhog,hamster,guinea pig,gerbil," + 
                     "chinchilla,prairie dog,mouse,rat";
      string pattern = @"\G(\w+\s?\w*),?";
      Match match = Regex.Match(input, pattern);
      while (match.Success) 
      {
         Console.WriteLine(match.Groups[1].Value);
         match = match.NextMatch();
      } 
   }
}
// The example displays the following output:
//       capybara
//       squirrel
//       chipmunk
//       porcupine
//       gopher
//       beaver
//       groundhog
//       hamster
//       guinea pig
//       gerbil
//       chinchilla
//       prairie dog
//       mouse
//       rat
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "capybara,squirrel,chipmunk,porcupine,gopher," + _
                            "beaver,groundhog,hamster,guinea pig,gerbil," + _
                            "chinchilla,prairie dog,mouse,rat"
      Dim pattern As String = "\G(\w+\s?\w*),?"
      Dim match As Match = Regex.Match(input, pattern)
      Do While match.Success
         Console.WriteLine(match.Groups(1).Value)
         match = match.NextMatch()
      Loop 
   End Sub
End Module
' The example displays the following output:
'       capybara
'       squirrel
'       chipmunk
'       porcupine
'       gopher
'       beaver
'       groundhog
'       hamster
'       guinea pig
'       gerbil
'       chinchilla
'       prairie dog
'       mouse
'       rat
```

Der reguläre Ausdruck `\G(\w+\s?\w*),?` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | ----------- 
`\G` | Beginnt die Übereinstimmung am Ende der vorherigen.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`\s?` | Übereinstimmung mit 0 (Null) oder einem Leerzeichen.
`\w*` | Übereinstimmung mit keinem oder mehreren Wortzeichen.
`(\w+\s?\w*)` | Übereinstimmung mit mindestens einem Wortzeichen gefolgt von 0 (Null) oder einem Leerzeichen, gefolgt von 0 (Null) oder weiteren Wortzeichen. Dies ist die erste Erfassungsgruppe.
`,?` | Übereinstimmung mit 0 (Null) oder einem Literal-Kommazeichen.
 
## <a name="word-boundary-b"></a>Wortgrenze: \b

Der **\b**-Anker gibt an, dass die Übereinstimmung an einer Grenze zwischen einem Wortzeichen (dem **\w**-Sprachelement) und einem Nicht-Wortzeichen (dem **\W**-Sprachelement) vorliegen muss. Wortzeichen bestehen aus alphanumerischen Zeichen und Unterstrichen. Bei Nicht-Wortzeichen handelt es sich um alle Zeichen, die weder alphanumerisch noch Unterstriche sind. (Weitere Informationen finden Sie unter [Zeichenklassen in regulären Ausdrücken](classes.md).) Die Übereinstimmung kann auch an einer Wortgrenze am Anfang oder Ende der Zeichenfolge vorliegen.

Der **\b**-Anker wird häufig verwendet, um sicherzustellen, dass ein Teilausdruck statt nur mit Anfang oder Ende mit einem ganzen Wort übereinstimmt. Im folgenden Beispiel wird die Verwendung des regulären Ausdrucks `\bare\w*\b` veranschaulicht. Der Ausdruck stimmt mit jedem Wort überein, das mit der Teilzeichenfolge "are" beginnt. Die Ausgabe des Beispiels veranschaulicht auch, dass **\b** sowohl mit dem Anfang als auch dem Ende der Eingabezeichenfolge übereinstimmt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "area bare arena mare";
      string pattern = @"\bare\w*\b";
      Console.WriteLine("Words that begin with 'are':");
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("'{0}' found at position {1}",
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       Words that begin with 'are':
//       'area' found at position 0
//       'arena' found at position 10
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "area bare arena mare"
      Dim pattern As String = "\bare\w*\b"
      Console.WriteLine("Words that begin with 'are':")
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Words that begin with 'are':
'       'area' found at position 0
'       'arena' found at position 10
```

Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | ----------- 
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`are` | Übereinstimmung mit der Teilzeichenfolge "are".
`\w*` | Übereinstimmung mit keinem oder mehreren Wortzeichen.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
## <a name="non-word-boundary-b"></a>Nicht-Wortgrenze: \B

Der **\B**-Anker gibt an, dass die Übereinstimmung nicht an einer Wortgrenze vorliegen darf. Dies ist das Gegenteil des **\b**-Ankers.

Im folgenden Beispiel wird der **\B**-Anker verwendet, um nach Vorkommen der Teilzeichenfolge „qu“ in einem Wort zu suchen. Das Muster des regulären Ausdrucks `\Bqu\w+` stimmt mit einer Teilzeichenfolge überein, die mit "qu" beginnt, nicht der Wortbeginn ist und bis zum Ende des Worts reicht.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "equity queen equip acquaint quiet";
      string pattern = @"\Bqu\w+";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       'quity' found at position 1
//       'quip' found at position 14
//       'quaint' found at position 21
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "equity queen equip acquaint quiet"
      Dim pattern As String = "\Bqu\w+"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       'quity' found at position 1
'       'quip' found at position 14
'       'quaint' found at position 21
```

Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | ----------- 
`\B` | Übereinstimmung beginnt nicht an einer Wortgrenze.
`qu` | Übereinstimmung mit der Teilzeichenfolge "qu".
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
 
## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)

[Optionen für reguläre Ausdrücke](options.md)
 



<!--HONumber=Nov16_HO3-->


