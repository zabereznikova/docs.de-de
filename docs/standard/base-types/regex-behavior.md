---
title: "Einzelheiten zum Verhalten regulärer Ausdrücke"
description: "Einzelheiten zum Verhalten regulärer Ausdrücke"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6f11047f-45a4-4caf-a259-18abe08cc0d2
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 5656cabb708dcfc311ac7a709446003951b97aa6
ms.lasthandoff: 03/02/2017

---

# <a name="details-of-regular-expression-behavior"></a>Einzelheiten zum Verhalten regulärer Ausdrücke


Das .NET-Modul für reguläre Ausdrücke ist ein zurückverfolgendes Modul zum Abgleich regulärer Ausdrücke, das ein herkömmliches NFA-Modul (Nondeterministic Finite Automaton) beinhaltet, wie es beispielsweise auch von Perl, Python, Emacs und Tcl verwendet wird. Dadurch unterscheidet es sich von schnelleren, aber vom Umfang her beschränkten DFA-Modulen (Deterministic Finite Automaton), die reine reguläre Ausdrücke verwenden. Diese werden z.B. in awk, egrep oder lex verwendet. Außerdem unterscheidet es sich dadurch von standardisierten, aber langsameren POSIX-NFAs. Im folgende Abschnitt werden die drei Typen von Modulen für reguläre Ausdrücke beschrieben, und es wird erklärt, warum reguläre Ausdrücke in .NET mit einem herkömmlichen NFA-Modul implementiert werden.

## <a name="benefits-of-the-nfa-engine"></a>Vorteile des NFA-Moduls

Wenn DFA-Module Mustervergleiche durchführen, wird die Verarbeitungsreihenfolge durch die Eingabezeichenfolge gesteuert. Das Modul beginnt am Anfang der Eingabezeichenfolge und geht sequenziell vor, um zu bestimmen, ob das nächste Zeichen mit dem Muster für reguläre Ausdrücke übereinstimmt. So wird garantiert die längstmögliche Zeichenfolge abgeglichen. Da dasselbe Zeichen niemals zweimal getestet wird, unterstützen DFA-Module keine Rückverfolgung. Da ein DFA-Modul nur einen endlichen Zustand enthält, kann damit kein Muster mit Rückverweisen abgeglichen werden, und weil es keine explizite Erweiterung erstellt, kann es keine Teilausdrücke erfassen.

Im Gegensatz zu DFA-Modulen wird beim Musterabgleich durch herkömmliche NFA-Module die Verarbeitungsreihenfolge durch das Muster für reguläre Ausdrücke gesteuert. Während der Verarbeitung eines bestimmten Sprachelements verwendet das Modul den gierigen Abgleich, das heißt, es gleicht so viel wie irgend möglich von der Eingabezeichenfolge ab. Es speichert jedoch auch seinen Zustand, nachdem ein Teilausdruck erfolgreich abgeglichen wurde. Wenn keine Übereinstimmung gefunden wurde, kann das Modul in einen gespeicherten Zustand zurückkehren, um weitere Abgleiche auszuführen. Dieser Prozess, bei dem ein erfolgreicher Teilausdrucksabgleich verlassen wird, um spätere Sprachelemente im regulären Ausdruck ebenfalls finden zu können, wird als Rückverfolgung oder Backtracking bezeichnet. NFA-Module verwenden die Rückverfolgung, um alle möglichen Erweiterungen eines regulären Ausdrucks in einer bestimmten Reihenfolge zu testen und die erste Übereinstimmung zu akzeptieren. Da ein herkömmliches NFA-Modul für einen erfolgreichen Abgleich eine spezielle Erweiterung des regulären Ausdrucks erstellt, können Übereinstimmungen mit Teilausdrücken erfasst und Übereinstimmungen mit Rückverweisen gefunden werden. Allerdings kann ein herkömmliches NFA aufgrund der Rückverfolgung den gleichen Zustand über unterschiedliche Pfade mehrmals erreichen. Das Resultat ist im ungünstigsten Fall ein exponentiell verlangsamtes Laufzeitverhalten. Da von einem herkömmlichen NFA-Modul die erste Übereinstimmung akzeptiert wird, bleiben weitere (möglicherweise längere) Übereinstimmungen unentdeckt.

