---
title: "Das Objektmodell für reguläre Ausdrücke"
description: "Das Objektmodell für reguläre Ausdrücke"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a1e611ec-c6a2-48c6-9c52-0ed845787621
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: becfe2624ad1ee1d03707ef48c780f518eb8eb28

---

# <a name="the-regular-expression-object-model"></a>Das Objektmodell für reguläre Ausdrücke

In diesem Thema wird das Objektmodell beschrieben, das beim Arbeiten mit regulären .NET-Ausdrücken verwendet wird. Es enthält die folgenden Abschnitte:

* [Das Modul für reguläre Ausdrücke](#the-regular-expression-engine)

* [Die MatchCollection- und Match-Objekte](#the-matchcollection-and-match-objects)

* [Die Gruppensammlung](#the-group-collection)

* [Die erfasste Gruppe](#the-captured-group)

* [Die Erfassungssammlung](#the-capture-collection)

* [Die einzelne Erfassung](#the-individual-capture)

## <a name="the-regular-expression-engine"></a>Das Modul für reguläre Ausdrücke

Das Modul für reguläre Ausdrücke in .NET wird durch die [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse dargestellt. Das Modul für reguläre Ausdrücke ist für das Analysieren und Kompilieren eines regulären Ausdrucks sowie für das Ausführen von Vorgängen zuständig, die dem Muster eines regulären Ausdrucks mit einer Eingabezeichenfolge entsprechen. Das Modul ist die zentrale Komponente im .NET-Objektmodell für reguläre Ausdrücke.

Das Modul für reguläre Ausdrücke kann auf zwei verschiedene Arten verwendet werden:

* Durch Aufrufen der statischen Methoden der [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse. Die Methodenparameter schließen die Eingabezeichenfolge und das Muster eines regulären Ausdrucks ein. Das Modul für reguläre Ausdrücke führt eine Zwischenspeicherung der regulären Ausdrücke aus, die in statischen Methodenaufrufen verwendet werden. Daher zeigen wiederholte Aufrufe von statischen regulären Ausdrucksmethoden, für die der gleiche reguläre Ausdruck verwendet wird, eine relativ gute Leistung.

* Durch Instanziieren eines [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts und durch Übergeben eines regulären Ausdrucks an den Klassenkonstruktor. In diesem Fall ist das [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt unveränderlich (schreibgeschützt) und stellt ein Modul für reguläre Ausdrücke dar, das eng an einen einzelnen regulären Ausdruck gekoppelt ist. Da von Regex-Instanzen verwendete reguläre Ausdrücke nicht zwischengespeichert werden, sollte ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt nicht mehrmals mit dem gleichen regulären Ausdruck instanziiert werden.

Sie können die Methoden der [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse aufrufen, um die folgenden Vorgänge auszuführen: 

* Bestimmen, ob eine Zeichenfolge mit einem Muster eines regulären Ausdrucks übereinstimmt.

* Extrahieren einer einzelnen Übereinstimmung oder der ersten Übereinstimmung.

* Extrahieren aller Übereinstimmungen.

* Ersetzen einer übereinstimmenden Teilzeichenfolge.

* Teilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray.

Diese Vorgänge werden in den folgenden Abschnitten beschrieben.

### <a name="matching-a-regular-expression-pattern"></a>Vergleich eines Muster eines regulären Ausdrucks

Von der [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode wird `true` zurückgegeben, falls die Zeichenfolge mit dem Muster übereinstimmt, bzw. `false`, wenn dies nicht der Fall ist. Die [IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String))-Methode wird häufig dazu verwendet, um Zeichenfolgeneingaben zu überprüfen. Durch den folgenden Code wird z. B. sichergestellt, dass eine Zeichenfolge mit einer gültigen Sozialversicherungsnummer in den USA übereinstimmt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] values = { "111-22-3333", "111-2-3333"};
      string pattern = @"^\d{3}-\d{2}-\d{4}$";
      foreach (string value in values) {
         if (Regex.IsMatch(value, pattern))
            Console.WriteLine("{0} is a valid SSN.", value);
         else   
            Console.WriteLine("{0}: Invalid", value);
      }
   }
}
// The example displays the following output:
//       111-22-3333 is a valid SSN.
//       111-2-3333: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim values() As String = { "111-22-3333", "111-2-3333"}
      Dim pattern As String = "^\d{3}-\d{2}-\d{4}$"
      For Each value As String In values
         If Regex.IsMatch(value, pattern) Then
            Console.WriteLine("{0} is a valid SSN.", value)
         Else   
            Console.WriteLine("{0}: Invalid", value)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       111-22-3333 is a valid SSN.
'       111-2-3333: Invalid
```

Das Muster für reguläre Ausdrücke `^\d{3}-\d{2}-\d{4}$` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | ----------- 
`^` | Entsprechung für den Anfang der Eingabezeichenfolge finden.
`\d{3}` | Entsprechung für drei Dezimalstellen finden.
`-` | Entsprechung für einen Bindestrich finden.
`\d{2}` | Entsprechung für zwei Dezimalstellen finden.
`-` | Entsprechung für einen Bindestrich finden.
`\d{4}` | Entsprechung für vier Dezimalstellen finden.
`$` | Entsprechung für das Ende der Eingabezeichenfolge finden.
 
### <a name="extracting-a-single-match-or-the-first-match"></a>Extrahieren einer einzelnen Übereinstimmung oder der ersten Übereinstimmung

Von der [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String))-Methode wird ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt zurückgegeben, das Informationen zur ersten Teilzeichenfolge enthält, die mit einem Muster für reguläre Ausdrücke übereinstimmt. Wenn die `Match.Success`-Eigenschaft `true` zurückgibt und angibt, dass eine Übereinstimmung gefunden wurde, können Sie Informationen zu nachfolgenden Übereinstimmungen abrufen, indem Sie die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode aufrufen. Diese Methodenaufrufe können fortgesetzt werden, bis die `Match.Success`-Eigenschaft `false` zurückgibt. Im folgenden Code wird zum Beispiel mithilfe der Methode [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String)) das erste Vorkommen eines doppelt vorhandenen Worts in einer Zeichenfolge gesucht. Anschließend wird die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode aufgerufen, um zusätzliche Vorkommen zu suchen. Im Beispiel wird die `Match.Success`-Eigenschaft nach jedem Methodenaufruf überprüft, um zu bestimmen, ob die aktuelle Übereinstimmung erfolgreich war und ob ein Aufruf der [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode folgen soll.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      Match match = Regex.Match(input, pattern);
      while (match.Success)
      {
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
         match = match.NextMatch();
      }                       
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      Dim match As Match = Regex.Match(input, pattern)
      Do While match.Success
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
         match = match.NextMatch()
      Loop                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

Das Muster für reguläre Ausdrücke `\b(\w+)\W+(\1)\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | ----------- 
`\b` | Beginnt den Vergleich an einer Wortgrenze.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\W+` | Entsprechung für mindestens ein Nicht-Wortzeichen finden.
`(\1)` | Entsprechung für die erste erfasste Zeichenfolge finden. Dies ist die zweite Erfassungsgruppe. 
`\b` | Beendet den Vergleich an einer Wortgrenze.
 
### <a name="extracting-all-matches"></a>Extrahieren aller Übereinstimmungen

Von der [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode wird ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt zurückgegeben, das Informationen zu allen Übereinstimmungen enthält, die vom Modul für reguläre Ausdrücke in der Eingabezeichenfolge gefunden wurden. Zum Beispiel kann das vorherige Beispiel neu geschrieben werden, um die [Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode anstelle der Methoden [Match](xref:System.Text.RegularExpressions.Regex.Match(System.String)) und [NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) aufzurufen.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "This is a a farm that that raises dairy cattle."; 
      string pattern = @"\b(\w+)\W+(\1)\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("Duplicate '{0}' found at position {1}.",  
                           match.Groups[1].Value, match.Groups[2].Index);
   }
}
// The example displays the following output:
//       Duplicate 'a' found at position 10.
//       Duplicate 'that' found at position 22.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "This is a a farm that that raises dairy cattle." 
      Dim pattern As String = "\b(\w+)\W+(\1)\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("Duplicate '{0}' found at position {1}.", _ 
                           match.Groups(1).Value, match.Groups(2).Index)
      Next                       
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'a' found at position 10.
'       Duplicate 'that' found at position 22.
```

### <a name="replacing-a-matched-substring"></a>Ersetzen einer übereinstimmenden Teilzeichenfolge

Die [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))-Methode ersetzt jede Teilzeichenfolge, die das Muster für reguläre Ausdrücke mit einer angegebenen Zeichenfolge oder einem Muster für reguläre Ausdrücke abgleicht, und gibt die gesamte Eingabezeichenfolge mit Ersetzungen zurück. Beispielsweise fügt der folgende Code ein US-Währungssymbol vor einer Dezimalzahl in einer Zeichenfolge hinzu.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+\.\d{2}\b";
      string replacement = "$$$&"; 
      string input = "Total Cost: 103.64";
      Console.WriteLine(Regex.Replace(input, pattern, replacement));     
   }
}
// The example displays the following output:
//       Total Cost: $103.64
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+\.\d{2}\b"
      Dim replacement As String = "$$$&" 
      Dim input As String = "Total Cost: 103.64"
      Console.WriteLine(Regex.Replace(input, pattern, replacement))     
   End Sub
End Module
' The example displays the following output:
'       Total Cost: $103.64
```

Das Muster für reguläre Ausdrücke `\b\d+\.\d{2}\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | ----------- 
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
`\.` | Entsprechung für einen Punkt finden.
`\d{2}` | Entsprechung für zwei Dezimalstellen finden.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Das Ersetzungsmuster `$$$&` wird gemäß der Darstellung in der folgenden Tabelle interpretiert.

Muster | Ersetzungszeichenfolge
------- | ------------------ 
`$$` | Das Dollarzeichen (**$**).
`$&` | Die gesamte abgeglichene Teilzeichenfolge.
 
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Aufteilen einer einzelnen Zeichenfolge in ein Zeichenfolgenarray

Mit der [Regex.Split](xref:System.Text.RegularExpressions.Regex.Split(System.String))-Methode wird die Eingabezeichenfolge an den Stellen aufgeteilt, die durch eine Übereinstimmung bei einem regulären Ausdruck definiert wurde. Im folgenden Code werden z. B. die Elemente in ein Zeichenfolgenarray in einer nummerierten Liste eingefügt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea";
      string pattern = @"\b\d{1,2}\.\s";
      foreach (string item in Regex.Split(input, pattern))
      {
         if (! String.IsNullOrEmpty(item))
            Console.WriteLine(item);
      }      
   }
}
// The example displays the following output:
//       Eggs
//       Bread
//       Milk
//       Coffee
//       Tea
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "1. Eggs 2. Bread 3. Milk 4. Coffee 5. Tea"
      Dim pattern As String = "\b\d{1,2}\.\s"
      For Each item As String In Regex.Split(input, pattern)
         If Not String.IsNullOrEmpty(item) Then
            Console.WriteLine(item)
         End If
      Next      
   End Sub
End Module
' The example displays the following output:
'       Eggs
'       Bread
'       Milk
'       Coffee
'       Tea
```

Das Muster für reguläre Ausdrücke `\b\d{1,2}\.\s` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\d{1,2}` | Entsprechung für eine oder zwei Dezimalstellen finden.
`\.` | Entsprechung für einen Punkt finden.
`\s` | Entsprechung für ein Leerraumzeichen finden.
 
## <a name="the-matchcollection-and-match-objects"></a>Die MatchCollection- und Match-Objekte

[Regex](xref:System.Text.RegularExpressions.Regex)-Methoden geben zwei Objekte zurück, die Teil des Objektmodells für reguläre Ausdrücke sind: das [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt und das [Match](xref:System.Text.RegularExpressions.Match)-Objekt. 

### <a name="the-match-collection"></a>Die Match-Sammlung

Die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode gibt ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt mit [Match](xref:System.Text.RegularExpressions.Match)-Objekten zurück, die alle Übereinstimmungen darstellen, die das Modul für reguläre Ausdrücke gefunden hat, und zwar in der Reihenfolge, in der sie in der Eingabezeichenfolge auftreten. Wenn keine Übereinstimmungen vorhanden sind, gibt die Methode ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt zurück, das ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt ohne Member enthält. Die [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item`-Eigenschaft ermöglicht den Zugriff auf einzelne Member der Sammlung nach Index, von null bis eins weniger als es dem Wert der [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count)-Eigenschaft entspricht. „Item“ ist der Indexer (in C#) und die Standardeigenschaft der Sammlung (in Visual Basic).

Der Aufruf der [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode füllt standardmäßig das [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt mithilfe der verzögerten Auswertung auf. Der Zugriff auf Eigenschaften, die eine vollständig aufgefüllte Sammlung erfordern, z.B. die Eigenschaften [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count) und `Item`, führt möglicherweise zu Leistungseinbußen. Daher wird empfohlen, dass Sie über das [IEnumerator](xref:System.Collections.IEnumerator)-Objekt auf die Sammlung zugreifen, das von der [MatchCollection.GetEnumerator](xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator)-Methode zurückgegeben wird. Einzelne Sprachen stellen Konstrukte bereit, z.B. `foreach` in C# und „For Each“ in Visual Basic, die die IEnumerator](xref:System.Collections.IEnumerator)-Schnittstelle der Sammlung umschließen.

Im folgenden Beispiel wird mithilfe der [Regex.Matches(String)](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode ein [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt mit sämtlichen Übereinstimmungen aufgefüllt, die in einer Eingabezeichenfolge gefunden wurden. Im Beispiel wird die Auflistung aufgeführt, die Übereinstimmungen werden in ein Zeichenfolgenarray kopiert, und die Zeichenpositionen werden in einem ganzzahligen Array erfasst.

```csharp
using System;
using System.Collections.Generic;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
       MatchCollection matches;
       List<string> results = new List<string>();
       List<int> matchposition = new List<int>();

       // Create a new Regex object and define the regular expression.
       Regex r = new Regex("abc");
       // Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd");
       // Enumerate the collection to retrieve all matches and positions.
       foreach (Match match in matches)
       {
          // Add the match string to the string array.
           results.Add(match.Value);
           // Record the character position where the match was found.
           matchposition.Add(match.Index);
       }
       // List the results.
       for (int ctr = 0; ctr < results.Count; ctr++)
         Console.WriteLine("'{0}' found at position {1}.", 
                           results[ctr], matchposition[ctr]);  
   }
}
// The example displays the following output:
//       'abc' found at position 3.
//       'abc' found at position 7.
```

```vb
Imports System.Collections.Generic
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
       Dim matches As MatchCollection
       Dim results As New List(Of String)
       Dim matchposition As New List(Of Integer)

       ' Create a new Regex object and define the regular expression.
       Dim r As New Regex("abc")
       ' Use the Matches method to find all matches in the input string.
       matches = r.Matches("123abc4abcd")
       ' Enumerate the collection to retrieve all matches and positions.
       For Each match As Match In matches
          ' Add the match string to the string array.
           results.Add(match.Value)
           ' Record the character position where the match was found.
           matchposition.Add(match.Index)
       Next
       ' List the results.
       For ctr As Integer = 0 To results.Count - 1
         Console.WriteLine("'{0}' found at position {1}.", _
                           results(ctr), matchposition(ctr))  
       Next
   End Sub
End Module
' The example displays the following output:
'       'abc' found at position 3.
'       'abc' found at position 7.
```

### <a name="the-match"></a>Die Übereinstimmung

Die [Match](xref:System.Text.RegularExpressions.Match)-Klasse stellt das Ergebnis einer einzelnen Übereinstimmung eines regulären Ausdrucks dar. Es gibt zwei Möglichkeiten für den Zugriff auf [Match](xref:System.Text.RegularExpressions.Match)-Objekte:

* Sie können von dem [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt abgerufen werden, das von der Regex.Matches-Methode zurückgegeben wird. Um einzelne [Match](xref:System.Text.RegularExpressions.Match)-Objekte abzurufen, durchlaufen Sie die Sammlung über ein `foreach`-Konstrukt (in C#) oder ein `For Each...Next`-Konstrukt (in Visual Basic), oder rufen Sie mithilfe der [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection) `Item`-Eigenschaft ein bestimmtes [Match](xref:System.Text.RegularExpressions.Match)-Objekt nach Index oder nach Name ab. Sie können auch einzelne [Match](xref:System.Text.RegularExpressions.Match)-Objekte aus der Sammlung abrufen, indem Sie die Sammlung nach Index durchlaufen, von 0 (null) bis eins weniger, als es der Anzahl der Objekte in der Sammlung entspricht. Bei dieser Methode wird jedoch keine verzögerte Auswertung genutzt, weil dabei auf die [MatchCollection.Count](xref:System.Text.RegularExpressions.MatchCollection.Count)-Eigenschaft zugegriffen wird. 

  Im folgenden Beispiel werden einzelne [Match](xref:System.Text.RegularExpressions.Match)-Objekte aus einem [MatchCollection](xref:System.Text.RegularExpressions.MatchCollection)-Objekt abgerufen, indem die Sammlung mit dem `foreach`-Konstrukt durchlaufen wird. Der reguläre Ausdruck stimmt mit der Zeichenfolge "abc" in der Eingabezeichenfolge überein.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        foreach (Match match in Regex.Matches(input, pattern))
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
        Next                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

* Durch Aufrufen der [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String))-Methode, die ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt zurückgibt, das die erste Übereinstimmung in einer Zeichenfolge oder einem Teil einer Zeichenfolge darstellt. Sie können bestimmen, ob die Übereinstimmung gefunden wurde, indem der Wert der `Match.Success`-Eigenschaft abgerufen wird. Um [Match](xref:System.Text.RegularExpressions.Match)-Objekte abzurufen, die nachfolgende Übereinstimmungen darstellen, rufen Sie die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode wiederholt auf, bis die `Success`-Eigenschaft des zurückgegebenen [Match](xref:System.Text.RegularExpressions.Match)-Objekts `false` lautet. 

  Im folgenden Beispiel werden die [Regex.Match(String, String)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String))-Methode und die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode verwendet, um die Zeichenfolge „abc“ in der Eingabezeichenfolge abzugleichen.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "abc";
        string input = "abc123abc456abc789";
        Match match = Regex.Match(input, pattern);
        while (match.Success)
        {
           Console.WriteLine("{0} found at position {1}.", 
                             match.Value, match.Index);
           match = match.NextMatch();                  
        }                     
     }
  }
  // The example displays the following output:
  //       abc found at position 0.
  //       abc found at position 6.
  //       abc found at position 12.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "abc"
        Dim input As String = "abc123abc456abc789"
        Dim match As Match = Regex.Match(input, pattern)
        Do While match.Success
           Console.WriteLine("{0} found at position {1}.", _
                             match.Value, match.Index)
           match = match.NextMatch()                  
        Loop                     
     End Sub
  End Module
  ' The example displays the following output:
  '       abc found at position 0.
  '       abc found at position 6.
  '       abc found at position 12.
  ```

Zwei Eigenschaften der [Match](xref:System.Text.RegularExpressions.Match)-Klasse geben Sammlungsobjekte zurück:

* Die [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft gibt ein [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt zurück, das Informationen zu den Teilzeichenfolgen enthält, die mit Erfassungsgruppen im Muster für reguläre Ausdrücke übereinstimmen. 

* Die `Match.Captures`-Eigenschaft gibt ein [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt mit eingeschränkter Verwendung zurück. Die Sammlung wird nicht für ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt aufgefüllt, dessen `Success`-Eigenschaft `false` lautet. Andernfalls enthält es ein einzelnes [Capture](xref:System.Text.RegularExpressions.Capture)-Objekt, das über die gleichen Informationen wie das [Match](xref:System.Text.RegularExpressions.Match)-Objekt verfügt. 

Weitere Informationen zu diesen Objekten finden Sie in den Abschnitten [Die Gruppensammlung](#the-group-collection) und [Die Erfassungssammlung](#the-capture-collection) im weiteren Verlauf dieses Themas.

Zwei zusätzliche Eigenschaften der [Match](xref:System.Text.RegularExpressions.Match)-Klasse stellen Informationen zur Übereinstimmung bereit. Die `Match.Value`-Eigenschaft gibt die Teilzeichenfolge in der Eingabezeichenfolge zurück, die mit dem Muster eines regulären Ausdrucks übereinstimmt. Die `Match.Index`-Eigenschaft gibt die nullbasierte Anfangsposition der entsprechenden Zeichenfolge in der Eingabezeichenfolge zurück.

Die [Match](xref:System.Text.RegularExpressions.Match)-Klasse besitzt ebenfalls zwei Methoden zum Mustervergleich:

* Die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode sucht die Übereinstimmung nach der Übereinstimmung, die durch das aktuelle [Match](xref:System.Text.RegularExpressions.Match)-Objekt dargestellt wird, und gibt ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt zurück, das diese Übereinstimmung darstellt.

* Die [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode führt einen angegebenen Ersetzungsvorgang in der entsprechenden Zeichenfolge aus und gibt das Ergebnis zurück. 


Im folgenden Beispiel werden mit der [Match.Result](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode jeder Zahl, die zwei Nachkommastellen enthält, ein **$**-Symbol und ein Leerzeichen vorangestellt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\d+(,\d{3})*\.\d{2}\b";
      string input = "16.32\n194.03\n1,903,672.08"; 

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Result("$$ $&"));
   }
}
// The example displays the following output:
//       $ 16.32
//       $ 194.03
//       $ 1,903,672.08
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\d+(,\d{3})*\.\d{2}\b"
      Dim input As String = "16.32" + vbCrLf + "194.03" + vbCrLf + "1,903,672.08" 

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Result("$$ $&"))
      Next
   End Sub
End Module
' The example displays the following output:
'       $ 16.32
'       $ 194.03
'       $ 1,903,672.08
```

Das Muster für reguläre Ausdrücke `\b\d+(,\d{3})*\.\d{2}\b` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden.
`(,\d{3})*` | Entsprechung für null oder mehr Vorkommen eines Kommas finden, auf das Dezimalstellen folgen.
`\.` | Entsprechung für das Dezimaltrennzeichenzeichen finden.
`\d{2} | Entsprechung für zwei Dezimalstellen finden.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Das Ersetzungsmuster **$$ $&** gibt an, dass die übereinstimmende Teilzeichenfolge durch ein Dollarzeichensymbol (**$**, das `$$`-Muster), ein Leerzeichen und den Wert der Übereinstimmung (das `$&`-Muster) ersetzt werden soll.

## <a name="the-group-collection"></a>Die Gruppensammlung

Die [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft gibt ein [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt zurück, das [Group](xref:System.Text.RegularExpressions.Group)-Objekte enthält, die erfasste Gruppen in einer einzelnen Übereinstimmung darstellen. Das erste [Group](xref:System.Text.RegularExpressions.Group)-Objekt in der Sammlung (bei Index 0) stellt die gesamte Übereinstimmung dar. Jedes Objekt, das folgt, stellt die Ergebnisse einer einzelnen Erfassungsgruppe dar. 

Sie können einzelne [Group](xref:System.Text.RegularExpressions.Group)-Objekte in der Sammlung mit der [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32))-Eigenschaft abrufen. Sie können unbenannte Gruppen durch ihre Ordnungsposition in der Auflistung abrufen und benannte Gruppen entweder nach dem Namen oder nach der Ordnungsposition abrufen. Unbenannte Erfassungen werden zuerst in der Auflistung angezeigt und werden von links nach rechts in der Reihenfolge indiziert, in der sie im Muster eines regulären Ausdrucks angezeigt werden. Benannte Erfassungen werden nach unbenannten Erfassungen von links nach rechts in der Reihenfolge indiziert, in der sie im Muster eines regulären Ausdrucks angezeigt werden. Um festzustellen, welche nummerierten Gruppen in der Sammlung verfügbar sind, die für eine bestimmte Methode für Übereinstimmungen mit regulären Ausdrücken zurückgegeben wird, können Sie die Instanzmethode [Regex.GetGroupNumbers](xref:System.Text.RegularExpressions.Regex.GetGroupNumbers) aufrufen. Um festzustellen, welche benannten Gruppen in der Sammlung verfügbar sind, können Sie die Instanzmethode [Regex.GetGroupNames](xref:System.Text.RegularExpressions.Regex.GetGroupNames) aufrufen. Beide Methoden sind besonders nützlich in Allzweckroutinen, die die von beliebigen regulären Ausdrücken gefundenen Übereinstimmungen analysieren. 

Die [GroupCollection.Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32))-Eigenschaft ist der Indexer der Sammlung in C# und der Standardeigenschaft des Sammlungsobjekts in Visual Basic. Dies bedeutet, dass auf diese einzelnen [Group](xref:System.Text.RegularExpressions.Group)-Objekte wie folgt nach Index (oder nach Name bei benannten Gruppen) zugegriffen werden kann: 

```csharp
Group group = match.Groups[ctr];
```

```vb
Dim group As Group = match.Groups(ctr)
```

Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der Gruppierungskonstrukte verwendet, um Monat, Tag und Jahr eines Datums zu erfassen. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)\s(\d{1,2}),\s(\d{4})\b";
      string input = "Born: July 28, 1989";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
         for (int ctr = 0; ctr <  match.Groups.Count; ctr++)
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups[ctr].Value);
    }
}
// The example displays the following output:
//       Group 0: July 28, 1989
//       Group 1: July
//       Group 2: 28
//       Group 3: 1989
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)\s(\d{1,2}),\s(\d{4})\b"
      Dim input As String = "Born: July 28, 1989"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         For ctr As Integer = 0 To match.Groups.Count - 1
            Console.WriteLine("Group {0}: {1}", ctr, match.Groups(ctr).Value)
         Next      
      End If   
   End Sub
