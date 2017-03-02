---
title: "Gruppierungskonstrukte in regulären Ausdrücken"
description: "Gruppierungskonstrukte in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e0bf3718-e64b-460b-b73d-66678cec6093
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 05fcdadee5d932a53941386f97971c24cc912fd8
ms.lasthandoff: 03/02/2017

---

# <a name="grouping-constructs-in-regular-expressions"></a>Gruppierungskonstrukte in regulären Ausdrücken

Gruppierungskonstrukte grenzen die Teilausdrücke eines regulären Ausdrucks ab und zeichnen die Teilzeichenfolgen einer Eingabezeichenfolge auf. Mit Gruppierungskonstrukten können Sie folgende Schritte ausführen:

* Finden Sie eine Entsprechung für einen Teilausdruck, der in der Eingabezeichenfolge wiederholt wird.

* Wenden Sie einen Quantifizierer auf einen Teilausdruck an, der über mehrere reguläre Ausdruckssprachelemente verfügt. Weitere Informationen zu Quantifizierern finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md).

* Schließen Sie einen Teilausdruck in die Zeichenfolge ein, die von den [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))- und [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methoden zurückgegeben wird.

* Rufen Sie einzelne Teilausdrücke aus der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft ab, und verarbeiten Sie sie getrennt vom entsprechenden Text als Ganzes.

Die folgende Tabelle führt die Gruppierungskonstrukte auf, die von dem .NET-Modul für reguläre Ausdrücke unterstützt werden, und gibt an, ob sie erfassend oder nicht erfassend sind. 

Gruppierungskonstrukt | Erfassend oder nicht erfassend
------------------ | -------------------------
[Übereinstimmende Teilausdrücke](#matched-subexpressions) | Wird erfasst
[Benannte übereinstimmende Teilausdrücke](#named-matched-subexpressions) | Wird erfasst
[Ausgleichsgruppendefinitionen](#balancing-group-definitions) | Wird erfasst
[Nicht erfassende Gruppen](#noncapturing-groups) | Nicht erfassend
[Gruppenoptionen](#group-options) | Nicht erfassend
[Positive Lookaheadassertionen mit einer Breite von null](#zero-width-positive-lookahead-assertions) | Nicht erfassend
[Negative Lookaheadassertionen mit einer Breite von null](#zero-width-negative-lookahead-assertions) | Nicht erfassend
[Positive Lookbehindassertionen mit einer Breite von null](#zero-width-positive-lookbehind-assertions) | Nicht erfassend
[Negative Lookbehindassertionen mit einer Breite von null](#zero-width-negative-lookbehind-assertions) | Nicht erfassend
[Nicht zurückverfolgende Teilausdrücke](#nonbacktracking-subexpressions) | Nicht erfassend

Weitere Informationen zu Gruppen und dem Objektmodell für reguläre Ausdrücke finden Sie unter [Gruppierungskonstrukte und Objekte für reguläre Ausdrücke](#grouping-constructs-and-regular-expression-objects). 

## <a name="matched-subexpressions"></a>Übereinstimmende Teilausdrücke

Das folgende Gruppierungskonstrukt erfasst einen übereinstimmenden Teilausdruck: 

**(**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges gültiges Muster für reguläre Ausdrücke. Erfassungen, die Klammern verwenden, werden automatisch von links nach rechts und mit eins beginnend auf Grundlage der Reihenfolge der öffnenden runden Klammern im regulären Ausdruck aufgezählt. Die Erfassung, die mit 0 gekennzeichnet wird, ist der Text, dem das gesamte Muster für den regulären Ausdruck entspricht.

> [!NOTE]
> Standardmäßig erfasst das Sprachelement „(Teilausdruck)“ den übereinstimmenden Teilausdruck. Wenn der RegexOptions-Parameter einer Methode für den Abgleich von Mustern für reguläre Ausdrücke das RegexOptions.ExplicitCapture-Flag enthält oder wenn die n-Option auf diesen Teilausdruck angewendet wird (siehe den Abschnitt zu Gruppenoptionen weiter unten in diesem Thema), wird der übereinstimmende Teilausdruck jedoch nicht erfasst.
 
Für den Zugriff auf erfasste Gruppen gibt es vier Möglichkeiten:

* Indem das Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mithilfe der Syntax **\**_number_ verwiesen, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.

* Indem das benannte Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mithilfe der Syntax **\k<**_name_**>** verwiesen, wobei *name* der Name einer Erfassungsgruppe ist, oder mit **\k**_<number_**>**, wobei *number* die Ordinalzahl einer Erfassungsgruppe ist. Eine Erfassungsgruppe weist einen Standardnamen auf, der mit der zugehörigen Ordinalzahl identisch ist. Weitere Informationen finden Sie im Abschnitt „Gruppierungskonstrukte und Objekte für reguläre Ausdrücke“ weiter unten in diesem Thema.

* Mit der Ersatzsequenz **$**_number_ in einem [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))- oder [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methodenaufruf, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.

* Programmgesteuert mithilfe des [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekts, das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegeben wird. Der Member auf der Nullposition in der Auflistung stellt die gesamte Übereinstimmung für einen regulären Ausdruck dar. Jeder nachfolgende Member stellt einen übereinstimmenden Teilausdruck dar. Weitere Informationen finden Sie im Abschnitt [Gruppierungskonstrukte und Objekte für reguläre Ausdrücke](#grouping-constructs-and-regular-expression-objects).

Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der doppelte Wörter im Text identifiziert. Die zwei Erfassungsgruppen des Musters eines regulären Ausdrucks stellen die zwei Instanzen des doppelten Worts dar. Die zweite Instanz wird erfasst, um die Anfangsposition in der Eingabezeichenfolge zu melden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w+)\s(\1)";
      string input = "He said that that was the the correct answer.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("Duplicate '{0}' found at positions {1} and {2}.", 
                           match.Groups[1].Value, match.Groups[1].Index, match.Groups[2].Index);
   }
}
// The example displays the following output:
//       Duplicate 'that' found at positions 8 and 13.
//       Duplicate 'the' found at positions 22 and 26.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w+)\s(\1)\W"
      Dim input As String = "He said that that was the the correct answer."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("Duplicate '{0}' found at positions {1} and {2}.", _
                           match.Groups(1).Value, match.Groups(1).Index, match.Groups(2).Index)
      Next
   End Sub
End Module
' The example displays the following output:
'       Duplicate 'that' found at positions 8 and 13.
'       Duplicate 'the' found at positions 22 and 26.
```

Das Muster für den reguläre Ausdruck lautet folgendermaßen:

```
(\w+)\s(\1)\W
```

Die folgende Tabelle zeigt, wie das Muster eines regulären Ausdrucks interpretiert wird. 

Muster | Beschreibung
------- | ----------- 
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`(\1)` | Suchen Sie nach einer Entsprechung für die Zeichenfolge in der ersten erfassten Gruppe. Dies ist die zweite Erfassungsgruppe. Im Beispiel wird sie einer erfassten Gruppe zugewiesen, damit die Anfangsposition des doppelten Worts von der `Match.Index`-Eigenschaft abgerufen werden kann.
`\W` | Finden Sie eine Entsprechung für ein Nichtwortzeichen, einschließlich Leerzeichen und Interpunktion. Dies verhindert, dass für das Muster eines regulären Ausdrucks eine Entsprechung für ein Wort gefunden wird, das mit dem Wort von der zuerst erfassten Gruppe beginnt.
 
## <a name="named-matched-subexpressions"></a>Benannte übereinstimmende Teilausdrücke

Das folgende Gruppierungskonstrukt erfasst einen übereinstimmenden Teilausdruck und ermöglicht den Zugriff nach Name oder Zahl: 

```
(?<name>subexpression)
```

oder:

```
(?'name'subexpression)
```

Hierbei ist *name* ein gültiger Gruppenname, und *subexpression* ist ein beliebiges gültiges Muster für reguläre Ausdrücke. *name* darf keine Interpunktionszeichen enthalten und nicht mit einer Zahl beginnen.

> [!NOTE]
> Wenn der [RegexOptions](xref:System.Text.RegularExpressions.RegexOptions)-Parameter einer Methode für den Abgleich von Mustern für reguläre Ausdrücke das [RegexOptions.ExplicitCapture](xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture)-Flag enthält oder wenn die **n**-Option auf diesen Teilausdruck angewendet wird (siehe den Abschnitt [Gruppenoptionen](#group-options) weiter unten in diesem Thema), besteht die einzige Möglichkeit zur Erfassung eines Teilausdrucks in der expliziten Benennung von Erfassungsgruppen.
 
Sie können wie folgt auf benannte erfasste Gruppen zugreifen:

* Indem das benannte Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mithilfe der Syntax **\k<**_name_**>** verwiesen, wobei *name* der Name des erfassten Teilausdrucks ist. 

* Indem das Rückverweiskonstrukt im regulären Ausdruck verwendet wird. Auf den übereinstimmenden Teilausdruck wird im gleichen regulären Ausdruck mithilfe der Syntax **\**_number_ verwiesen, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist. Benannte übereinstimmende Teilausdrücke werden hintereinander von links nach rechts nach übereinstimmenden Teilausdrücken nummeriert.

* Mit der Ersatzsequenz **${**_name_**}** in einem [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))- oder [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methodenaufruf, wobei *name* der Name des erfassten Teilausdrucks ist.

* Mit der Ersatzsequenz **$**_number_ in einem [Regex.Replace](xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String))- oder [Match.Result](xref:System.Text.RegularExpressions.Match.Result(System.String))-Methodenaufruf, wobei *number* die Ordinalzahl des erfassten Teilausdrucks ist.

* Programmgesteuert mithilfe des [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekts, das von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegeben wird. Der Member auf der Nullposition in der Auflistung stellt die gesamte Übereinstimmung für einen regulären Ausdruck dar. Jeder nachfolgende Member stellt einen übereinstimmenden Teilausdruck dar. Benannte erfasste Gruppen werden in der Auflistung nach nummerierten erfassten Gruppen gespeichert.

* Programmgesteuert durch Bereitstellen des Teilausdrucknamens für den Indexer des [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekts (in C#) oder für seine Item-Eigenschaft (in Visual Basic).

Ein einfaches Muster eines regulären Ausdrucks veranschaulicht, wie auf nummerierte (unbenannte) und benannte Gruppen entweder programmgesteuert oder mit der Sprachsyntax für reguläre Ausdrücke verwiesen werden kann. Der reguläre Ausdruck `((?<One>abc)\d+)?(?<Two>xyz)(.*)` generiert die folgenden Erfassungsgruppen nach Nummer und Name. Die erste Erfassungsgruppe (Nummer 0) bezieht sich stets auf das gesamte Muster.

Nummer | Name | Muster
------ | ---- | ------- 
0 | 0 (Standardname) | `((?<One>abc)\d+)?(?<Two>xyz)(.*)`
1 | 1 (Standardname) | `((?<One>abc)\d+)`
2 | 2 (Standardname) | `(.*)`
3 | Eins | `(?<One>abc)`
4 | Zwei | `(?<Two>xyz)`
 
Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der duplizierte Wörter sowie das Wort, das jedem duplizierten Wort direkt folgt, identifiziert. Das Muster eines regulären Ausdrucks definiert zwei benannte Teilausdrücke: `duplicateWord`, der das doppelte Wort darstellt; und `nextWord`, der das Wort darstellt, das auf das doppelte Wort folgt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?<duplicateWord>\w+)\s\k<duplicateWord>\W(?<nextWord>\w+)";
      string input = "He said that that was the the correct answer.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine("A duplicate '{0}' at position {1} is followed by '{2}'.", 
                           match.Groups["duplicateWord"].Value, match.Groups["duplicateWord"].Index, 
                           match.Groups["nextWord"].Value);

   }
}
// The example displays the following output:
//       A duplicate 'that' at position 8 is followed by 'was'.
//       A duplicate 'the' at position 22 is followed by 'correct'.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?<duplicateWord>\w+)\s\k<duplicateWord>\W(?<nextWord>\w+)"
      Dim input As String = "He said that that was the the correct answer."
      Console.WriteLine(Regex.Matches(input, pattern, RegexOptions.IgnoreCase).Count)
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine("A duplicate '{0}' at position {1} is followed by '{2}'.", _
                           match.Groups("duplicateWord").Value, match.Groups("duplicateWord").Index, _
                           match.Groups("nextWord").Value)
      Next
   End Sub
End Module
' The example displays the following output:
'    A duplicate 'that' at position 8 is followed by 'was'.
'    A duplicate 'the' at position 22 is followed by 'correct'.
```

Das Muster für den reguläre Ausdruck lautet folgendermaßen:

```
(?<duplicateWord>\w+)\s\k<duplicateWord>\W(?<nextWord>\w+)
```

In der folgenden Tabelle wird gezeigt, wie der reguläre Ausdruck interpretiert wird.

Muster | Beschreibung
------- | -----------
`(?<duplicateWord>\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Geben Sie für die Erfassungsgruppe `duplicateWord` als Namen an.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`\k<duplicateWord>` | Suchen Sie nach einer Entsprechung der Zeichenfolge der erfassten Gruppe mit der Bezeichnung `duplicateWord`. 
`\W` | Finden Sie eine Entsprechung für ein Nichtwortzeichen, einschließlich Leerzeichen und Interpunktion. Dies verhindert, dass für das Muster eines regulären Ausdrucks eine Entsprechung für ein Wort gefunden wird, das mit dem Wort von der zuerst erfassten Gruppe beginnt.
`(?<nextWord>\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Geben Sie für die Erfassungsgruppe `nextWord` als Namen an.
 
Beachten Sie, dass der Name einer Gruppe in einem regulären Ausdruck wiederholt werden kann. Beispielsweise ist es möglich, dass mehr als eine Gruppe den Namen `digit` trägt, wie im folgenden Beispiel veranschaulicht wird. Im Fall von doppelten Namen wird der Wert des [Group](xref:System.Text.RegularExpressions.Group)-Objekts durch die letzte erfolgreiche Erfassung in der Eingabezeichenfolge bestimmt. Darüber hinaus wird [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection) mit Informationen über jede Erfassung aufgefüllt, genauso, wie es der Fall wäre, wenn der Gruppenname nicht dupliziert wäre. 

Im folgenden Beispiel umfasst der reguläre Ausdruck `\D+(?<digit>\d+)\D+(?<digit>\d+)?` zwei Vorkommen einer Gruppe namens `digit`. Die erste mit `digit` benannte Gruppe erfasst ein oder mehrere Ziffernzeichen. Die zweite mit `digit` benannte Gruppe erfasst entweder null oder ein Vorkommen von einem oder mehreren Ziffernzeichen. Wie die Ausgabe des Beispiels zeigt, definiert der Wert dieses Texts, wenn die zweite Erfassungsgruppe erfolgreich mit Text übereinstimmt, den Wert des [Group](xref:System.Text.RegularExpressions.Group)-Objekts. Wenn die zweite Erfassungsgruppe nicht der Eingabezeichenfolge entspricht, definiert der Wert der letzten erfolgreichen Übereinstimmung den Wert des [Group](xref:System.Text.RegularExpressions.Group)-Objekts. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      String pattern = @"\D+(?<digit>\d+)\D+(?<digit>\d+)?";
      String[] inputs = { "abc123def456", "abc123def" };
      foreach (var input in inputs) {
         Match m = Regex.Match(input, pattern);
         if (m.Success) {
            Console.WriteLine("Match: {0}", m.Value);
            for (int grpCtr = 1; grpCtr < m.Groups.Count; grpCtr++) {
               Group grp = m.Groups[grpCtr];
               Console.WriteLine("Group {0}: {1}", grpCtr, grp.Value);
               for (int capCtr = 0; capCtr < grp.Captures.Count; capCtr++)
                  Console.WriteLine("   Capture {0}: {1}", capCtr,
                                    grp.Captures[capCtr].Value);
            }
         }
         else {
            Console.WriteLine("The match failed.");
         }
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//       Match: abc123def456
//       Group 1: 456
//          Capture 0: 123
//          Capture 1: 456
//
//       Match: abc123def
//       Group 1: 123
//          Capture 0: 123
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\D+(?<digit>\d+)\D+(?<digit>\d+)?"
      Dim inputs() As String = { "abc123def456", "abc123def" }
      For Each input As String In inputs
         Dim m As Match = Regex.Match(input, pattern)
         If m.Success Then
            Console.WriteLine("Match: {0}", m.Value)
            For grpCtr As Integer = 1 to m.Groups.Count - 1
               Dim grp As Group = m.Groups(grpCtr)
               Console.WriteLine("Group {0}: {1}", grpCtr, grp.Value)
               For capCtr As Integer = 0 To grp.Captures.Count - 1
                  Console.WriteLine("   Capture {0}: {1}", capCtr,
                                    grp.Captures(capCtr).Value)
               Next
            Next
         Else
            Console.WriteLine("The match failed.")
         End If
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'       Match: abc123def456
'       Group 1: 456
'          Capture 0: 123
'          Capture 1: 456
'
'       Match: abc123def
'       Group 1: 123
'          Capture 0: 123
```

In der folgenden Tabelle wird gezeigt, wie der reguläre Ausdruck interpretiert wird.

Muster | Beschreibung
------- | -----------
`\D+` | Übereinstimmung mit einem oder mehreren Nichtdezimal-Ziffernzeichen. 
`(?<digit>\d+)` | Übereinstimmung mit einem oder mehreren Dezimalziffernzeichen. Weisen Sie die Übereinstimmung der Gruppe namens `digit` zu. 
`\D+` | Übereinstimmung mit einem oder mehreren Nichtdezimal-Ziffernzeichen. 
`(?<digit>\d+)?` | Übereinstimmung mit keinem oder einem Vorkommen mindestens eines Dezimalziffernzeichens. Weisen Sie die Übereinstimmung der Gruppe namens `digit` zu.
 
## <a name="balancing-group-definitions"></a>Ausgleichen von Gruppendefinitionen

Eine Ausgleichsgruppendefinition löscht die Definition einer zuvor definierten Gruppe und speichert in der aktuellen Gruppe das Intervall zwischen der zuvor definierten Gruppe und der aktuellen Gruppe. Dieses Gruppierungskonstrukt besitzt das folgende Format: 

```
(?<name1-name2>subexpression)
```

oder:

```
(?'name1-name2' subexpression)
```

Hierbei ist *name1* die aktuelle Gruppe (optional), *name2* eine zuvor definierte Gruppe und *subexpression* ein beliebiges gültiges Muster für reguläre Ausdrücke. Die Ausgleichsgruppendefinition löscht die Definition von *name2* und speichert das Intervall zwischen *name2* und *name1* in *name1*. Wenn keine *name2*-Gruppe definiert ist, wird die Übereinstimmung zurückverfolgt. Da durch Löschen der letzten Definition von *name2* die vorherige Definition von *name2* angezeigt wird, kann mithilfe dieses Konstrukts der Erfassungsstapel für die *name2*-Gruppe als Zähler für die Nachverfolgung von geschachtelten Konstrukten, z.B. Anführungszeichen oder öffnende bzw. schließende Klammern, verwendet werden. 

Die Ausgleichsgruppendefinition verwendet *name2* als Stapel. Das Anfangszeichen jedes geschachtelten Konstrukts wird in die Gruppe sowie in die zugehörige [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Auflistung eingefügt. Wenn das schließende Zeichen abgeglichen wird, wird das entsprechende öffnende Zeichen aus der Gruppe entfernt, und die [Captures](xref:System.Text.RegularExpressions.Group.Captures)-Auflistung wird um eins verringert. Nachdem die öffnenden und schließenden Zeichen aller geschachtelten Konstrukte abgeglichen wurden, ist *name1* leer.

> [!NOTE]
> Nachdem Sie den regulären Ausdruck im folgenden Beispiel geändert haben, sodass er die entsprechenden öffnenden und schließenden Zeichen eines geschachtelten Konstrukts enthält, können Sie diesen zur Behandlung der meisten geschachtelten Konstrukte verwenden, z. B. für mathematische Ausdrücke oder Programmcodezeilen, die mehrere geschachtelte Methodenaufrufe enthalten. 
 
Das folgende Codebeispiel verwendet eine Ausgleichsgruppendefinition, um in einer Eingabezeichenfolge nach öffnenden und schließenden spitzen Klammern (<>) zu suchen. Im Beispiel werden zwei benannte Gruppen, `Open` und `Close`, definiert, die wie ein Stapel verwendet werden, um übereinstimmende Paare von spitzen Klammern nachzuverfolgen. Jede erfasste öffnende spitze Klammer wird in die Erfassungsauflistung der `Open`-Gruppe eingefügt, und jede erfasste schließende spitze Klammer wird in die Erfassungsauflistung der `Close`-Gruppe eingefügt. Die Ausgleichsgruppendefinition stellt sicher, dass es eine entsprechende schließende spitze Klammer für jede öffnende spitze Klammer gibt. Trifft dies nicht zu, wird das abschließende Teilmuster, `(?(Open)(?!))`, nur ausgewertet, wenn die `Open`-Gruppe nicht leer ist (und wenn alle geschachtelten Konstrukte nicht geschlossen wurden). Wenn das endgültige Teilmuster ausgewertet wird, schlägt die Übereinstimmung fehl, da das `(?!)` Teilmuster eine negative Lookaheadassertion mit einer Breite von&0; (null) ist, die immer fehlschlägt. 

```csharp
using System;
using System.Text.RegularExpressions;

class Example
{
   public static void Main() 
   {
      string pattern = "^[^<>]*" +
                       "(" + 
                       "((?'Open'<)[^<>]*)+" +
                       "((?'Close-Open'>)[^<>]*)+" +
                       ")*" +
                       "(?(Open)(?!))$";
      string input = "<abc><mno<xyz>>";

      Match m = Regex.Match(input, pattern);
      if (m.Success == true)
      {
         Console.WriteLine("Input: \"{0}\" \nMatch: \"{1}\"", input, m);
         int grpCtr = 0;
         foreach (Group grp in m.Groups)
         {
            Console.WriteLine("   Group {0}: {1}", grpCtr, grp.Value);
            grpCtr++;
            int capCtr = 0;
            foreach (Capture cap in grp.Captures)
            {            
                Console.WriteLine("      Capture {0}: {1}", capCtr, cap.Value);
                capCtr++;
            }
          }
      }
      else
      {
         Console.WriteLine("Match failed.");
      }   
    }
}
// The example displays the following output:
//    Input: "<abc><mno<xyz>>"
//    Match: "<abc><mno<xyz>>"
//       Group 0: <abc><mno<xyz>>
//          Capture 0: <abc><mno<xyz>>
//       Group 1: <mno<xyz>>
//          Capture 0: <abc>
//          Capture 1: <mno<xyz>>
//       Group 2: <xyz
//          Capture 0: <abc
//          Capture 1: <mno
//          Capture 2: <xyz
//       Group 3: >
//          Capture 0: >
//          Capture 1: >
//          Capture 2: >
//       Group 4:
//       Group 5: mno<xyz>
//          Capture 0: abc
//          Capture 1: xyz
//          Capture 2: mno<xyz>
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main() 
        Dim pattern As String = "^[^<>]*" & _
                                "(" + "((?'Open'<)[^<>]*)+" & _
                                "((?'Close-Open'>)[^<>]*)+" + ")*" & _
                                "(?(Open)(?!))$"
        Dim input As String = "<abc><mno<xyz>>"
        Dim rgx AS New Regex(pattern)'
        Dim m As Match = Regex.Match(input, pattern)
        If m.Success Then
            Console.WriteLine("Input: ""{0}"" " & vbCrLf & "Match: ""{1}""", _
                               input, m)
            Dim grpCtr As Integer = 0
            For Each grp As Group In m.Groups
               Console.WriteLine("   Group {0}: {1}", grpCtr, grp.Value)
               grpCtr += 1
               Dim capCtr As Integer = 0
               For Each cap As Capture In grp.Captures            
                  Console.WriteLine("      Capture {0}: {1}", capCtr, cap.Value)
                  capCtr += 1
               Next
            Next
        Else
            Console.WriteLine("Match failed.")
        End If
    End Sub
End Module  
' The example displays the following output:
'       Input: "<abc><mno<xyz>>"
'       Match: "<abc><mno<xyz>>"
'          Group 0: <abc><mno<xyz>>
'             Capture 0: <abc><mno<xyz>>
'          Group 1: <mno<xyz>>
'             Capture 0: <abc>
'             Capture 1: <mno<xyz>>
'          Group 2: <xyz
'             Capture 0: <abc
'             Capture 1: <mno
'             Capture 2: <xyz
'          Group 3: >
'             Capture 0: >
'             Capture 1: >
'             Capture 2: >
'          Group 4:
'          Group 5: mno<xyz>
'             Capture 0: abc
'             Capture 1: xyz
'             Capture 2: mno<xyz>
```

Das Muster des regulären Ausdrucks lautet:

```
^[^<>]*(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*(?(Open)(?!))$
```

Der reguläre Ausdruck wird wie folgt interpretiert:

Muster | Beschreibung
------- | -----------
`^` | Starten Sie am Beginn der Zeichenfolge.
`[^<>]*` | Finden Sie eine Entsprechung für null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind.
`(?'Open'<)` | Suchen Sie eine Übereinstimmung für ein kleiner als-Zeichen, und weisen Sie es einer Gruppe mit dem Namen `Open` zu.
`[^<>]*` | Finden Sie eine Entsprechung für null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind.
`((?'Open'<)[^<>]*) +` | Finden Sie eine Entsprechung für ein oder mehr Vorkommen einer linken spitzen Klammer, gefolgt von null oder mehr Zeichen, die keine linken oder rechten spitzen Klammern sind. Dies ist die zweite Erfassungsgruppe.
`(?'Close-Open'>)` | Finden Sie eine Entsprechung für eine öffnende spitze Klammer, weisen Sie die Teilzeichenfolge zwischen der `Open`-Gruppe und der aktuellen Gruppe der `Close`-Gruppe zu, und löschen Sie die Definition der `Open`-Gruppe.
`[^<>]*` | Sucht eine Übereinstimmung mit null oder mehr Vorkommen eines Zeichens, das weder eine linke noch eine rechte spitze Klammer ist. 
`((?'Close-Open'>)[^<>]*)+` | Finden Sie eine Entsprechung für ein oder mehr Vorkommen einer rechten spitzen Klammer, gefolgt von einem die oft ausgegebene Befehlszeilen  Zeichen, das weder eine linke noch eine rechte spitze Klammern ist. Wenn die rechte spitze Klammer zugeordnet wird, wird die Teilzeichenfolge zwischen der `Open`-Gruppe und der aktuellen Gruppe der `Close`-Gruppe zugewiesen, und die Definition der `Open`-Gruppe wird gelöscht. Dies ist die dritte Erfassungsgruppe.
`(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*` | Finden Sie eine Entsprechung für null oder mehr Vorkommen des folgenden Musters: ein oder mehr Vorkommen einer linken spitzen Klammer, gefolgt von null oder mehr Zeichen, die keine spitzen Klammern sind, gefolgt von einem oder mehr Vorkommen einer rechten spitzen Klammer, gefolgt von null oder mehr Vorkommen von nicht spitzen Klammern. Löschen Sie beim Abgleichen der schließenden spitzen Klammer die Definition der `Open`-Gruppe, und weisen Sie der `Open`-Gruppe die Teilzeichenfolge zwischen der `Close`-Gruppe und der aktuellen Gruppe zu. Dies ist die erste Erfassungsgruppe.
`(?(Open)(?!))` | Wenn die `Open`-Gruppe vorhanden ist und eine leere Zeichenfolge abgeglichen werden kann, geben Sie die Übereinstimmung auf, erhöhen Sie dabei jedoch nicht die Position des Moduls für den regulären Ausdruch in der Zeichenfolge. Dies ist eine negative Lookaheadassertion mit einer Breite von Null. Da eine leere Zeichenfolge in einer Eingabezeichenfolge immer implizit vorhanden ist, schlägt diese Übereinstimmung immer fehl. Das Fehlschlagen dieser Übereinstimmung weist darauf hin, dass die spitzen Klammern nicht ausgeglichen sind. 
`$` | Entsprechung für das Ende der Eingabezeichenfolge finden.
 
Der abschließende Teilausdruck, `(?(Open)(?!))`, gibt an, ob die Schachtelungskonstrukte in der Eingabezeichenfolge ausgeglichen sind (z. B. ob jeder öffnenden spitzen Klammer eine entsprechende schließende spitze Klammer zugeordnet ist). Dabei wird eine bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe verwendet. Weitere Informationen finden Sie unter [Alternierungskonstrukte in regulären Ausdrücken](alternation.md). Wenn die `Open`-Gruppe definiert ist, versucht das Modul für reguläre Ausdrücke, eine Entsprechung für den `(?!)`-Teilausdruck in der Eingabezeichenfolge zu finden. Die `Open`-Gruppe sollte nur definiert werden, wenn Schachtelungskonstrukte nicht ausgeglichen sind. Daher sollte das in der Eingabezeichenfolge zu findende Muster immer dazu führen, dass die Übereinstimmung fehlschlägt. In diesem Fall ist `(?!)` eine negative Lookaheadassertion mit einer Breite von Null, die immer fehlschlägt, da eine leere Zeichenfolge immer an der nächsten Position in der Eingabezeichenfolge implizit vorhanden ist.

Im Beispiel wertet das Modul für reguläre Ausdrücke die Eingabezeichenfolge „<abc><mno<xyz>>“ wie in der folgenden Tabelle gezeigt aus.

Schritt | Muster | Ergebnis
---- | ------- | ------ 
1 | `^` | Beginnt den Abgleich am Anfang der Eingabezeichenfolge
2 | `[^<>]*` | Sucht vor der öffnenden spitzen Klammer nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen. 
3 | `(((?'Open'<)` | Findet eine Übereinstimmung mit der linken spitzen Klammer in „<abc>“ und weist sie der `Open`-Gruppe zu.
4 | `[^<>]*` | Entspricht "abc".
5 | `)+` | "<abc" ist der Wert der zweiten erfassten Gruppe. Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt das Modul für reguläre Ausdrücke keine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster aus.
6 | `((?'Close-Open'>)` | Findet eine Übereinstimmung mit der rechten spitzen Klammer in „<abc>“, weist „abc“ (die Teilzeichenfolge zwischen der `Open`-Gruppe und der rechten spitzen Klammer) der `Close`-Gruppe zu und löscht den aktuellen Wert („<“) der `Open`-Gruppe, der dann leer bleibt.
7 | `[^<>]*` | Sucht nach der schließenden spitzen Klammer nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.
8 | `)+` | Der Wert der dritten erfassten Gruppe ist ">". Das nächste Zeichen in der Eingabezeichenfolge ist keine schließende spitze Klammer. Deshalb führt das Modul für reguläre Ausdrücke keine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster aus.
9 | `)*` | Der Wert der ersten erfassten Gruppe ist „<abc>“. Das nächste Zeichen in der Eingabezeichenfolge ist eine linke spitze Klammer, weshalb das Modul für reguläre Ausdrücke eine Schleife zurück zum `(((?'Open'<)`-Teilmuster ausführt.
10 | `(((?'Open'<)` | Findet eine Übereinstimmung mit der linken spitzen Klammer in „<mno>“ und weist sie der `Open`-Gruppe zu. Die `Group.Captures`-Auflistung verfügt jetzt über einen einzelnen Wert "<".
11 | `[^<>]*` | Entspricht "mno".
12 | `)+` | "<mno" ist der Wert der zweiten erfassten Gruppe. Das nächste Zeichen in der Eingabezeichenfolge ist eine öffnende spitze Klammer, weshalb das Modul für reguläre Ausdrücke eine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster ausführt.
13 | `(((?'Open'<)` | Findet eine Übereinstimmung mit der linken spitzen Klammer in „<xyz>“ und weist sie der `Open`-Gruppe zu. Die `Group.Captures`-Auflistung der `Open`-Gruppe schließt jetzt zwei Erfassungen ein: die linke spitze Klammer von „<mno>“ und die linke spitze Klammer von „<xyz>“.
14 | `[^<>]*` | Entspricht "xyz".
15 | `)+` | "<xyz" ist der Wert der zweiten erfassten Gruppe. Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt das Modul für reguläre Ausdrücke keine Schleife zurück zum `(?'Open'<)[^<>]*)`-Teilmuster aus.
16 | `((?'Close-Open'>)` | Findet eine Übereinstimmung für die rechte spitze Klammer in „<xyz>“. „xyz“ weist die Teilzeichenfolge zwischen der `Open`-Gruppe und der rechten spitzen Klammer der `Close`-Gruppe zu und löscht den aktuellen Wert der `Open`-Gruppe. Der Wert der vorherigen Erfassung (die linke spitze Klammer in „<mno>“) wird zum aktuellen Wert der `Open`-Gruppe. Die `Captures`-Auflistung der `Open`-Gruppe schließt jetzt eine einzelne Erfassung ein, die linke spitze Klammer von „<xyz>“.
17 | `[^<>]*` | Sucht nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.
18 | `)+` | Der Wert der dritten erfassten Gruppe ist ">". Das nächste Zeichen in der Eingabezeichenfolge ist eine schließende spitze Klammer, weshalb das Modul für reguläre Ausdrücke eine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster ausführt.
19 | `((?'Close-Open'>)` | Findet eine Entsprechung für die abschließende rechte spitze Klammer in „xyz>>“, weist „mno<xyz>“ (die Teilzeichenfolge zwischen der `Open`-Gruppe und der rechten spitzen Klammer) der `Close`-Gruppe zu und löscht den aktuellen Wert der `Open`-Gruppe. Die `Open`-Gruppe ist jetzt leer.
20 | `[^<>]*` | Sucht nach Zeichen, die keine spitzen Klammern sind; findet keine Übereinstimmungen.
21 | `)+` | Der Wert der dritten erfassten Gruppe ist ">". Das nächste Zeichen in der Eingabezeichenfolge ist keine schließende spitze Klammer. Deshalb führt das Modul für reguläre Ausdrücke keine Schleife zurück zum `((?'Close-Open'>)[^<>]*)`-Teilmuster aus.
22 | `)*` | Der Wert der ersten erfassten Gruppe ist „<mno<xyz>>“. Das nächste Zeichen in der Eingabezeichenfolge ist keine öffnende spitze Klammer. Deshalb führt das Modul für reguläre Ausdrücke keine Schleife zurück zum `(((?'Open'<)`-Teilmuster aus.
23 | `(?(Open)(?!))` | Die `Open`-Gruppe ist nicht definiert, sodass keine Übereinstimmung gesucht wird.
24 | `$` | Gleicht das Ende der Eingabezeichenfolge ab.

## <a name="noncapturing-groups"></a>Nicht erfassende Gruppen

Das folgende Gruppierungskonstrukt erfasst nicht die Teilzeichenfolge, die zu einem Teilausdruck passt:

```
**(?**:_subexpression_**)**
```

Hierbei ist *subexpression* ein beliebiges gültiges Muster für reguläre Ausdrücke. Das nicht erfassende Gruppenkonstrukt wird in der Regel verwendet, wenn ein Quantifizierer auf eine Gruppe angewendet wird, die von der Gruppe erfassten Teilzeichenfolgen jedoch nicht von Interesse sind.

>[!NOTE]
> Wenn ein regulärer Ausdruck geschachtelte Gruppierungskonstrukte einschließt, gilt ein äußeres nicht erfassendes Gruppenkonstrukt nicht für die inneren geschachtelten Gruppenkonstrukte. 
 
Im folgenden Beispiel wird ein regulärer Ausdruck veranschaulicht, der nicht erfassende Gruppen einschließt. Beachten Sie, dass die Ausgabe keine erfassten Gruppen einschließt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(?:\b(?:\w+)\W*)+\.";
      string input = "This is a short sentence.";
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: {0}", match.Value);
      for (int ctr = 1; ctr < match.Groups.Count; ctr++)
         Console.WriteLine("   Group {0}: {1}", ctr, match.Groups[ctr].Value);
   }
}
// The example displays the following output:
//       Match: This is a short sentence.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(?:\b(?:\w+)\W*)+\."
      Dim input As String = "This is a short sentence."
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: {0}", match.Value)
      For ctr As Integer = 1 To match.Groups.Count - 1
         Console.WriteLine("   Group {0}: {1}", ctr, match.Groups(ctr).Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       Match: This is a short sentence.
```

Der reguläre Ausdruck `(?:\b(?:\w+)\W*)+\.` stimmt mit einem Satz überein, der durch einen Punkt beendet wird. Da sich der reguläre Ausdruck auf Sätze konzentriert und nicht auf einzelne Wörter, werden Gruppierungskonstrukte ausschließlich als Quantifizierer verwendet. Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(?:\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Weisen Sie einer erfassten Gruppe den entsprechenden Text nicht zu.
`\W*` | Suchen Sie nach einer Übereinstimmung mit null oder mehr Nicht-Wortzeichen.
`(?:\b(?:\w+)\W*)+` | Suchen Sie nach einer Übereinstimmung für das Muster aus einem oder mehreren Wortzeichen, beginnend bei einer Wortgrenze und gefolgt von null oder mehr Nicht-Wortzeichen (ein oder zwei Mal). Weisen Sie einer erfassten Gruppe den entsprechenden Text nicht zu.
`\.` | Entsprechung für einen Punkt finden.
 
## <a name="group-options"></a>Gruppenoptionen

Das folgende Gruppierungskonstrukt wendet die angegebenen Optionen in einem Teilausdruck an oder deaktiviert sie:

**(?imnsx-imnsx:**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges gültiges Muster für reguläre Ausdrücke. Beispielsweise aktiviert `(?i-s:)` die Einstellung, dass Groß-/Kleinschreibung nicht beachtet wird, und deaktiviert den Einzeilenmodus. Weitere Informationen zu den Inlineoptionen, die Sie angeben können, finden Sie unter [Optionen für reguläre Ausdrücke](options.md).

> [!NOTE]
> Sie können Optionen angeben, die für einen vollständigen regulären Ausdruck und nicht für einen Teilausdruck gültig sind. Verwenden Sie dazu einen [System.Text.RegularExpressions.Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktor oder eine statische Methode. Sie können auch Inlineoptionen angeben, die nach einem bestimmten Punkt in einem regulären Ausdruck gelten. Verwenden Sie dazu das `(?imnsx-imnsx)`-Sprachkonstrukt.
 
Das Konstrukt für die Gruppenoptionen ist keine Erfassungsgruppe. Obwohl jeder Teil einer Zeichenfolge, der von *subexpression* erfasst wird, in der Übereinstimmung enthalten ist, ist die Teilzeichenfolge weder in einer erfassten Gruppe enthalten noch wird sie dazu verwendet, das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt aufzufüllen.

Der reguläre Ausdruck `\b(?ix: d \w+)\s ` im folgenden Beispiel verwendet Inlineoptionen in einem Gruppierungskonstrukt, um einen Abgleich ohne Berücksichtigung der Groß-/Kleinschreibung zu aktivieren und zu ermöglichen, dass beim Identifizieren aller Wörter, die mit dem Buchstaben „d“ beginnen, Leerstellen im Muster ignoriert werden. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
 `(?ix: d \w+)` | In diesem Muster wird Übereinstimmung ohne Berücksichtigung von Groß- und Kleinschreibung verwendet, und Leerzeichen werden ignoriert (entspricht dem Buchstaben "d" gefolgt von mindestens einem Wortzeichen). 
`\s` | Entsprechung für ein Leerraumzeichen finden.
 
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

## <a name="zero-width-positive-lookahead-assertions"></a>Positive Lookaheadassertionen mit einer Breite von Null

Das folgende Gruppierungskonstrukt definiert eine positive Lookaheadassertion mit einer Breite von Null:

**(?**=*subexpression*__)__

Hierbei ist *subexpression* ein beliebiges Muster für reguläre Ausdrücke. Damit eine Übereinstimmung erfolgreich ist, muss die Eingabezeichenfolge mit dem Muster für reguläre Ausdrücke in *subexpression* übereinstimmen, obwohl die übereinstimmende Teilzeichenfolge nicht im Übereinstimmungsergebnis enthalten ist. Eine positive Lookaheadassertion mit einer Breite von Null wird nicht zurückverfolgt.

In der Regel befindet sich eine positive Lookaheadassertion mit einer Breite von Null am Ende eines Musters eines regulären Ausdrucks. Damit wird eine Teilzeichenfolge definiert, die am Ende einer Zeichenfolge gefunden werden muss, damit eine Übereinstimmung vorliegt, jedoch nicht in der Übereinstimmung enthalten sein soll. Dies ist auch zum Verhindern einer übermäßigen Rückverfolgung nützlich. Sie können eine Lookaheadassertion mit einer Breite von Null verwenden, um sicherzustellen, dass eine bestimmte Erfassungsgruppe mit Text beginnt, der einer Teilmenge des Musters entspricht, das für diese Erfassungsgruppe definiert ist. Wenn z. B. eine Erfassungsgruppe aufeinander folgenden Wortzeichen entspricht, können Sie mit einer positiven Lookaheadassertion mit einer Breite von Null anfordern, dass das erste Zeichen ein alphabetischer Großbuchstabe ist.

Im folgenden Beispiel wird mithilfe einer positiven Lookaheadassertion mit einer Breite von Null eine Entsprechung für das Wort gesucht, das dem Verb "is" in der Eingabezeichenfolge vorausgeht. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\w+(?=\sis\b)";
      string[] inputs = { "The dog is a Malamute.", 
                          "The island has beautiful birds.", 
                          "The pitch missed home plate.", 
                          "Sunday is a weekend day." };

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success)
            Console.WriteLine("'{0}' precedes 'is'.", match.Value);
         else
            Console.WriteLine("'{0}' does not match the pattern.", input); 
      }
   }
}
// The example displays the following output:
//    'dog' precedes 'is'.
//    'The island has beautiful birds.' does not match the pattern.
//    'The pitch missed home plate.' does not match the pattern.
//    'Sunday' precedes 'is'.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\w+(?=\sis\b)"
      Dim inputs() As String = { "The dog is a Malamute.", _
                                 "The island has beautiful birds.", _
                                 "The pitch missed home plate.", _
                                 "Sunday is a weekend day." }

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then
            Console.WriteLine("'{0}' precedes 'is'.", match.Value)
         Else
            Console.WriteLine("'{0}' does not match the pattern.", input) 
         End If     
      Next
   End Sub
End Module
' The example displays the following output:
'       'dog' precedes 'is'.
'       'The island has beautiful birds.' does not match the pattern.
'       'The pitch missed home plate.' does not match the pattern.
'       'Sunday' precedes 'is'.
```

Der reguläre Ausdruck „\b\w+(?=\sis\b)“ wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`(?=\sis\b)` | Bestimmen Sie, ob den Wortzeichen ein Leerstellenzeichen und die Zeichenfolge "is" folgt, die bei einer Wortgrenze endet. Trifft dies zu, ist die Übereinstimmung erfolgreich.

## <a name="zero-width-negative-lookahead-assertions"></a>Negative Lookaheadassertionen mit einer Breite von Null

Das folgende Gruppierungskonstrukt definiert eine negative Lookaheadassertion mit einer Breite von Null:

**(?!**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges Muster für reguläre Ausdrücke. Damit die Übereinstimmung erfolgreich ist, darf die Eingabezeichenfolge nicht mit dem Muster für reguläre Ausdrücke in *subexpression* übereinstimmen, obwohl die übereinstimmende Zeichenfolge nicht im Übereinstimmungsergebnis enthalten ist. 

Eine negative Lookaheadassertion mit einer Breite von Null wird in der Regel entweder am Anfang oder dem Ende eines regulären Ausdrucks verwendet. Am Anfang eines regulären Ausdrucks kann ein bestimmtes Muster definiert werden, das nicht zugewiesen werden soll, wenn der Anfang des regulären Ausdrucks ein ähnliches aber allgemeineres Muster zur Übereinstimmung definiert. In diesem Fall wird dies häufig verwendet, um das Zurückverfolgen einzuschränken. Am Ende eines regulären Ausdrucks kann ein Teilausdruck definiert werden, der am Ende einer Übereinstimmung nicht auftreten darf. 

Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der am Anfang des regulären Ausdrucks eine Lookaheadassertion mit einer Breite von Null verwendet, um eine Entsprechung für Wörter zu finden, die nicht mit "un" beginnen. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?!un)\w+\b";
      string input = "unite one unethical ethics use untie ultimate";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       one
//       ethics
//       use
//       ultimate
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?!un)\w+\b"
      Dim input As String = "unite one unethical ethics use untie ultimate"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       one
'       ethics
'       use
'       ultimate
```

Der reguläre Ausdruck „\b(?!un)\w+\b“ wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(?!un)` | Es wird bestimmt, ob die nächsten zwei Zeichen "un" sind. Trifft dies nicht zu, ist eine Übereinstimmung möglich.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Im folgenden Beispiel wird ein regulärer Ausdruck definiert, der am Ende eine Lookaheadassertion mit einer Breite von Null verwendet, um eine Entsprechung für Wörter zu finden, die nicht mit einem Interpunktionszeichen enden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\w+\b(?!\p{P})";
      string input = "Disconnected, disjointed thoughts in a sentence fragment.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       disjointed
//       thoughts
//       in
//       a
//       sentence
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\w+\b(?!\p{P})"
      Dim input As String = "Disconnected, disjointed thoughts in a sentence fragment."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next   
   End Sub
End Module
' The example displays the following output:
'       disjointed
'       thoughts
'       in
'       a
'       sentence
```

Der reguläre Ausdruck `\b\w+\b(?!\p{P})` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`\b` | Der Vergleich endet an einer Wortgrenze.
`\p{P})` | Wenn das nächste Zeichen kein Interpunktionszeichen (z. B. ein Punkt oder ein Komma) ist, ist die Übereinstimmung erfolgreich.
 
## <a name="zero-width-positive-lookbehind-assertions"></a>Positive Lookbehindassertionen mit einer Breite von Null

Das folgende Gruppierungskonstrukt definiert eine positive Lookbehindassertion mit einer Breite von Null:

**(?<=**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges Muster für reguläre Ausdrücke. Damit eine Übereinstimmung erfolgreich ist, muss die *subexpression*-Zeichenfolge in der Eingabezeichenfolge links von der aktuellen Position auftreten, obwohl der Teilausdruck nicht im Übereinstimmungsergebnis enthalten ist. Eine positive Lookbehindassertion mit einer Breite von Null wird nicht zurückverfolgt.

Positive Lookbehindassertionen mit einer Breite von Null werden in der Regel entweder am Anfang oder am Ende von regulären Ausdrücken verwendet. Das Muster, das sie definieren, ist eine Vorbedingung für eine Übereinstimmung, obwohl es kein Teil des Übereinstimmungsergebnisses ist. 

Im folgenden Beispiel wird eine Entsprechung für die letzten zwei Ziffern des Jahres für das&21;. Jahrhundert (das heißt, es ist erforderlich, dass die Ziffern "20" der entsprechenden Zeichenfolge vorausgehen) gefunden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "2010 1999 1861 2140 2009";
      string pattern = @"(?<=\b20)\d{2}\b";

      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       10
//       09
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "2010 1999 1861 2140 2009"
      Dim pattern As String = "(?<=\b20)\d{2}\b"

      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next      
   End Sub
End Module
' The example displays the following output:
'       10
'       09
```

Das Muster für reguläre Ausdrücke `(?<=\b20)\d{2}\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | -----------
`\d{2}` | Entsprechung für zwei Dezimalstellen finden.
`{?<=\b20)` | Die Übereinstimmung wird fortgesetzt, wenn den zwei Dezimalstellen die Dezimalstellen "20" bei einer Wortgrenze vorangestellt sind.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Positive Lookbehindassertions mit einer Breite von Null werden auch verwendet, um das Zurückverfolgen einzuschränken, wenn die letzten Zeichen in einer Erfassungsgruppe eine Teilmenge der Zeichen sein müssen, die dem Muster eines regulären Ausdrucks dieser Gruppe entsprechen. Wenn beispielsweise eine Gruppe alle aufeinander folgenden Wortzeichen erfasst, können Sie mit einer positiven Lookaheadassertion mit einer Breite von Null anfordern, dass das letzte Zeichen alphabetisch ist. 

## <a name="zero-width-negative-lookbehind-assertions"></a>Negative Lookbehindassertionen mit einer Breite von Null

Das folgende Gruppierungskonstrukt definiert eine negative Lookbehindassertion mit einer Breite von Null:

**(?<!**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges Muster für reguläre Ausdrücke. Damit eine Übereinstimmung erfolgreich ist, darf die *subexpression*-Zeichenfolge nicht in der Eingabezeichenfolge links von der aktuellen Position auftreten. Jede Teilzeichenfolge, die nicht mit dem Teilausdruck übereinstimmt, ist nicht im Übereinstimmungsergebnis enthalten.

Negative Lookbehindassertionen mit einer Breite von Null werden in der Regel entweder am Anfang oder am Ende von regulären Ausdrücken verwendet. Das Muster, das sie definieren, schließt eine Übereinstimmung in der darauf folgenden Zeichenfolge aus. Sie werden auch verwendet, um die Rückverfolgung einzuschränken, wenn die letzten Zeichen in einer erfassten Gruppe keine Zeichen sein dürfen, die dem Muster eines regulären Ausdrucks dieser Gruppe entsprechen. Wenn beispielsweise eine Gruppe alle aufeinander folgenden Wortzeichen erfasst, können Sie mit einer positiven Lookaheadassertion mit einer Breite von Null anfordern, dass das letzte Zeichen kein Unterstrich (_) ist.

Im folgenden Beispiel wird eine Entsprechung für das Datum eines die oft ausgegebene Befehlszeilen  Wochentags gesucht, der nicht auf das Wochenende (das heißt weder Samstag noch Sonntag) fällt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] dates = { "Monday February 1, 2010", 
                         "Wednesday February 3, 2010", 
                         "Saturday February 6, 2010", 
                         "Sunday February 7, 2010", 
                         "Monday, February 8, 2010" };
      string pattern = @"(?<!(Saturday|Sunday) )\b\w+ \d{1,2}, \d{4}\b";

      foreach (string dateValue in dates)
      {
         Match match = Regex.Match(dateValue, pattern);
         if (match.Success)
            Console.WriteLine(match.Value);
      }      
   }
}
// The example displays the following output:
//       February 1, 2010
//       February 3, 2010
//       February 8, 2010
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim dates() As String = { "Monday February 1, 2010", _
                                "Wednesday February 3, 2010", _
                                "Saturday February 6, 2010", _
                                "Sunday February 7, 2010", _
                                "Monday, February 8, 2010" }
      Dim pattern As String = "(?<!(Saturday|Sunday) )\b\w+ \d{1,2}, \d{4}\b"

      For Each dateValue As String In dates
         Dim match As Match = Regex.Match(dateValue, pattern)
         If match.Success Then
            Console.WriteLine(match.Value)
         End If   
      Next      
   End Sub
End Module
' The example displays the following output:
'       February 1, 2010
'       February 3, 2010
'       February 8, 2010
```

Das Muster für reguläre Ausdrücke `(?<!(Saturday|Sunday) )\b\w+ \d{1,2}, \d{4}\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`\w+` | Suchen Sie nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von einem Leerzeichen.
`\d{1,2},` | Finden Sie eine Entsprechung für entweder eine oder zwei Dezimalstellen, gefolgt von einem Leerstellenzeichen und einem Komma.
`\d{4}\b` | Finden Sie eine Entsprechung für vier Dezimalstellen, und beenden Sie die Übereinstimmung an einer Wortgrenze.
`(?<!(Samstag|Sonntag) )` | Wenn der Übereinstimmung etwas anderes als die Zeichenfolgen "Samstag" oder "Sonntag" (gefolgt von einem Leerzeichen) vorangestellt wird, ist die Übereinstimmung erfolgreich.

## <a name="nonbacktracking-subexpressions"></a>Nicht zurückverfolgende Teilausdrücke

Das folgende Gruppierungskonstrukt stellt einen nicht zurückverfolgenden Teilausdruck (auch bekannt als "gieriger" Teilausdruck) dar:

**(?>**_subexpression_**)**

Hierbei ist *subexpression* ein beliebiges Muster für reguläre Ausdrücke.

Wenn ein regulärer Ausdruck ein optionales oder alternatives übereinstimmendes Muster einschließt und eine Übereinstimmung nicht erfolgreich ist, kann sich das Modul für reguläre Ausdrücke in mehrere Richtungen branchen, um eine Entsprechung zwischen einer Eingabezeichenfolge und einem Muster zu finden. Wenn eine Übereinstimmung nach der ersten Verzweigung nicht gefunden wird, kann das Modul für reguläre Ausdrücke den Punkt der ersten Übereinstimmung sichern bzw. den Punkt zurückverfolgen und die Übereinstimmung mithilfe der zweiten Verzweigung durchführen. Dieser Prozess kann fortgesetzt werden, bis alle Branches versucht wurden.

Das Sprachkonstrukt **(?>**_subexpression_**)** deaktiviert die Rückverfolgung. Das Modul für reguläre Ausdrücke stimmt mit so vielen Zeichen in der Eingabezeichenfolge überein wie möglich. Wenn keine weitere Übereinstimmung möglich ist, findet keine Rückverfolgung statt, um alternative Musterübereinstimmungen zu versuchen. (Das heißt, der Teilausdruck sucht nur Entsprechungen für Zeichenfolgen, zu denen der Teilausdruck allein passen würde. Er versucht nicht, eine Entsprechung für eine Zeichenfolge auf Grundlage des Teilausdrucks und beliebige folgende Teilausdrücke zu finden.) 

Diese Option wird empfohlen, wenn Sie wissen, dass eine Rückverfolgung nicht erfolgreich ist. Indem verhindert wird, dass vom Modul für reguläre Ausdrücke unnötige Suchläufe durchgeführt werden, wird die Leistung verbessert. 

Im folgenden Beispiel wird veranschaulicht, wie ein nicht zurückverfolgender Teilausdruck die Ergebnisse einer Musterübereinstimmung ändert. Der rückverfolgende reguläre Ausdruck findet erfolgreich eine Entsprechung für eine Reihe von Zeichen, die von einem weiteren Vorkommen des gleichen Zeichens bei einer Wortgrenze gefolgt wird. Beim regulären Ausdruck ohne Rückverfolgung ist dies nicht der Fall. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "cccd.", "aaad", "aaaa" };
      string back = @"(\w)\1+.\b";
      string noback = @"(?>(\w)\1+).\b";

      foreach (string input in inputs)
      {
         Match match1 = Regex.Match(input, back);
         Match match2 = Regex.Match(input, noback);
         Console.WriteLine("{0}: ", input);

         Console.Write("   Backtracking : ");
         if (match1.Success)
            Console.WriteLine(match1.Value);
         else
            Console.WriteLine("No match");

         Console.Write("   Nonbacktracking: ");
         if (match2.Success)
            Console.WriteLine(match2.Value);
         else
            Console.WriteLine("No match");
      }
   }
}
// The example displays the following output:
//    cccd.:
//       Backtracking : cccd
//       Nonbacktracking: cccd
//    aaad:
//       Backtracking : aaad
//       Nonbacktracking: aaad
//    aaaa:
//       Backtracking : aaaa
//       Nonbacktracking: No match
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "cccd.", "aaad", "aaaa" }
      Dim back As String = "(\w)\1+.\b"
      Dim noback As String = "(?>(\w)\1+).\b"

      For Each input As String In inputs
         Dim match1 As Match = Regex.Match(input, back)
         Dim match2 As Match = Regex.Match(input, noback)
         Console.WriteLine("{0}: ", input)

         Console.Write("   Backtracking : ")
         If match1.Success Then
            Console.WriteLine(match1.Value)
         Else
            Console.WriteLine("No match")
         End If

         Console.Write("   Nonbacktracking: ")
         If match2.Success Then
            Console.WriteLine(match2.Value)
         Else
            Console.WriteLine("No match")
         End If
      Next
   End Sub
End Module
' The example displays the following output:
'    cccd.:
'       Backtracking : cccd
'       Nonbacktracking: cccd
'    aaad:
'       Backtracking : aaad
'       Nonbacktracking: aaad
'    aaaa:
'       Backtracking : aaaa
'       Nonbacktracking: No match
```

Der nicht zurückverfolgende reguläre Ausdruck `(?>(\w)\1+).\b` wird entsprechend der folgenden Tabelle definiert.

Muster | Beschreibung
------- | -----------
`(\w)` | Finden Sie eine Entsprechung für ein einzelnes Wortzeichen, und weisen Sie es der ersten Erfassungsgruppe zu.
`\1+` | Finden Sie mindestens eine Entsprechung für die erste erfasste Teilzeichenfolge.
`.` | Finden Sie eine Entsprechung für ein beliebiges Zeichen.
`\b` | Beendet den Vergleich an einer Wortgrenze.
`(?>(\w)\1+)` | Finden Sie eine Entsprechung für ein oder mehrere Vorkommen eines duplizierten Wortzeichens, führen Sie jedoch keine Rückverfolgung aus, um für das letzte Zeichen bei einer Wortgrenze eine Entsprechung zu finden.
 
## <a name="grouping-constructs-and-regular-expression-objects"></a>Gruppieren von Konstrukten und Objekten für reguläre Ausdrücke

Teilzeichenfolgen, die von einer Gruppe zur Erfassung von regulären Ausdrücken abgeglichen werden, werden durch [System.Text.RegularExpressions.Group](xref:System.Text.RegularExpressions.Group)-Objekte dargestellt, die aus dem von der [Match.Groups](xref:System.Text.RegularExpressions.Match.Groups)-Eigenschaft zurückgegebenen [System.Text.RegularExpressions.GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt abgerufen werden können. Das [GroupCollection](xref:System.Text.RegularExpressions.GroupCollection)-Objekt wird folgendermaßen aufgefüllt:

* Das erste [Group](xref:System.Text.RegularExpressions.Group)-Objekt in der Auflistung (das Objekt bei Index&0;) stellt die gesamte Übereinstimmung dar.

* Der nächste Satz von [Group](xref:System.Text.RegularExpressions.Group)-Objekten stellt unbenannte (nummerierte) Erfassungsgruppen dar. Sie werden in der Reihenfolge angezeigt, in der sie im regulären Ausdruck definiert sind (von links nach rechts). Die Indexwerte dieser Gruppen reichen von 1 bis zur Anzahl unbenannter Erfassungsgruppen in der Auflistung. (Der Index einer bestimmten Gruppe entspricht seinem nummerierten Rückverweis. Weitere Informationen zu Rückverweisen finden Sie unter [Rückverweiskonstrukte in regulären Ausdrücken](backreference.md).

* Der letzte Satz von [Group](xref:System.Text.RegularExpressions.Group)-Objekten stellt benannte Erfassungsgruppen dar. Sie werden in der Reihenfolge angezeigt, in der sie im regulären Ausdruck definiert sind (von links nach rechts). Der Indexwert der zuerst benannten Erfassungsgruppe ist um eins größer als der Index der letzten unbenannten Erfassungsgruppe. Wenn es keine unbenannten Erfassungsgruppen im regulären Ausdruck gibt, ist der Indexwert der zuerst benannten Erfassungsgruppe gleich eins. 


Wenn Sie einen Quantifizierer auf eine Erfassungsgruppe anwenden, reflektieren die entsprechenden [Capture.Value](xref:System.Text.RegularExpressions.Capture.Value)-, [Capture.Index](xref:System.Text.RegularExpressions.Capture.Index)- und [Capture.Length](xref:System.Text.RegularExpressions.Capture.Length)-Eigenschaften des [Group](xref:System.Text.RegularExpressions.Group)-Objekts die letzte Teilzeichenfolge, die von einer Erfassungsgruppe erfasst wird. Sie können einen vollständigen Satz von Teilzeichenfolgen abrufen, die von Gruppen erfasst werden, die Quantifizierer aus dem von der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft zurückgegebenen [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt besitzen.

Das folgende Beispiel verdeutlicht die Beziehung zwischen den [Group](xref:System.Text.RegularExpressions.Group)- und [Capture](xref:System.Text.RegularExpressions.Capture)-Objekten. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\b(\w+)\W+)+";
      string input = "This is a short sentence.";
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}'", match.Value);
      for (int ctr = 1; ctr < match.Groups.Count; ctr++)
      {
         Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups[ctr].Value);
         int capCtr = 0;
         foreach (Capture capture in match.Groups[ctr].Captures)
         {
            Console.WriteLine("      Capture {0}: '{1}'", capCtr, capture.Value);
            capCtr++;
         }
      }
   }
}
// The example displays the following output:
//       Match: 'This is a short sentence. '
//          Group 1: 'sentence.'
//             Capture 0: 'This '
//             Capture 1: 'is '
//             Capture 2: 'a '
//             Capture 3: 'short '
//             Capture 4: 'sentence.'
//          Group 2: 'sentence'
//             Capture 0: 'This'
//             Capture 1: 'is'
//             Capture 2: 'a'
//             Capture 3: 'short'
//             Capture 4: 'sentence'
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\b(\w+)\W+)+"
      Dim input As String = "This is a short sentence."
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}'", match.Value)
      For ctr As Integer = 1 To match.Groups.Count - 1
         Console.WriteLine("   Group {0}: '{1}'", ctr, match.Groups(ctr).Value)
         Dim capCtr As Integer = 0
         For Each capture As Capture In match.Groups(ctr).Captures
            Console.WriteLine("      Capture {0}: '{1}'", capCtr, capture.Value)
            capCtr += 1
         Next
      Next
   End Sub
End Module
' The example displays the following output:
'       Match: 'This is a short sentence.'
'          Group 1: 'sentence.'
'             Capture 0: 'This '
'             Capture 1: 'is '
'             Capture 2: 'a '
'             Capture 3: 'short '
'             Capture 4: 'sentence.'
'          Group 2: 'sentence'
'             Capture 0: 'This'
'             Capture 1: 'is'
'             Capture 2: 'a'
'             Capture 3: 'short'
'             Capture 4: 'sentence'
```

Das Muster eines regulären Ausdrucks `\b(\w+)\W+)+` extrahiert einzelne Wörter aus einer Zeichenfolge. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen. Zusammen bilden diese Zeichen ein Wort. Dies ist die zweite Erfassungsgruppe.
`\W+` | Entsprechung für mindestens ein Nicht-Wortzeichen finden.
`(\w+)\W+)+` | Suchen Sie nach einer Übereinstimmung für das Muster aus einem oder mehreren Wortzeichen, gefolgt von einem oder mehreren Nicht-Wortzeichen (ein oder zwei Mal). Dies ist die erste Erfassungsgruppe.
 
Die erste Erfassungsgruppe stimmt mit jedem Wort des Satzes überein. Die zweite Erfassungsgruppe vergleicht jedes Wort zusammen mit der Interpunktion und den Leerstellen, die auf das Wort folgen. Das [Group](xref:System.Text.RegularExpressions.Group)-Objekt, dessen Index 2 ist, stellt Informationen zu dem Text bereit, der durch die zweite Erfassungsgruppe abgeglichen wird. Der vollständige Satz von Wörtern, die von der Erfassungsgruppe erfasst wurden, ist in dem [CaptureCollection](xref:System.Text.RegularExpressions.CaptureCollection)-Objekt verfügbar, das von der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Eigenschaft zurückgegeben wurde.

## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)

[Backtracking in regulären Ausdrücken](backtracking.md)