POSIX-NFA-Module arbeiten wie herkömmliche NFA-Module, jedoch mit einem Unterschied: Die Rückverfolgung wird so lange fortgesetzt, bis gewährleistet ist, dass die längstmögliche Übereinstimmung gefunden wurde. Aus diesem Grund ist ein POSIX-NFA-Modul langsamer als ein herkömmliches NFA-Modul. Außerdem ist es bei Verwendung eines POSIX-NFA-Moduls nicht möglich, durch eine Änderung der Reihenfolge bei der Rückverfolgungssuche einer kürzeren Übereinstimmung Vorrang vor einer längeren zu geben. 

Programmierer bevorzugen meist herkömmliche NFA-Module, da sie eine umfassendere Kontrolle des Zeichenfolgenabgleichs bieten als DFA- oder POSIX-NFA-Module. Obwohl sie im ungünstigsten Fall langsam sind, kann durch die Verwendung von Suchmustern, die Mehrdeutigkeiten vermeiden und die Rückverfolgung einschränken, ein lineares oder polynomisches Laufzeitverhalten erreicht werden. Anders ausgedrückt werden bei NFA-Modulen zwar Kompromisse bei der Leistung zugunsten von Funktionalität und Flexibilität eingegangen, doch bieten sie meist eine gute bis akzeptable Leistung, wenn ein regulärer Ausdruck gut geschrieben wurde und Fälle vermieden werden, in denen die Rückverfolgung die Leistung exponentiell beeinträchtigt.

> [!NOTE]
> Weitere Informationen über die durch eine übermäßige Rückverfolgung verursachten Leistungseinbußen sowie über Methoden, einen regulären Ausdruck zur Umgehung dieses Problems zu erstellen, finden Sie unter [Rückverfolgung in regulären Ausdrücken](backtracking.md).
 
## <a name="net-framework-engine-capabilities"></a>Funktionen des .NET Framework-Moduls

Um die Vorteile eines herkömmlichen NFA-Moduls voll ausschöpfen zu können, enthält das .NET-Modul für reguläre Ausdrücke einen vollständigen Satz von Konstrukten, mit deren Hilfe Programmierer das Rückverfolgungsmodul steuern können. Diese Konstrukte können dazu verwendet werden, Übereinstimmungen schneller zu finden oder spezielle Erweiterungen eines regulären Ausdrucks anderen vorzuziehen.

Weitere Funktionen des .NET-Moduls für reguläre Ausdrücke: 

### <a name="lazy-quantifiers"></a>Träge Quantifizierer

Träge Quantifizierer: **??**, __*?__, **+?**, **{**_n_**,**_m_**}?**. Diese Konstrukte veranlassen das Rückverfolgungsmodul, zuerst die kleinste Anzahl von Wiederholungen zu durchsuchen. Im Gegensatz dazu wird bei „gierigen“ Quantifizierern die maximale Anzahl an Wiederholungen zuerst berücksichtigt. Das folgende Beispiel veranschaulicht die Unterschiede zwischen beiden. Mit einem regulären Ausdruck wird nach einem Satz gesucht, der auf eine Zahl endet, und zum Erfassen dieser Zahl ist eine Erfassungsgruppe vorgesehen. Der reguläre Ausdruck `.+(\d+)\.` schließt den gierigen Quantifizierer `.+` ein, der bewirkt, dass das Modul für reguläre Ausdrücke nur die letzte Ziffer der Zahl erfasst. Im Gegensatz dazu schließt der reguläre Ausdruck `.+?(\d+)\.` den trägen Quantifizierer `.+?` ein, der bewirkt, dass das Modul für reguläre Ausdrücke die gesamte Zahl erfasst.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string lazyPattern = @".+?(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
       // Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", lazyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (greedy): 5