End Module
' The example displays the following output:
'       Group 0: July 28, 1989
'       Group 1: July
'       Group 2: 28
'       Group 3: 1989
```

Das Muster für reguläre Ausdrücke `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(\d{1,2})` | Entsprechung für eine oder zwei Dezimalstellen finden. Dies ist die zweite Erfassungsgruppe.
`,` | Entsprechung für ein Komma finden.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(\d{4})` | Entsprechung für vier Dezimalstellen finden. Dies ist die dritte Erfassungsgruppe.
`\b` | Beendet den Vergleich an einer Wortgrenze.
 
## <a name="the-captured-group"></a>Die erfasste Gruppe

Die [Group](xref:System.Text.RegularExpressions.Group)-Klasse stellt das von einer einzelnen Erfassungsgruppe erfasste Ergebnis dar. [Group](xref:System.Text.RegularExpressions.Group)-Objekte, die die in einem regulären Ausdruck definierten Erfassungsgruppen darstellen, werden von der [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32))-Eigenschaft des [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekts zurückgegeben, das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegeben wurde. Die [Item](xref:System.Text.RegularExpressions.GroupCollection.Item(System.Int32))-Eigenschaft ist der Indexer (in C#) und die Standardeigenschaft (in Visual Basic) der [Group](xref:System.Text.RegularExpressions.Group)-Klasse. Sie können auch einzelne Member abrufen, indem Sie die Sammlung mit dem `foreach`-Konstrukt durchlaufen. Ein Beispiel finden Sie im vorherigen Abschnitt.

Im folgenden Beispiel werden verschachtelte Gruppierungskonstrukte verwendet, um Teilzeichenfolgen in Gruppen aufzuzeichnen. Das Muster eines regulären Ausdrucks `(a(b))c` stimmt mit der Zeichenfolge "abc" überein. Es weist die Teilzeichenfolgen "ab" der ersten Erfassungsgruppe und die Teilzeichenfolge "b" der zweiten Erfassungsgruppe zu.

```csharp
List<int> matchposition = new List<int>();
List<string> results = new List<string>();
// Define substrings abc, ab, b.
Regex r = new Regex("(a(b))c"); 
Match m = r.Match("abdabc");
for (int i = 0; m.Groups[i].Value != ""; i++) 
{
   // Add groups to string array.
   results.Add(m.Groups[i].Value); 
   // Record character position.
   matchposition.Add(m.Groups[i].Index); 
}

// Display the capture groups.
for (int ctr = 0; ctr < results.Count; ctr++)
   Console.WriteLine("{0} at position {1}", 
                     results[ctr], matchposition[ctr]);
// The example displays the following output:
//       abc at position 3
//       ab at position 3
//       b at position 4
```

```vb
Dim matchposition As New List(Of Integer)
 Dim results As New List(Of String)
 ' Define substrings abc, ab, b.
 Dim r As New Regex("(a(b))c") 
 Dim m As Match = r.Match("abdabc")
 Dim i As Integer = 0
 While Not (m.Groups(i).Value = "")    
    ' Add groups to string array.
    results.Add(m.Groups(i).Value)     
    ' Record character position. 
    matchposition.Add(m.Groups(i).Index) 
     i += 1
 End While

 ' Display the capture groups.
 For ctr As Integer = 0 to results.Count - 1
    Console.WriteLine("{0} at position {1}", _ 
                      results(ctr), matchposition(ctr))
 Next                     
' The example displays the following output:
'       abc at position 3
'       ab at position 3
'       b at position 4
```

Im folgenden Codebeispiel werden benannte Gruppierungskonstrukte verwendet, um Teilzeichenfolgen in einer Zeichenfolge zu erfassen, die Daten im Format "DATENNAME:WERT" enthält. Durch den regulären Ausdruck werden diese am Doppelpunkt (:) getrennt.

```csharp
Regex r = new Regex("^(?<name>\\w+):(?<value>\\w+)");
Match m = r.Match("Section1:119900");
Console.WriteLine(m.Groups["name"].Value);
Console.WriteLine(m.Groups["value"].Value);
// The example displays the following output:
//       Section1
//       119900
```

```vb
Dim r As New Regex("^(?<name>\w+):(?<value>\w+)")
Dim m As Match = r.Match("Section1:119900")
Console.WriteLine(m.Groups("name").Value)
Console.WriteLine(m.Groups("value").Value)
' The example displays the following output:
'       Section1
'       119900
```

Das Muster für reguläre Ausdrücke `^(?<name>\w+):(?<value>\w+)` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`^` | Beginnt den Vergleich am Anfang der Eingabezeichenfolge.
`(?<name>\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Der Name dieser Erfassungsgruppe ist „name“.
`:` | Entsprechung für einen Doppelpunkt finden.
`(?<value>\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Der Name dieser Erfassungsgruppe ist „value“.
 
Die Eigenschaften der [Group](xref:System.Text.RegularExpressions.Group)-Klasse enthalten Informationen zur erfassten Gruppe: Die `Group.Value`-Eigenschaft enthält die erfasste Teilzeichenfolge, die `Group.Index`-Eigenschaft gibt die Anfangsposition der erfassten Gruppe im Eingabetext an, die `Group.Length`-Eigenschaft enthält die Länge des erfassten Texts, und die `Group.Success`-Eigenschaft gibt an, ob eine Teilzeichenfolge dem Muster entsprach, das durch die Erfassungsgruppe definiert wurde.

Durch Anwenden von Quantifizierern auf eine Gruppe (siehe [Quantifizierer in regulären Ausdrücken](quantifiers.md)) wird die Beziehung einer Erfassung pro Erfassungsgruppe in zweifacher Hinsicht geändert:

* Wenn der __*__-Quantifizierer oder der __*?__-Quantifizierer (der null oder mehr Übereinstimmungen angibt) für eine Gruppe übernommen wird, verfügt eine Erfassungsgruppe möglicherweise über keine Übereinstimmung in der Eingabezeichenfolge. Wenn kein erfasster Text vorhanden ist, werden die Eigenschaften des [Group](xref:System.Text.RegularExpressions.Group)-Objekts entsprechend der Darstellung in der folgenden Tabelle festgelegt.

  Gruppeneigenschaft | Wert
  -------------- | ----- 
  `Success` | `false`
  `Value` | [String.Empty](xref:System.String.Empty) 
  `Length` | 0
 
  Dies wird im folgenden Beispiel veranschaulicht. Im Muster eines regulären Ausdrucks `aaa(bbb)*ccc` kann es für die erste Erfassungsgruppe (die Teilzeichenfolge "bbb") null oder mehrere Übereinstimmungen geben. Da die Eingabezeichenfolge "aaaccc" dem Muster entspricht, weist die Erfassungsgruppe keine Übereinstimmung auf.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "aaa(bbb)*ccc";
        string input = "aaaccc";
        Match match = Regex.Match(input, pattern);
        Console.WriteLine("Match value: {0}", match.Value);
        if (match.Groups[1].Success)
           Console.WriteLine("Group 1 value: {0}", match.Groups[1].Value);
        else
           Console.WriteLine("The first capturing group has no match.");
     }
  }
  // The example displays the following output:
  //       Match value: aaaccc
  //       The first capturing group has no match.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "aaa(bbb)*ccc"
        Dim input As String = "aaaccc"
        Dim match As Match = Regex.Match(input, pattern)
        Console.WriteLine("Match value: {0}", match.Value)
        If match.Groups(1).Success Then
           Console.WriteLine("Group 1 value: {0}", match.Groups(1).Value)
        Else
           Console.WriteLine("The first capturing group has no match.")
       End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match value: aaaccc
  '       The first capturing group has no match.
  ```

* Quantifizierer können mit mehreren Vorkommen eines Musters übereinstimmen, das durch eine Erfassungsgruppe definiert wird. In diesem Fall enthalten die `Value`-Eigenschaft und die `Length`-Eigenschaft eines [Group](xref:System.Text.RegularExpressions.Group)-Objekts nur Informationen zur letzten erfassten Teilzeichenfolge. Der folgende reguläre Ausdruck entspricht z. B. einem einzelnen Satz, der mit einem Punkt endet. Es werden zwei Gruppierungskonstrukte verwendet: Mit dem ersten Konstrukt werden einzelne Wörter mit einem Leerstellenzeichen erfasst und mit dem zweiten einzelne Wörter. Wie die Ausgabe des Beispiels zeigt, erfasst die zweite Erfassungsgruppe nur das letzte Wort, obwohl mit dem regulären Ausdruck ein vollständiger Satz erfasst wird.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = @"\b((\w+)\s?)+\.";
        string input = "This is a sentence. This is another sentence.";
        Match match = Regex.Match(input, pattern);
        if (match.Success)
        {
           Console.WriteLine("Match: " + match.Value);
           Console.WriteLine("Group 2: " + match.Groups[2].Value);
        }   
     }
  }
  // The example displays the following output:
  //       Match: This is a sentence.
  //       Group 2: sentence
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "\b((\w+)\s?)+\."
        Dim input As String = "This is a sentence. This is another sentence."
        Dim match As Match = Regex.Match(input, pattern)
        If match.Success Then
           Console.WriteLine("Match: " + match.Value)
           Console.WriteLine("Group 2: " + match.Groups(2).Value)
        End If   
     End Sub
  End Module
  ' The example displays the following output:
  '       Match: This is a sentence.
  '       Group 2: sentence
  ```

## <a name="the-capture-collection"></a>Die Erfassungssammlung

Das [Group](xref:System.Text.RegularExpressions.Group)-Objekt enthält nur Informationen zur letzten Erfassung. Allerdings sind alle Erfassungen, die von einer Erfassungsgruppe gemacht wurden, nach wie vor über das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt verfügbar, das von der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft zurückgegeben wird. Jeder Member der Sammlung ist ein [Capture](xref:System.Text.RegularExpressions.Capture)-Objekt, das eine von dieser Erfassungsgruppe durchgeführte Erfassung darstellt, und zwar in der Reihenfolge, in der sie erfasst wurden (und daher in der Reihenfolge, in der die erfassten Zeichenfolgen von links nach rechts in der Eingabezeichenfolge abgeglichen wurden). Einzelne [Capture](xref:System.Text.RegularExpressions.Capture)-Objekte können auf zwei unterschiedliche Arten aus der Sammlung abgerufen werden: 

* Durch das Durchlaufen der Sammlung mit einem Konstrukt wie `foreach` (in C#) oder `For Each` (in Visual Basic).

* Mit der [CaptureCollection.Item](xref:System.Text.RegularExpressions.CaptureCollection.Item(System.Int32))-Eigenschaft, um ein bestimmtes Objekt nach Index abzurufen. Die Item-Eigenschaft ist die Standardeigenschaft des [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekts (in Visual Basic) oder des Indexers (in C#).


Wenn ein Quantifizierer nicht für eine Erfassungsgruppe übernommen wird, enthält das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt ein einzelnes [Capture](xref:System.Text.RegularExpressions.Capture)-Objekt, das von geringem Interesse ist, da es Informationen zur gleichen Übereinstimmung wie das [Group](xref:System.Text.RegularExpressions.Group)-Objekt enthält. Wenn ein Quantifizierer für eine Erfassungsgruppe übernommen wird, enthält das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt alle von der Erfassungsgruppe durchgeführten Erfassungen, und der letzte Member der Sammlung stellt die gleiche Erfassung wie das [Group](xref:System.Text.RegularExpressions.Group)-Objekt dar. 

Wenn Sie zum Beispiel das Muster `((a(b))c)+` für reguläre Ausdrücke verwenden (wobei der `+`-Quantifizierer mindestens eine Übereinstimmung angibt), um Übereinstimmungen von der Zeichenfolge „abcabcabc“ zu erfassen, enthält das [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt für jedes [Group](xref:System.Text.RegularExpressions.Group)-Objekt drei Member.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "((a(b))c)+";
      string input = "abcabcabc";

      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Match: '{0}' at position {1}",  
                           match.Value, match.Index);
         GroupCollection groups = match.Groups;
         for (int ctr = 0; ctr < groups.Count; ctr++) {
            Console.WriteLine("   Group {0}: '{1}' at position {2}", 
                              ctr, groups[ctr].Value, groups[ctr].Index);
            CaptureCollection captures = groups[ctr].Captures;
            for (int ctr2 = 0; ctr2 < captures.Count; ctr2++) {
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", 
                                 ctr2, captures[ctr2].Value, captures[ctr2].Index);
            }                     
         }
      }
   }
}
// The example displays the following output:
//       Match: 'abcabcabc' at position 0
//          Group 0: 'abcabcabc' at position 0
//             Capture 0: 'abcabcabc' at position 0
//          Group 1: 'abc' at position 6
//             Capture 0: 'abc' at position 0
//             Capture 1: 'abc' at position 3
//             Capture 2: 'abc' at position 6
//          Group 2: 'ab' at position 6
//             Capture 0: 'ab' at position 0
//             Capture 1: 'ab' at position 3
//             Capture 2: 'ab' at position 6
//          Group 3: 'b' at position 7
//             Capture 0: 'b' at position 1
//             Capture 1: 'b' at position 4
//             Capture 2: 'b' at position 7
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example dosplays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