//       Number at end of sentence (lazy): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim lazyPattern As String = ".+?(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (greedy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match using lazy quantifier .+?.
      match = Regex.Match(input, lazyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (lazy): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", lazyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (greedy): 5
'       Number at end of sentence (lazy): 107325
```

Die gierigen und trägen Versionen dieses regulären Ausdrucks werden der folgenden Tabelle entsprechend definiert.

Muster | Beschreibung
------- | -----------
`.+` (gieriger Quantifizierer) | Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens. Dadurch sucht das Modul für reguläre Ausdrücke nach einer Übereinstimmung mit der gesamten Zeichenfolge und führt dann bei Bedarf die Rückverfolgung aus, um im Rest des Musters eine Übereinstimmung zu finden.
`.+?` (träger Quantifizierer) | Sucht nach mindestens einem Vorkommen eines beliebigen Zeichens, jedoch so wenigen wie möglich.
`(\d+)` | Sucht nach mindestens einem numerischen Zeichen und weist dieses der ersten Erfassungsgruppe zu.
`\.` | Entsprechung für einen Punkt finden.
 
Weitere Informationen zu trägen Quantifizierern finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md).

### <a name="positive-lookahead"></a>Positives Lookahead

Positives Lookahead: **(?**=_teilausdruck_**)**. Diese Funktion ermöglicht es dem Rückverfolgungsmodul, nach dem Finden eines Teilausdrucks zu derselben Textstelle zurückzukehren. Um einen Text vollständig zu durchsuchen, empfiehlt es sich, unterschiedliche Muster von derselben Startposition aus anzuwenden. Zudem kann das Modul überprüfen, ob eine Teilzeichenfolge am Ende der Übereinstimmung vorhanden ist, ohne dass die Teilzeichenfolge im übereinstimmenden Text enthalten ist. Im folgenden Beispiel werden die Wörter in einem Satz, denen keine Interpunktionszeichen folgen, mithilfe eines positiven Lookaheads extrahiert.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b[A-Z]+\b(?=\P{P})";
      string input = "If so, what comes next?";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       If
//       what
//       comes
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b[A-Z]+\b(?=\P{P})"
      Dim input As String = "If so, what comes next?"
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next   
   End Sub
End Module
' The example displays the following output:
'       If
'       what
'       comes
```

Der reguläre Ausdruck `\b[A-Z]+\b(?=\P{P})` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`[A-Z]+` | Sucht ein- oder mehrmals nach einer Übereinstimmung mit einem beliebigen Buchstabenzeichen. Da die [Regex.Matches](xref:System.Text.RegularExpressions.Regex.Matches(System.String))-Methode mit der [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option aufgerufen wird, wird beim Vergleich die Groß-/Kleinschreibung nicht beachtet. 
`\b` | Der Vergleich endet an einer Wortgrenze.
`(?=\P{P})` | Lookahead, um zu bestimmen, ob es sich beim nächsten Zeichen um ein Interpunktionszeichen handelt. Wenn dies nicht der Fall ist, ist der Abgleich erfolgreich.

Weitere Informationen zu positiven Lookaheadassertionen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

### <a name="negative-lookahead"></a>Negatives Lookahead

Negatives Lookahead: **(?!**_teilausdruck_**)**. Diese Funktion ermöglicht es, nur dann eine Übereinstimmung mit einem Ausdruck zu erhalten, wenn ein Teilausdruck kein Ergebnis liefert. Dies ist beim Bereinigen einer Suche besonders effektiv, da es oftmals einfacher ist, einen Ausdruck für einen auszuschließenden Fall anzugeben als einen Ausdruck für Fälle, die eingeschlossen werden sollen. Beispielsweise ist es schwierig, einen Ausdruck für Wörter zu schreiben, die nicht mit „un“ beginnen. Im folgenden Beispiel erfolgt der Ausschluss mithilfe eines negativen Lookaheads.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?!non)\w+\b";
      string input = "Nonsense is not always non-functional.";
      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       is
//       not
//       always
//       functional
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?!non)\w+\b"
      Dim input As String = "Nonsense is not always non-functional."
      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       is
'       not
'       always
'       functional
```

Das Muster für reguläre Ausdrücke `\b(?!non)\w+\b` wird entsprechend der folgenden Tabelle definiert:

Muster | Beschreibung
------- | -----------
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(?!non)` | Lookahead, um sicherzustellen, dass die aktuelle Zeichenfolge nicht mit „non“ beginnt. Andernfalls wird keine Übereinstimmung gefunden.
`(\w+)` | Übereinstimmung mit mindestens einem Wortzeichen.
`\b` | Der Vergleich endet an einer Wortgrenze.
 
Weitere Informationen zu negativen Lookaheadassertionen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

### <a name="conditional-evaluation"></a>Bedingte Auswertung

Bedingte Auswertung: **(?(**_ausdruck_**)**_ja_&#124;_nein_**)** und **(?(**_name_**)**_ja_&#124;_nein_**)**, wobei *ausdruck* ein zu suchender Teilausdruck ist, *name* der Name einer Erfassungsgruppe, *ja* die zu suchende Zeichenfolge, wenn *ausdruck* gefunden wurde oder *name* eine gültige, nicht leere Erfassungsgruppe ist, und *nein* der zu suchende Teilausdruck ist, wenn *ausdruck* nicht gefunden wurde oder *name* keine gültige, nicht leere Erfassungsgruppe ist. Mit dieser Funktion kann das Modul je nach Ergebnis eines vorherigen Teilausdrucksabgleichs oder je nach Ergebnis einer Assertion mit einer Breite von&0; (null) anhand mehrerer Alternativmuster suchen. Dies lässt eine leistungsstärkere Form von Rückverfolgung zu, die es beispielsweise erlaubt, einen Teilausdruck auf der Grundlage davon zu suchen, ob eine Übereinstimmung mit einem vorherigen Teilausdruck gefunden wurde. Der reguläre Ausdruck im folgenden Beispiel gleicht Absätze ab, die sowohl für die öffentliche als auch für die interne Verwendung vorgesehen sind. Absätze, die nur für die interne Verwendung vorgesehen sind, beginnen mit einem `<PRIVATE>`-Tag. Das Muster für reguläre Ausdrücke `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` weist den Inhalt von Absätzen, die für die öffentliche und interne Verwendung vorgesehen sind, mithilfe einer bedingten Auswertung zu, um Erfassungsgruppen zu trennen. Diese Absätze können dann unterschiedlich behandelt werden.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "<PRIVATE> This is not for public consumption." + Environment.NewLine + 
                     "But this is for public consumption." + Environment.NewLine + 
                     "<PRIVATE> Again, this is confidential.\n";  
      string pattern = @"^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$";
      string publicDocument = null, privateDocument = null;

      foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Multiline))
      {
         if (match.Groups[1].Success) {
            privateDocument += match.Groups[1].Value + "\n";
         }
         else {
            publicDocument += match.Groups[3].Value + "\n";   
            privateDocument += match.Groups[3].Value + "\n";
         }  
      }

      Console.WriteLine("Private Document:");
      Console.WriteLine(privateDocument);
      Console.WriteLine("Public Document:");
      Console.WriteLine(publicDocument);
   }
}
// The example displays the following output:
//    Private Document:
//    This is not for public consumption.
//    But this is for public consumption.
//    Again, this is confidential.
//    
//    Public Document:
//    But this is for public consumption.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "<PRIVATE> This is not for public consumption." + vbCrLf + _
                            "But this is for public consumption." + vbCrLf + _
                            "<PRIVATE> Again, this is confidential." + vbCrLf
      Dim pattern As String = "^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$"
      Dim publicDocument As String = Nothing
      Dim privateDocument As String = Nothing

      For Each match As Match In Regex.Matches(input, pattern, RegexOptions.Multiline)
         If match.Groups(1).Success Then
            privateDocument += match.Groups(1).Value + vbCrLf
         Else
            publicDocument += match.Groups(3).Value + vbCrLf   
            privateDocument += match.Groups(3).Value + vbCrLf
         End If  
      Next

      Console.WriteLine("Private Document:")
      Console.WriteLine(privateDocument)
      Console.WriteLine("Public Document:")
      Console.WriteLine(publicDocument)
   End Sub