Im folgenden Beispiel wird der reguläre Ausdruck `(Abc)+` verwendet, um mindestens eine aufeinanderfolgende Ausführung der Zeichenfolge "Abc" in der Zeichenfolge "XYZAbcAbcAbcXYZAbcAb" zu suchen. Das Beispiel veranschaulicht die Verwendung der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft, um mehrere Gruppen erfasster Teilzeichenfolgen zurückzugeben.

```csharp
{
   int counter;
   Match m;
   CaptureCollection cc;
   GroupCollection gc;

   // Look for groupings of "Abc".
   Regex r = new Regex("(Abc)+"); 
   // Define the string to search.
   m = r.Match("XYZAbcAbcAbcXYZAbcAb"); 
   gc = m.Groups;

   // Display the number of groups.
   Console.WriteLine("Captured groups = " + gc.Count.ToString());

   // Loop through each group.
   for (int i=0; i < gc.Count; i++) 
   {
      cc = gc[i].Captures;
      counter = cc.Count;

      // Display the number of captures in this group.
      Console.WriteLine("Captures count = " + counter.ToString());

      // Loop through each capture in the group.
      for (int ii = 0; ii < counter; ii++) 
      {
         // Display the capture and its position.
         Console.WriteLine(cc[ii] + "   Starts at character " + 
              cc[ii].Index);
      }
   }
}
// The example displays the following output:
//       Captured groups = 2
//       Captures count = 1
//       AbcAbcAbc   Starts at character 3
//       Captures count = 3
//       Abc   Starts at character 3
//       Abc   Starts at character 6
//       Abc   Starts at character 9  
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "((a(b))c)+"
      Dim input As STring = "abcabcabc"

      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Match: '{0}' at position {1}", _ 
                           match.Value, match.Index)
         Dim groups As GroupCollection = match.Groups
         For ctr As Integer = 0 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at position {2}", _
                              ctr, groups(ctr).Value, groups(ctr).Index)
            Dim captures As CaptureCollection = groups(ctr).Captures
            For ctr2 As Integer = 0 To captures.Count - 1
               Console.WriteLine("      Capture {0}: '{1}' at position {2}", _
                                 ctr2, captures(ctr2).Value, captures(ctr2).Index)
            Next
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Match: 'abcabcabc' at position 0
'          Group 0: 'abcabcabc' at position 0
'             Capture 0: 'abcabcabc' at position 0
'          Group 1: 'abc' at position 6
'             Capture 0: 'abc' at position 0
'             Capture 1: 'abc' at position 3
'             Capture 2: 'abc' at position 6
'          Group 2: 'ab' at position 6
'             Capture 0: 'ab' at position 0
'             Capture 1: 'ab' at position 3
'             Capture 2: 'ab' at position 6
'          Group 3: 'b' at position 7
'             Capture 0: 'b' at position 1
'             Capture 1: 'b' at position 4
'             Capture 2: 'b' at position 7
```