End Module
' The example displays the following output:
'    Private Document:
'    This is not for public consumption.
'    But this is for public consumption.
'    Again, this is confidential.
'    
'    Public Document:
'    But this is for public consumption.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | -----------
`^` | Beginnt den Abgleich am Anfang einer Zeile.
`(?<Pvt>\<PRIVATE\>\s)?` | Sucht nach&0; oder&1; Vorkommen der Zeichenfolge `<PRIVATE>`, gefolgt von einem Leerzeichen. Weist die Übereinstimmung der Erfassungsgruppe „Pvt“ zu.
`(?(Pvt)((\w+\p{P}?\s)+)` | Wenn die Erfassungsgruppe `Pvt` vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen&0; oder&1; Interpunktionszeichen und dann ein Leerzeichen folgen. Weist die Teilzeichenfolge der ersten Erfassungsgruppe zu.
`&#124;((\w+\p{P}?\s)+))` | Wenn die Erfassungsgruppe `Pvt` nicht vorhanden ist, wird nach einem oder mehreren Vorkommen eines oder mehrerer Wortzeichen gesucht, denen&0; oder&1; Interpunktionszeichen und dann ein Leerzeichen folgen. Weist die Teilzeichenfolge der dritten Erfassungsgruppe zu.
`\r?$` | Gleicht das Ende einer Zeile oder das Ende der Zeichenfolge ab.
 
Weitere Informationen zur bedingten Auswertung finden Sie unter [Alternierungskonstrukte in regulären Ausdrücken](alternation.md).

### <a name="balancing-group-definitions"></a>Ausgleichen von Gruppendefinitionen

Ausgleichen von Gruppendefinitionen: **(?<**_name1-name2_**>** _teilausdruck_**)**. Diese Funktion ermöglicht es dem Modul für reguläre Ausdrücke, geschachtelte Konstrukte nachzuverfolgen, z.B. runde Klammern oder öffnende und schließende eckige Klammern. Ein Beispiel finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

### <a name="nonbacktracking-subexpressions"></a>Nicht zurückverfolgende Teilausdrücke

Teilausdrücke ohne Rückverfolgung (auch als gierige Teilausdrücke bezeichnet): **(?>**_teilausdruck_**)**. Durch diese Funktion kann das Rückverfolgungsmodul sicherstellen, dass nur die erste Übereinstimmung mit einem Teilausdruck geliefert wird, so als wäre der Teilausdruck unabhängig von dem vollständigen Ausdruck. Wenn Sie dieses Konstrukt nicht verwenden, kann das Verhalten eines Teilausdrucks durch Suchläufe mit Rückverfolgung über den längeren Ausdruck beeinflusst werden. Der reguläre Ausdruck `(a+)\w` stimmt beispielsweise mit einem oder mehreren „a“-Zeichen sowie einem Wortzeichen überein, das der Sequenz von „a“-Zeichen folgt, und weist die Sequenz von „a“-Zeichen der ersten Erfassungsgruppe zu. Wenn das abschließende Zeichen der Eingabezeichenfolge jedoch ebenfalls ein „a“ ist, wird es mit dem Sprachelement `\w` abgeglichen und nicht in die Erfassungsgruppe aufgenommen.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string backtrackingPattern = @"(a+)\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, backtrackingPattern);
         Console.WriteLine("   Pattern: {0}", backtrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: (a+)\w
//             Match: aaaaa
//             Group 1: aaaa
//       Input: aaaaab
//          Pattern: (a+)\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim backtrackingPattern As String = "(a+)\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, backtrackingPattern)
         Console.WriteLine("   Pattern: {0}", backtrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: (a+)\w
'             Match: aaaaa
'             Group 1: aaaa
'       Input: aaaaab
'          Pattern: (a+)\w
'             Match: aaaaab
'             Group 1: aaaaa
```

Der reguläre Ausdruck `((?>a+))\w` verhindert dieses Verhalten. Da alle aufeinander folgenden „a“-Zeichen ohne Rückverfolgung abgeglichen werden, sind alle aufeinander folgenden „a“-Zeichen in der ersten Erfassungsgruppe enthalten. Wenn dem „a“-Zeichen nicht mindestens ein weiteres Zeichen folgt, bei dem es sich nicht um „a“ handelt, liegt keine Übereinstimmung vor.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "aaaaa", "aaaaab" };
      string nonbacktrackingPattern = @"((?>a+))\w";
      Match match;

      foreach (string input in inputs) {
         Console.WriteLine("Input: {0}", input);
         match = Regex.Match(input, nonbacktrackingPattern);
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern);
         if (match.Success) { 
            Console.WriteLine("      Match: {0}", match.Value);
            Console.WriteLine("      Group 1: {0}", match.Groups[1].Value);
         }
         else {
            Console.WriteLine("      Match failed.");
         }   
      }
      Console.WriteLine();            
   }
}
// The example displays the following output:
//       Input: aaaaa
//          Pattern: ((?>a+))\w
//             Match failed.
//       Input: aaaaab
//          Pattern: ((?>a+))\w
//             Match: aaaaab
//             Group 1: aaaaa
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "aaaaa", "aaaaab" }
      Dim nonbacktrackingPattern As String = "((?>a+))\w"
      Dim match As Match

      For Each input As String In inputs
         Console.WriteLine("Input: {0}", input)
         match = Regex.Match(input, nonbacktrackingPattern)
         Console.WriteLine("   Pattern: {0}", nonbacktrackingPattern)
         If match.Success Then 
            Console.WriteLine("      Match: {0}", match.Value)
            Console.WriteLine("      Group 1: {0}", match.Groups(1).Value)
         Else 
            Console.WriteLine("      Match failed.")
         End If   
      Next
      Console.WriteLine()            
   End Sub
End Module
' The example displays the following output:
'       Input: aaaaa
'          Pattern: ((?>a+))\w
'             Match failed.
'       Input: aaaaab
'          Pattern: ((?>a+))\w
'             Match: aaaaab
'             Group 1: aaaaa
```

Weitere Informationen zu Teilausdrücken ohne Rückverfolgung finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

### <a name="right-to-left-matching"></a>Abgleich von rechts nach links

Der Abgleich von rechts nach links, der durch Festlegen der [RegexOptions.RightToLeft](xref:System.Text.RegularExpressions.RegexOptions.RightToLeft)-Option für eine Suchmethode für [Regex](xref:System.Text.RegularExpressions.Regex)-Klassenkonstruktoren oder statische Instanzen angegeben wird. Diese Funktion eignet sich für die Suche von rechts nach links (statt von links nach rechts) oder in Fällen, in denen es effektiver ist, auf der rechten Seite eines Musters mit der Suche zu beginnen. Wie im folgenden Beispiel veranschaulicht, kann mit dem Abgleich von rechts nach links das Verhalten gieriger Quantifizierer geändert werden. Im Beispiel werden zwei Suchen nach einem Satz ausgeführt, der auf eine Zahl endet. Mit der Suche von links nach rechts, für die der gierige Quantifizierer `+` verwendet wird, wird eine der sechs Ziffern im Satz gefunden. Hingegen werden bei der Suche von rechts nach links alle sechs Ziffern gefunden. Eine Beschreibung des Musters für reguläre Ausdrücke finden Sie weiter oben in diesem Abschnitt im Beispiel zur Veranschaulichung träger Quantifizierer.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string greedyPattern = @".+(\d+)\.";
      string input = "This sentence ends with the number 107325.";
      Match match;

      // Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);

      // Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft);
      if (match.Success)
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups[1].Value);
      else
         Console.WriteLine("{0} finds no match.", greedyPattern);
   }
}
// The example displays the following output:
//       Number at end of sentence (left-to-right): 5
//       Number at end of sentence (right-to-left): 107325
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim greedyPattern As String = ".+(\d+)\."
      Dim input As String = "This sentence ends with the number 107325."
      Dim match As Match

      ' Match from left-to-right using lazy quantifier .+?.
      match = Regex.Match(input, greedyPattern)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (left-to-right): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If

      ' Match from right-to-left using greedy quantifier .+.
      match = Regex.Match(input, greedyPattern, RegexOptions.RightToLeft)
      If match.Success Then
         Console.WriteLine("Number at end of sentence (right-to-left): {0}", 
                           match.Groups(1).Value)
      Else
         Console.WriteLine("{0} finds no match.", greedyPattern)
      End If
   End Sub