## <a name="the-individual-capture"></a>Die einzelne Erfassung

Die [Capture](xref:System.Text.RegularExpressions.Capture)-Klasse enthält die Ergebnisse einer einzelnen Teilausdrucksuche. Die [Capture.Value](xref:System.Text.RegularExpressions.Capture.Value)-Eigenschaft enthält den übereinstimmenden Text, und die [Capture.Index](xref:System.Text.RegularExpressions.Capture.Index)-Eigenschaft gibt die nullbasierte Position in der Eingabezeichenfolge an, bei der die übereinstimmende Teilzeichenfolge beginnt. 

Im folgenden Beispiel wird eine Eingabezeichenfolge hinsichtlich der Temperatur ausgewählter Orte analysiert. Ein Komma (",") wird verwendet, um einen Ort und seine Temperatur zu trennen. Ein Semikolon ("";) dient zum Trennen der Daten zu einzelnen Orten. Die gesamte Eingabezeichenfolge stellt eine einzelne Übereinstimmung dar. Im Muster `((\w+(\s\w+)*),(\d+);)+` eines regulären Ausdrucks, mit dem die Zeichenfolge analysiert wird, wird der Ortsname der zweiten Erfassungsgruppe und die Temperatur der vierten Erfassungsgruppe zugewiesen.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;"; 
      string pattern = @"((\w+(\s\w+)*),(\d+);)+";
      Match match = Regex.Match(input, pattern);
      if (match.Success)
      {
         Console.WriteLine("Current temperatures:");
         for (int ctr = 0; ctr < match.Groups[2].Captures.Count; ctr++)
            Console.WriteLine("{0,-20} {1,3}", match.Groups[2].Captures[ctr].Value, 
                              match.Groups[4].Captures[ctr].Value);
      }
   }
}
// The example displays the following output:
//       Current temperatures:
//       Miami                 78
//       Chicago               62
//       New York              67
//       San Francisco         59
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Miami,78;Chicago,62;New York,67;San Francisco,59;Seattle,58;" 
      Dim pattern As String = "((\w+(\s\w+)*),(\d+);)+"
      Dim match As Match = Regex.Match(input, pattern)
      If match.Success Then
         Console.WriteLine("Current temperatures:")
         For ctr As Integer = 0 To match.Groups(2).Captures.Count - 1
            Console.WriteLine("{0,-20} {1,3}", match.Groups(2).Captures(ctr).Value, _
                              match.Groups(4).Captures(ctr).Value)
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Current temperatures:
'       Miami                 78
'       Chicago               62
'       New York              67
'       San Francisco         59
```

Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`(\s\w+)*` | Entsprechung für null oder mehr Vorkommen eines Leerstellenzeichens finden, auf das mindestens ein Wortzeichen folgt. Dieses Muster entspricht Ortsnamen, die aus mehreren Wörtern bestehen. Dies ist die dritte Erfassungsgruppe.
`(\w+(\s\w+)*)` | Entsprechung für mindestens ein Wortzeichen finden, auf das null oder mehr Vorkommen eines Leerstellenzeichens folgen und mindestens ein Wortzeichen. Dies ist die zweite Erfassungsgruppe.
`,` | Entsprechung für ein Komma finden.
`(\d+)` | Entsprechung für mindestens eine Stelle finden. Dies ist die vierte Erfassungsgruppe.
`;` | Entsprechung für ein Semikolon finden.
`((\w+(\s\w+)*),(\d+);)+` | Entsprechung für das Muster eines Worts finden, auf das alle weiteren Wörter folgen, auf die ein Komma, mindestens eine Ziffer und ein Semikolon folgen (mindestens einmal). Dies ist die erste Erfassungsgruppe. 
 
## <a name="see-also"></a>Siehe auch

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