End Module
' The example displays the following output:
'       Number at end of sentence (left-to-right): 5
'       Number at end of sentence (right-to-left): 107325
```

Weitere Informationen zum Abgleich von rechts nach links finden Sie unter [Optionen für reguläre Ausdrücke](options.md).

### <a name="positive-and-negative-lookbehind"></a>Positives und negatives Lookbehind

Positives und negatives Lookbehind: **(?<**=_teilausdruck_**)** für positives Lookbehind und **(?<!**_teilausdruck_**)** für negatives Lookbehind. Diese Funktion ähnelt dem zuvor in diesem Thema erläuterten Lookahead. Reguläre Ausdrücke gestatten uneingeschränkte Lookbehinds, da eine vollständige Suche nach Übereinstimmungen von rechts nach links möglich ist. Positives und negatives Lookbehind können auch verwendet werden, um das Schachteln von Quantifizierern zu vermeiden, wenn der geschachtelte Teilausdruck eine Obermenge eines äußeren Ausdrucks ist. Reguläre Ausdrücke mit solchen geschachtelten Quantifizierern bieten oft eine schlechte Leistung. Im folgenden Beispiel wird z.B. überprüft, ob eine Zeichenfolge mit einem alphanumerischen Zeichen beginnt und endet und ob ein beliebiges anderes Zeichen in der Zeichenfolge zu einer größeren Teilmenge gehört. Sie bildet einen Teil des regulären Ausdrucks zum Überprüfen von E-Mail-Adressen. Weitere Informationen finden Sie unter [Gewusst wie: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](verify-format.md).

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                          "me.myself!" };
      string pattern = @"^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$";
      foreach (string input in inputs) {
         if (Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase))
            Console.WriteLine("{0}: Valid", input);
         else
            Console.WriteLine("{0}: Invalid", input);
      }
   }
}
// The example displays the following output:
//       jack.sprat: Valid
//       dog#: Invalid
//       dog#1: Valid
//       me.myself: Valid
//       me.myself!: Invalid
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "jack.sprat", "dog#", "dog#1", "me.myself", 
                                 "me.myself!" }
      Dim pattern As String = "^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$"
      For Each input As String In inputs
         If Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase) Then
            Console.WriteLine("{0}: Valid", input)
         Else
            Console.WriteLine("{0}: Invalid", input)
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       jack.sprat: Valid
'       dog#: Invalid
'       dog#1: Valid
'       me.myself: Valid
'       me.myself!: Invalid
```

Der reguläre Ausdruck `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` wird entsprechend der Darstellung in der folgenden Tabelle definiert.

Muster | Beschreibung
------- | ----------- 
`^` | Beginnt die Suche am Anfang der Zeichenfolge.
`[A-Z0-9]` | Übereinstimmung mit beliebigem numerischen oder alphanumerischen Zeichen. (Beim Vergleich wird die Groß-und Kleinschreibung nicht berücksichtigt.)
`([-!#$%&'.*+/=?^`{}&#124;~\w])*` | Übereinstimmung mit null oder mehr Vorkommen eines beliebigen Wortzeichens oder eines der folgenden Zeichen: -, !, #, $, %, &, ', ., *, +, /, =, ?, ^, `, {, }, &#124; oder ~.
`(?<=[A-Z0-9])` | Lookbehind für vorheriges Zeichen, das numerisch oder alphanumerisch sein muss. (Beim Vergleich wird die Groß-und Kleinschreibung nicht berücksichtigt.)
`$` | Beendet die Suche am Ende der Zeichenfolge.
 
Weitere Informationen zu positivem und negativem Lookbehind finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).


## <a name="related-topics"></a>Verwandte Themen

Titel | Beschreibung
----- | ----------- 
[Backtracking](backtracking.md) | Informationen über die Verwendung der Rückverfolgung bei regulären Ausdrücken, um mit Verzweigungen nach alternativen Übereinstimmungen zu suchen.
[Kompilierung und Wiederverwendung](compilation.md) | Informationen zum Kompilieren und Wiederverwenden regulärer Ausdrücke mit dem Ziel der Leistungsverbesserung.
[Threadsicherheit](thread-safety.md) | Informationen zur Threadsicherheit bei regulären Ausdrücken und Erläuterungen zur Notwendigkeit eines synchronisierten Zugriffs auf Objekte in regulären Ausdrücken.
[Reguläre Ausdrücke in .NET](regular-expressions.md) | Übersicht über die programmiersprachenbezogenen Aspekte von regulären Ausdrücken.
[Das Objektmodell für reguläre Ausdrücke](object-model.md) | Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.
[Beispiele für reguläre Ausdrücke](regex-examples.md) | Codebeispiele, die die Verwendung regulärer Ausdrücke in üblichen Anwendungen veranschaulichen.
[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md) | Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.
 
## <a name="reference"></a>Verweis

[System.Text.RegularExpressions](xref:System.Text.RegularExpressions)


