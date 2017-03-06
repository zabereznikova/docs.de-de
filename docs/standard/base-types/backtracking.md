---
title: "Rückverfolgung in regulären Ausdrücken"
description: "Rückverfolgung in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8a3e6298-26b7-4c99-bd97-c9892f6c9418
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 58925ce755e995432f3ff205793a192f34999e12
ms.lasthandoff: 03/02/2017

---

# <a name="backtracking-in-regular-expressions"></a>Rückverfolgung in regulären Ausdrücken

Eine Rückverfolgung tritt ein, wenn ein Muster eines regulären Ausdrucks optionale [Quantifizierer](quantifiers.md) oder [Alternierungskonstrukte](alternation.md) enthält und das Modul für reguläre Ausdrücke in einen zuvor gespeicherten Zustand zurückkehrt, um die Suche nach einer Übereinstimmung fortzusetzen. Die Rückverfolgung ist für die Leistungsfähigkeit regulärer Ausdrücke von zentraler Bedeutung. Sie ermöglicht flexible und leistungsstarke Ausdrücke, die höchst komplexen Muster entsprechen können. Diese Leistungsfähigkeit zieht aber auch Nachteile mit sich. Die Rückverfolgung ist häufig der wichtigste Faktor, der sich auf die Leistung des Moduls für reguläre Ausdrücke auswirkt. Der Entwickler kann jedoch steuern, wie sich das Modul für reguläre Ausdrücke verhält und wie die Rückverfolgung verwendet wird. In diesem Thema wird erläutert, wie die Rückverfolgung funktioniert und wie sie gesteuert werden kann.

> [!NOTE]
> Bei einem NFA-Modul (Nondeterministic Finite Automaton) wie dem Modul für reguläre Ausdrücke liegt die Verantwortung für die Erstellung effizienter und schneller regulärer Ausdrücke im Allgemeinen beim Entwickler.
 
Dieses Thema enthält folgende Abschnitte:

* [Linearer Vergleich ohne Rückverfolgung](#linear-comparison-without-backtracking)

* [Rückverfolgung mit optionalen Quantifizierern oder Alternierungskonstrukten](#backtracking-with-optional-quantifiers-or-alternation-constructs)

* [Rückverfolgung mit geschachtelten optionalen Quantifizierern](#backtracking-with-nested-optional-quantifiers)

* [Steuern der Rückverfolgung](#controlling-backtracking)

## <a name="linear-comparison-without-backtracking"></a>Linearer Vergleich ohne Rückverfolgung

Wenn das Muster eines regulären Ausdrucks nicht über optionale Quantifizierer oder Alternierungskonstrukte verfügt, wird das Modul für reguläre Ausdrücke zeitlich linear ausgeführt. Das heißt, nachdem das Modul für reguläre Ausdrücke dem ersten Sprachelement im Muster Text in der Eingabezeichenfolge zugeordnet hat, wird versucht, das nächste Sprachelement im Muster dem nächsten Zeichen oder der nächsten Zeichengruppe in der Eingabezeichenfolge zuzuordnen. Dies wird fortgesetzt, bis die Übereinstimmung erfolgreich ausgeführt wurde oder fehlschlägt. In beiden Fällen wechselt das Modul für reguläre Ausdrücke immer je ein Zeichen in der Eingabezeichenfolge weiter.

Dies wird im folgenden Beispiel veranschaulicht. Der reguläre Ausdruck `e{2}\w\b` sucht nach zwei Vorkommen des Buchstabens "e", gefolgt von einem beliebigen Wortzeichen, wiederum gefolgt von einer Wortgrenze.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "needing a reed";
      string pattern = @"e{2}\w\b";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("{0} found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       eed found at position 11
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "needing a reed"
      Dim pattern As String = "e{2}\w\b"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("{0} found at position {1}", _
                           match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       eed found at position 11
```

Obwohl dieser reguläre Ausdruck den Quantifizierer `{2}` einschließt, wird er auf lineare Weise ausgewertet. Das Modul für reguläre Ausdrücke wird nicht zurückverfolgt, da `{2}` kein optionaler Quantifizierer ist, sondern eine genaue Zahl angibt und keine variable Anzahl von Übereinstimmungen des vorherigen Teilausdrucks. Daher versucht das Modul für reguläre Ausdrücke, eine Übereinstimmung des regulären Ausdrucksmusters mit der Eingabezeichenfolge wie in der folgenden Tabelle dargestellt zu finden.

Vorgang | Position im Muster | Position in der Zeichenfolge | Ergebnis
--------- | ------------------- | ------------------ | ------ 
1 | e | "needing a reed" (Index 0) | Keine Übereinstimmung. 
2 | e | "eeding a reed" (Index 1) | Mögliche Übereinstimmung. 
3 | e{2} | "eding a reed" (Index 2) | Mögliche Übereinstimmung. 
4 | \w | "ding a reed" (Index 3) | Mögliche Übereinstimmung.
5 | \b | "ing a reed" (Index 4) | Mögliche Übereinstimmung schlägt fehl. 
6 | e | "eding a reed" (Index 2) | Mögliche Übereinstimmung. 
7 | e{2} | "ding a reed" (Index 3) | Mögliche Übereinstimmung schlägt fehl. 
8 | e | "ding a reed" (Index 3) | Übereinstimmung schlägt fehl. 
9 | e | "ing a reed" (Index 4) | Keine Übereinstimmung.
10 | e | "ng a reed" (Index 5) | Keine Übereinstimmung.
11 | e | "g a reed" (Index 6) | Keine Übereinstimmung.
12 | e | „ a reed“ (Index 7) | Keine Übereinstimmung.
13 | e | "a reed" (Index 8) | Keine Übereinstimmung.
14 | e | „ reed“ (Index 9) | Keine Übereinstimmung.
15 | e | "a reed" (Index 10) | Keine Übereinstimmung
16 | e | "eed" (Index 11) | Mögliche Übereinstimmung.
17 | e{2} | "ed" (Index 12) | Mögliche Übereinstimmung.
18 | \w | "d" (Index 13) | Mögliche Übereinstimmung.
19 | \b | "" (Index 14) | Übereinstimmung.
 

Wenn das Muster eines regulären Ausdrucks keine optionalen Quantifizierer oder Alternierungskonstrukte enthält, entspricht die maximale Anzahl von Vergleichen, die für die Übereinstimmung des regulären Ausdrucksmusters mit der Eingabezeichenfolge erforderlich sind, ungefähr der Anzahl der Zeichen in der Eingabezeichenfolge. In diesem Fall verwendet das Modul für reguläre Ausdrücke 19 Vergleiche, um mögliche Übereinstimmungen in dieser Zeichenfolge mit 13 Zeichen zu identifizieren. Mit anderen Worten, das Modul für reguläre Ausdrücke wird zeitlich annähernd linear ausgeführt, wenn es keine optionalen Quantifizierer oder Alternierungskonstrukte enthält.

## <a name="backtracking-with-optional-quantifiers-or-alternation-constructs"></a>Rückverfolgung mit optionalen Quantifizierern oder Alternierungskonstrukten

Wenn ein regulärer Ausdruck optionale Quantifizierer oder Alternierungskonstrukte enthält, erfolgt die Auswertung der Eingabezeichenfolge nicht mehr linear. Mustervergleiche mit einem NFA-Modul werden durch die Sprachelemente im regulären Ausdruck und nicht durch die Zeichen gesteuert, für die in der Eingabezeichenfolge Übereinstimmungen gefunden werden sollen. Daher versucht das Modul für reguläre Ausdrücke, vollständige Übereinstimmungen für die optionalen oder alternativen Teilausdrücke zu finden. Wenn zum nächsten Sprachelement im Teilausdruck gewechselt und keine Übereinstimmung gefunden wird, kann das Modul für reguläre Ausdrücke einen Teil der erfolgreichen Übereinstimmung aufgeben und zu einem zuvor gespeicherten Zustand zurückkehren, um eine Übereinstimmung des gesamten regulären Ausdrucks mit der Eingabezeichenfolge zu erzielen. Dieses Zurückkehren zu einem zuvor gespeicherten Zustand, um eine Übereinstimmung zu finden, wird als Rückverfolgung bezeichnet.

Als Beispiel dient das reguläre Ausdrucksmuster `.*(es)`, das mit den Zeichen "es" und allen vorangestellten Zeichen übereinstimmt. Wenn die Eingabezeichenfolge "Essential services are provided by regular expressions." lautet, wird die gesamte Zeichenfolge bis einschließlich der Zeichen "es" im Wort "expressions" nach einer Übereinstimmung mit dem Muster durchsucht.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "Essential services are provided by regular expressions.";
      string pattern = ".*(es)"; 
      Match m = Regex.Match(input, pattern, RegexOptions.IgnoreCase);
      if (m.Success) {
         Console.WriteLine("'{0}' found at position {1}", 
                           m.Value, m.Index);
         Console.WriteLine("'es' found at position {0}", 
                           m.Groups[1].Index);      
      } 
   }
}
//    'Essential services are provided by regular expres' found at position 0
//    'es' found at position 47
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "Essential services are provided by regular expressions."
      Dim pattern As String = ".*(es)" 
      Dim m As Match = Regex.Match(input, pattern, RegexOptions.IgnoreCase)
      If m.Success Then
         Console.WriteLine("'{0}' found at position {1}", _
                           m.Value, m.Index)
         Console.WriteLine("'es' found at position {0}", _
                           m.Groups(1).Index)                  
      End If     
   End Sub
End Module
'    'Essential services are provided by regular expres' found at position 0
'    'es' found at position 47
```

Hierzu verwendet das Modul für reguläre Ausdrücke das Zurückverfolgen wie folgt:

* Die gesamte Eingabezeichenfolge wird auf Übereinstimmung mit `.*` (Übereinstimmung mit keinem, einem oder mehreren Vorkommen beliebiger Zeichen) geprüft.

* Es wird versucht, eine Übereinstimmung mit "e" im Muster des regulären Ausdrucks zu finden. Die Eingabezeichenfolge weist jedoch keine weiteren Zeichen für eine Übereinstimmung auf.

* Es wird eine Rückverfolgung zur letzten erfolgreichen Übereinstimmung ausgeführt ("Essential services are provided by regular expressions") und versucht, eine Übereinstimmung von "e" mit dem Punkt am Satzende zu finden. Die Übereinstimmung schlägt fehl.

* Die Rückverfolgung zu einer vorherigen erfolgreichen Übereinstimmung wird um je ein Zeichen fortgesetzt, bis die vorläufige übereinstimmende Teilzeichenfolge "Essential services are provided by regular expr" lautet. Anschließend wird das "e" im Muster mit dem zweiten "e" in "expressions" verglichen, und es wird eine Übereinstimmung gefunden.

* Das "s" im Muster wird mit dem "s" verglichen, das dem übereinstimmenden Zeichen "e" folgt (das erste "s" in"expressions"). Die Übereinstimmung ist erfolgreich.

Bei einer Rückverfolgung erfordert das Abgleichen des regulären Ausdrucksmusters mit der Eingabezeichenfolge, die 55 Zeichen lang ist, 67 Vergleichsoperationen. Wenn das Muster des regulären Ausdrucks einen verzögerten Quantifizierer – `.*?(es),` – enthält, sind für den Abgleich mit dem regulären Ausdruck interessanterweise weitere Vergleiche erforderlich. In diesem Fall muss keine Rückverfolgung vom Ende der Zeichenfolge bis zum "r" in "expressions" erfolgen, sondern das Modul für reguläre Ausdrücke würde eine Rückverfolgung bis zum Anfang der Zeichenfolge ausführen, um eine Übereinstimmung mit "Es" zu finden. Hierfür wären 113 Vergleiche erforderlich. Wenn das Muster eines regulären Ausdrucks ein einzelnes Alternierungskonstrukt oder einen einzelnen optionalen Quantifizierer enthält, ist die Anzahl der zum Abgleichen eines Musters erforderlichen Vergleichsoperationen im Allgemeinen mehr als doppelt so hoch wie die Anzahl der Zeichen in der Eingabezeichenfolge.

## <a name="backtracking-with-nested-optional-quantifiers"></a>Rückverfolgung mit geschachtelten optionalen Quantifizierern

Die Anzahl der für den Abgleich mit einem regulären Ausdrucksmuster erforderlichen Vergleichsoperationen kann sich exponentiell erhöhen, wenn das Muster viele Alternierungskonstrukte bzw. geschachtelte Alternierungskonstrukte oder, wie es am häufigsten vorkommt, geschachtelte optionale Quantifizierer enthält. Beispielsweise ist das reguläre Ausdrucksmuster `^(a+)+$` darauf ausgelegt, eine Übereinstimmung mit einer vollständigen Zeichenfolge zu finden, die mindestens ein "a" enthält. Das Beispiel stellt zwei Eingabezeichenfolgen mit identischer Länge bereit. Aber nur die erste Zeichenfolge stimmt mit dem Muster überein. Die [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch)-Klasse wird verwendet, um zu bestimmen, wie lange die Vergleichsoperation dauert. 

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "^(a+)+$";
      string[] inputs = { "aaaaaa", "aaaaa!" };
      Regex rgx = new Regex(pattern);
      Stopwatch sw;

      foreach (string input in inputs) {
         sw = Stopwatch.StartNew();   
         Match match = rgx.Match(input);
         sw.Stop();
         if (match.Success)
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed);
         else
            Console.WriteLine("No match found in {0}", sw.Elapsed);
      }
   }
}
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(a+)+$"
      Dim inputs() As String = { "aaaaaa", "aaaaa!" }
      Dim rgx As New Regex(pattern)
      Dim sw As Stopwatch

      For Each input As String In inputs
         sw = Stopwatch.StartNew()   
         Dim match As Match = rgx.Match(input)
         sw.Stop()
         If match.Success Then
            Console.WriteLine("Matched {0} in {1}", match.Value, sw.Elapsed)
         Else
            Console.WriteLine("No match found in {0}", sw.Elapsed)
         End If      
      Next
   End Sub
End Module
```

Wie die Ausgabe des Beispiels zeigt, brauchte das Modul für reguläre Ausdrücke zum Bestimmen, dass eine Eingabezeichenfolge nicht mit dem Muster übereinstimmt, etwa doppelt so lang wie für die Ermittlung einer übereinstimmenden Zeichenfolge. Dies liegt daran, dass eine fehlgeschlagene Übereinstimmung immer den ungünstigsten Fall darstellt. Das Modul für reguläre Ausdrücke muss den regulären Ausdruck verwenden, um allen möglichen Pfaden durch die Daten zu folgen, bevor es feststellen kann, ob die Übereinstimmung fehlschlägt. Durch die geschachtelten Klammern werden viele zusätzliche Pfade durch die Daten erstellt. Das Modul für reguläre Ausdrücke stellt fest, dass die zweite Zeichenfolge nicht mit dem Muster übereinstimmt, indem wie folgt vorgegangen wird:

* Das Modul überprüft, ob es sich am Anfang der Zeichenfolge befindet, und vergleicht dann die ersten fünf Zeichen in der Zeichenfolge mit dem Muster a+. Anschließend wird sichergestellt, dass keine weiteren Gruppen des Zeichens "a" in der Zeichenfolge vorhanden sind. Schließlich wird das Ende der Zeichenfolge überprüft. Da ein zusätzliches Zeichen in der Zeichenfolge verbleibt, schlägt die Übereinstimmung fehl. Diese fehlgeschlagene Suche nach Übereinstimmung erfordert 9 Vergleiche. Das Modul für reguläre Ausdrücke speichert darüber hinaus Zustandsinformationen aus den Übereinstimmungen von "a" (hier bezeichnet als Übereinstimmung 1), "aa" (Übereinstimmung 2), "aaa" (Übereinstimmung 3) und "aaaa" (Übereinstimmung 4).

* Das Modul kehrt zur zuvor gespeicherten Übereinstimmung 4 zurück. Es wird ermittelt, dass ein zusätzliches Zeichen "a" vorhanden ist, das einer zusätzlichen Erfassungsgruppe zugewiesen werden soll. Schließlich wird das Ende der Zeichenfolge überprüft. Da ein zusätzliches Zeichen in der Zeichenfolge verbleibt, schlägt die Übereinstimmung fehl. Diese fehlgeschlagene Suche nach Übereinstimmung erfordert 4 Vergleiche. Bisher wurden insgesamt 13 Vergleiche ausgeführt.

* Das Modul kehrt zur zuvor gespeicherten Übereinstimmung 3 zurück. Es wird ermittelt, dass zwei zusätzliche "a"-Zeichen vorhanden sind, die einer zusätzlichen Erfassungsgruppe zugewiesen werden sollen. Allerdings schlägt die Überprüfung des Zeichenfolgenendes fehl. Anschließend kehrt das Modul zur Übereinstimmung&3; zurück und versucht, die zwei zusätzlichen "a"-Zeichen in zwei zusätzlichen Erfassungsgruppen abzugleichen. Die Überprüfung des Zeichenfolgenendes schlägt weiterhin fehl. Diese fehlgeschlagenen Übereinstimmungen erfordern 12 Vergleiche. Bisher wurden insgesamt 25 Vergleiche ausgeführt. 

Der Vergleich der Eingabezeichenfolge mit dem regulären Ausdruck wird auf diese Weise fortgesetzt, bis das Modul für reguläre Ausdrücke alle möglichen Übereinstimmungskombinationen durchlaufen hat und dann feststellt, dass keine Übereinstimmung vorhanden ist. Aufgrund der geschachtelten Quantifizierer handelt es sich bei diesem Vergleich um O(2n) oder einen exponentiellen Vorgang, wobei n für die Anzahl von Zeichen in der Eingabezeichenfolge steht. Dies bedeutet, dass im ungünstigsten Fall für eine Eingabezeichenfolge von 30 Zeichen etwa 1.073.741.824 Vergleiche und für eine Eingabezeichenfolge von 40 Zeichen ungefähr 1.099.511.627.776 Vergleiche erforderlich sind. Wenn Sie Zeichenfolgen mit dieser oder sogar einer größeren Länge verwenden, kann die Ausführung von Methoden mit regulären Ausdrücken erhebliche Zeit in Anspruch nehmen, wenn diese Eingaben verarbeiten, die nicht mit dem regulären Ausdrucksmuster übereinstimmen.

## <a name="controlling-backtracking"></a>Steuern der Rückverfolgung

Mithilfe der Rückverfolgung können Sie leistungsstarke, flexible reguläre Ausdrücke erstellen. Wie allerdings im vorangegangenen Abschnitt erläutert, sind diese Vorteile u. U. mit einer inakzeptabel schlechten Leistung verknüpft. Um eine übermäßige Rückverfolgung zu verhindern, sollten Sie ein Timeoutintervall definieren, wenn Sie ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt instanziieren oder eine statische Methode für Übereinstimmungen mit regulären Ausdrücken aufrufen. Dies wird im nächsten Abschnitt erläutert. Darüber hinaus unterstützt .NET Core drei Sprachelemente für reguläre Ausdrücke, die das Zurückverfolgen einschränken oder unterdrücken und komplexe reguläre Ausdrücke bei nur wenigen oder gar keinen Leistungseinbußen unterstützen: [nicht zurückverfolgende Teilausdrücke](#nonbacktracking-subexpression), [Lookbehindassertionen](#lookbehind-assertions) und [Lookaheadassertionen](#lookahead-assertions). Weitere Informationen zu den einzelnen Sprachelementen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).

### <a name="defining-a-time-out-interval"></a>Definieren eines Timeoutintervalls

Sie können einen Timeoutwert für das längste Intervall festlegen, innerhalb dessen das Modul für reguläre Ausdrücke nach einer einzelnen Übereinstimmung sucht, bevor der Versuch abgebrochen und eine [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException)-Ausnahme ausgelöst wird. Sie geben das Timeoutintervall an, indem Sie einen [TimeSpan](xref:System.TimeSpan)-Wert für den `Regex(String, RegexOptions, TimeSpan)`-Konstruktor für reguläre Ausdrucksinstanzen bereitstellen. Außerdem weist jede statische Methode für Musterübereinstimmungen eine Überladung mit einem [TimeSpan](xref:System.TimeSpan)-Wert zu dem [Regex.Regex(String, RegexOptions, TimeSpan)]-Parameter auf, der Ihnen ermöglicht, einen Timeoutwert anzugeben. Standardmäßig wird das Timeoutintervall auf [Regex.InfiniteMatchTimeout](xref:System.Text.RegularExpressions.Regex.InfiniteMatchTimeout) festgelegt, und das Modul für reguläre Ausdrücke gibt kein Timeout zurück. 

> [!IMPORTANT]
> Sie sollten immer ein Timeoutintervall festlegen, wenn ein regulärer Ausdruck auf Rückverfolgung angewiesen ist.
 
Eine [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException)-Ausnahme gibt an, dass das Modul für reguläre Ausdrücke keine Übereinstimmung innerhalb des angegebenen Timeoutintervalls finden konnte, es gibt aber nicht an, warum die Ausnahme ausgelöst wurde. Der Grund kann eine übermäßige Rückverfolgung sein. Es ist jedoch auch möglich, dass das Timeoutintervall angesichts der Systembelastung zum Zeitpunkt, als die Ausnahme ausgelöst wurde, zu niedrig festgelegt wurde. Wenn Sie die Ausnahme behandeln, können Sie entweder weitere Übereinstimmungen mit der Eingabezeichenfolge abbrechen oder das Timeoutintervall erhöhen und den Vergleichsvorgang erneut ausführen. 

Im folgenden Code wird beispielsweise der `Regex(String, RegexOptions, TimeSpan)`-Konstruktor aufgerufen, um ein Regex-Objekt mit einem Timeoutwert von einer Sekunde zu instanziieren. Das Muster des regulären Ausdrucks `(a+)+$`, das mit mindestens einer Sequenz von einem oder mehreren "a"-Zeichen am Ende einer Zeile übereinstimmt, unterliegt übermäßiger Rückverfolgung. Wenn [RegexMatchTimeoutException](xref:System.Text.RegularExpressions.RegexMatchTimeoutException) ausgelöst wird, wird der Timeoutwert im Beispiel bis zu einem maximalen Intervall von drei Sekunden erhöht. Danach wird der Versuch, das Muster abzugleichen, abgebrochen.

```csharp
using System;
using System.ComponentModel;
using System.Diagnostics;
using System.Security;
using System.Text.RegularExpressions;
using System.Threading; 

public class Example
{
   const int MaxTimeoutInSeconds = 3;

   public static void Main()
   {
      string pattern = @"(a+)+$";    // DO NOT REUSE THIS PATTERN.
      Regex rgx = new Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1));       
      Stopwatch sw = null;

      string[] inputs= { "aa", "aaaa>", 
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                         "aaaaaaaaaaaaaaaaaaaaaa>",
                         "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" };

      foreach (var inputValue in inputs) {
         Console.WriteLine("Processing {0}", inputValue);
         bool timedOut = false;
         do { 
            try {
               sw = Stopwatch.StartNew();
               // Display the result.
               if (rgx.IsMatch(inputValue)) {
                  sw.Stop();
                  Console.WriteLine(@"Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed); 
               }
               else {
                  sw.Stop();
                  Console.WriteLine(@"'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed);
               }
            }
            catch (RegexMatchTimeoutException e) {   
               sw.Stop();
               // Display the elapsed time until the exception.
               Console.WriteLine(@"Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed);
               Thread.Sleep(1500);       // Pause for 1.5 seconds.

               // Increase the timeout interval and retry.
               TimeSpan timeout = e.MatchTimeout.Add(TimeSpan.FromSeconds(1));
               if (timeout.TotalSeconds > MaxTimeoutInSeconds) {
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds);
                  timedOut = false;
               }
               else {               
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout); 
                  rgx = new Regex(pattern, RegexOptions.IgnoreCase, timeout);
                  timedOut = true;
               }
            }
         } while (timedOut);
         Console.WriteLine();
      }   
   }
}
// The example displays output like the following :
//    Processing aa
//    Valid: 'aa' (00.0000779 seconds)
//    
//    Processing aaaa>
//    'aaaa>' is not a valid string. (00.00005 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
//    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
//    Changing the timeout interval to 00:00:02
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
//    Changing the timeout interval to 00:00:03
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
//    Maximum timeout interval of 3 seconds exceeded.
//    
//    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
//    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
//    Maximum timeout interval of 3 seconds exceeded.
```

```vb
Imports System.ComponentModel
Imports System.Diagnostics
Imports System.Security
Imports System.Text.RegularExpressions
Imports System.Threading 

Module Example
   Const MaxTimeoutInSeconds As Integer = 3

   Public Sub Main()
      Dim pattern As String = "(a+)+$"    ' DO NOT REUSE THIS PATTERN.
      Dim rgx As New Regex(pattern, RegexOptions.IgnoreCase, TimeSpan.FromSeconds(1))       
      Dim sw As Stopwatch = Nothing

      Dim inputs() As String = { "aa", "aaaa>", 
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa",
                                 "aaaaaaaaaaaaaaaaaaaaaa>",
                                 "aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>" }

      For Each inputValue In inputs
         Console.WriteLine("Processing {0}", inputValue)
         Dim timedOut As Boolean = False
         Do 
            Try
               sw = Stopwatch.StartNew()
               ' Display the result.
               If rgx.IsMatch(inputValue) Then
                  sw.Stop()
                  Console.WriteLine("Valid: '{0}' ({1:ss\.fffffff} seconds)", 
                                    inputValue, sw.Elapsed) 
               Else
                  sw.Stop()
                  Console.WriteLine("'{0}' is not a valid string. ({1:ss\.fffff} seconds)", 
                                    inputValue, sw.Elapsed)
               End If
            Catch e As RegexMatchTimeoutException   
               sw.Stop()
               ' Display the elapsed time until the exception.
               Console.WriteLine("Timeout with '{0}' after {1:ss\.fffff}", 
                                 inputValue, sw.Elapsed)
               Thread.Sleep(1500)       ' Pause for 1.5 seconds.

               ' Increase the timeout interval and retry.
               Dim timeout As TimeSpan = e.MatchTimeout.Add(TimeSpan.FromSeconds(1))
               If timeout.TotalSeconds > MaxTimeoutInSeconds Then
                  Console.WriteLine("Maximum timeout interval of {0} seconds exceeded.",
                                    MaxTimeoutInSeconds)
                  timedOut = False
               Else                
                  Console.WriteLine("Changing the timeout interval to {0}", 
                                    timeout) 
                  rgx = New Regex(pattern, RegexOptions.IgnoreCase, timeout)
                  timedOut = True
               End If
            End Try
         Loop While timedOut
         Console.WriteLine()
      Next   
   End Sub 
End Module
' The example displays output like the following:
'    Processing aa
'    Valid: 'aa' (00.0000779 seconds)
'    
'    Processing aaaa>
'    'aaaa>' is not a valid string. (00.00005 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
'    Valid: 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa' (00.0000043 seconds)
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 01.00469
'    Changing the timeout interval to 00:00:02
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 02.01202
'    Changing the timeout interval to 00:00:03
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaa>' after 03.01043
'    Maximum timeout interval of 3 seconds exceeded.
'    
'    Processing aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>
'    Timeout with 'aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa>' after 03.01018
'    Maximum timeout interval of 3 seconds exceeded.
```

### <a name="nonbacktracking-subexpression"></a>Nicht zurückverfolgender Teilausdruck

Das Sprachelement **(?>** _Teilausdruck_**)** unterdrückt die Rückverfolgung in einem Teilausdruck. Das Element ist nützlich, um die mit fehlgeschlagenen Übereinstimmungen zusammenhängenden Leistungsprobleme zu vermeiden. 

Das folgende Beispiel zeigt, wie das Unterdrücken der Rückverfolgung bei Verwendung von geschachtelten Quantifizierern die Leistung verbessert. Es wird gemessen, wie viel Zeit das Modul für reguläre Ausdrücke benötigt, um zu ermitteln, dass eine Eingabezeichenfolge nicht mit zwei regulären Ausdrücken übereinstimmt. Der erste reguläre Ausdruck verwendet die Rückverfolgung, um eine Übereinstimmung mit einer Zeichenfolge zu finden, in der Folgendes ein Mal oder mehrmals vorkommt: eine oder mehrere hexadezimale Ziffern, gefolgt von einem Doppelpunkt, gefolgt von einer oder mehreren hexadezimalen Ziffern, gefolgt von zwei Doppelpunkten. Der zweite reguläre Ausdruck ist mit dem ersten identisch, mit der Ausnahme, dass dieser die Rückverfolgung deaktiviert. Wie die Ausgabe im Beispiel zeigt, ist die Leistungsverbesserung durch das Deaktivieren der Rückverfolgung signifikant.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:";
      bool matched;
      Stopwatch sw;

      Console.WriteLine("With backtracking:");
      string backPattern = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, backPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed);
      Console.WriteLine();

      Console.WriteLine("Without backtracking:");
      string noBackPattern = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$";
      sw = Stopwatch.StartNew();
      matched = Regex.IsMatch(input, noBackPattern);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed);
   }
}
// The example displays output like the following:
//       With backtracking:
//       Match: False in 00:00:27.4282019
//       
//       Without backtracking:
//       Match: False in 00:00:00.0001391
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "b51:4:1DB:9EE1:5:27d60:f44:D4:cd:E:5:0A5:4a:D24:41Ad:"
      Dim matched As Boolean
      Dim sw As Stopwatch

      Console.WriteLine("With backtracking:")
      Dim backPattern As String = "^(([0-9a-fA-F]{1,4}:)*([0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, backPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, backPattern), sw.Elapsed)
      Console.WriteLine()

      Console.WriteLine("Without backtracking:")
      Dim noBackPattern As String = "^((?>[0-9a-fA-F]{1,4}:)*(?>[0-9a-fA-F]{1,4}))*(::)$"
      sw = Stopwatch.StartNew()
      matched = Regex.IsMatch(input, noBackPattern)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", Regex.IsMatch(input, noBackPattern), sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       With backtracking:
'       Match: False in 00:00:27.4282019
'       
'       Without backtracking:
'       Match: False in 00:00:00.0001391
```

### <a name="lookbehind-assertions"></a>Lookbehindassertionen

.NET enthält zwei Sprachelemente, **(?<**=_Teilausdruck_**)** und **(?<!**_Teilausdruck_**)**, die mit dem bzw. den vorherigen Zeichen in der Eingabezeichenfolge übereinstimmen. Beide Sprachelemente sind Assertionen mit einer Breite von&0;. D.h., sie bestimmen ohne Vorlaufen oder Rückverfolgung, ob eine Übereinstimmung des oder der Zeichen unmittelbar vor dem aktuellen Zeichen mit *Teilausdruck* vorliegt. 

**(?<**=_Teilausdruck_**)** ist eine positive Lookbehindassertion. D.h., das oder die Zeichen vor der aktuellen Position muss bzw. müssen mit *Teilausdruck* übereinstimmen. **(?<!**_Teilausdruck_**)** ist eine negative Lookbehindassertion. D.h., das oder die Zeichen vor der aktuellen Position muss bzw. müssen nicht mit *Teilausdruck* übereinstimmen. Positive und negative Lookbehindassertionen sind besonders hilfreich, wenn *Teilausdruck* eine Teilmenge des vorherigen *Teilausdrucks* ist. 

Im folgenden Beispiel werden zwei äquivalente reguläre Ausdrucksmuster verwendet, die den Benutzernamen in einer E-Mail-Adresse überprüfen. Aufgrund übermäßiger Rückverfolgung tritt beim ersten Muster eine schlechte Leistung auf. Das zweite Muster ist eine Änderung des ersten regulären Ausdrucks, indem ein geschachtelter Quantifizierer durch eine positive Lookbehindassertion ersetzt wird. In der Beispielausgabe wird die Ausführungszeit der [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode angezeigt.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      Stopwatch sw;
      string input = "aaaaaaaaaaaaaaaaaaaa";
      bool result;

      string pattern = @"^[0-9A-Z]([-.\w]*[0-9A-Z])?@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed);

      string behindPattern = @"^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed);
   }
}
// The example displays output similar to the following:
//       Match: True in 00:00:00.0017549
//       Match with Lookbehind: True in 00:00:00.0000659
```

```vb
Module Example
   Public Sub Main()
      Dim sw As Stopwatch
      Dim input As String = "aaaaaaaaaaaaaaaaaaaa"
      Dim result As Boolean

      Dim pattern As String = "^[0-9A-Z]([-.\w]*[0-9A-Z])?@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match: {0} in {1}", result, sw.Elapsed)

      Dim behindPattern As String = "^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, behindPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("Match with Lookbehind: {0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays output similar to the following:
'       Match: True in 00:00:00.0017549
'       Match with Lookbehind: True in 00:00:00.0000659
```

Das Muster des ersten regulären Ausdrucks, `^[0-9A-Z]([-.\w]*[0-9A-Z])*@, is defined as shown in the following table.`

Muster | Beschreibung
------- | ----------- 
`^` | Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.
`[0-9A-Z]` | Übereinstimmung mit einem alphanumerischen Zeichen. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit der [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option aufgerufen wird.
`[-.\w]*` | Übereinstimmung mit keinem, einem oder mehreren Vorkommen eines Bindestrichs, eines Punkts oder eines Wortzeichens. 
`[0-9A-Z]` | Übereinstimmung mit einem alphanumerischen Zeichen. 
`([-.\w]*[0-9A-Z])*` | Übereinstimmung mit keinem oder mehreren Vorkommen der Kombination aus keinem oder mehreren Bindestrichen, Punkten oder Wortzeichen, gefolgt von einem alphanumerischen Zeichen. Dies ist die erste Erfassungsgruppe.
`@` | Übereinstimmung mit einem @-Zeichen.
 
Das zweite Muster für reguläre Ausdrücke `^[0-9A-Z][-.\w]*(?<=[0-9A-Z])@` verwendet eine positive Lookbehindassertion. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`^` | Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.
`[0-9A-Z]` | Übereinstimmung mit einem alphanumerischen Zeichen. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit der [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option aufgerufen wird.
`[-.\w]*` | Übereinstimmung mit keinem oder mehreren Vorkommen eines Bindestrichs, eines Punkts oder eines Wortzeichens.
`(?<=[0-9A-Z])` | Überprüfung des letzten übereinstimmenden Zeichens und Fortsetzen des Abgleichs, wenn es sich um ein alphanumerisches Zeichen handelt. Beachten Sie, dass alphanumerische Zeichen eine Teilmenge des Satzes sind, der aus Punkten, Bindestrichen und allen Wortzeichen besteht.
`@` | Übereinstimmung mit einem @-Zeichen.
 
### <a name="lookahead-assertions"></a>Lookaheadassertionen

.NET enthält zwei Sprachelemente, **(?**=_Teilausdruck_**)** und **(?!**_Teilausdruck_**)**, die mit dem bzw. den nächsten Zeichen in der Eingabezeichenfolge übereinstimmen. Beide Sprachelemente sind Assertionen mit einer Breite von&0;, d.h., sie bestimmen ohne Vorlaufen oder Rückverfolgung, ob eine Übereinstimmung des oder der Zeichen unmittelbar nach dem aktuellen Zeichen mit *Teilausdruck* vorliegt. 

**(?**=_Teilausdruck_**)** ist eine positive Lookaheadassertion. D.h., das oder die Zeichen nach der aktuellen Position muss bzw. müssen mit *Teilausdruck* übereinstimmen. **(?!**_Teilausdruck_**)** ist eine negative Lookaheadassertion. D.h., das oder die Zeichen nach der aktuellen Position muss bzw. müssen nicht mit *Teilausdruck* übereinstimmen. Positive und negative Lookaheadassertionen sind besonders hilfreich, wenn *Teilausdruck* eine Teilmenge des nächsten *Teilausdrucks* ist. 

Im folgenden Beispiel werden zwei äquivalente Muster für reguläre Ausdrücke verwendet, die einen vollqualifizierten Typnamen überprüfen. Aufgrund übermäßiger Rückverfolgung tritt beim ersten Muster eine schlechte Leistung auf. Das zweite Muster ist eine Änderung des ersten regulären Ausdrucks, indem ein geschachtelter Quantifizierer durch eine positive Lookaheadassertion ersetzt wird. In der Beispielausgabe wird die Ausführungszeit der [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode angezeigt.

```csharp
using System;
using System.Diagnostics;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string input = "aaaaaaaaaaaaaaaaaaaaaa.";
      bool result;
      Stopwatch sw;

      string pattern = @"^(([A-Z]\w*)+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);

      string aheadPattern = @"^((?=[A-Z])\w+\.)*[A-Z]\w*$";
      sw = Stopwatch.StartNew();
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase);
      sw.Stop();
      Console.WriteLine("{0} in {1}", result, sw.Elapsed);
   }
}
// The example displays the following output:
//       False in 00:00:03.8003793
//       False in 00:00:00.0000866
```

```vb
Imports System.Diagnostics
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim input As String = "aaaaaaaaaaaaaaaaaaaaaa."
      Dim result As Boolean
      Dim sw As Stopwatch

      Dim pattern As String = "^(([A-Z]\w*)+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, pattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)

      Dim aheadPattern As String = "^((?=[A-Z])\w+\.)*[A-Z]\w*$"
      sw = Stopwatch.StartNew()
      result = Regex.IsMatch(input, aheadPattern, RegexOptions.IgnoreCase)
      sw.Stop()
      Console.WriteLine("{0} in {1}", result, sw.Elapsed)
   End Sub
End Module
' The example displays the following output:
'       False in 00:00:03.8003793
'       False in 00:00:00.0000866
```

Das erste Muster für reguläre Ausdrücke `^(([A-Z]\w*)+\.)*[A-Z]\w*$` ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`^` | Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.
`([A-Z]\w*)+\.` | Übereinstimmung mit einem Buchstaben (A-Z), gefolgt von keinem oder mehreren Wortzeichen (einmaliges oder mehrmaliges Vorkommen), gefolgt von einem Punkt. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit der [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option aufgerufen wird.
`(([A-Z]\w*)+\.)*` | Keine oder mehrmalige Übereinstimmung mit dem vorherigen Muster. 
`[A-Z]\w*` | Übereinstimmung mit einem Buchstaben, gefolgt von keinem oder mehreren Wortzeichen.
`$` | Ende des Abgleichs am Ende der Eingabezeichenfolge.
 

Das zweite Muster für reguläre Ausdrücke `^((?=[A-Z])\w+\.)*[A-Z]\w*$` verwendet eine positive Lookaheadassertion. Das Muster wird wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`^` | Die Suche nach Übereinstimmungen soll am Anfang der Zeichenfolge beginnen.
`(?=[A-Z])` | Lookahead zum ersten Zeichen und die Suche nach Übereinstimmungen fortsetzen, wenn es sich um einen Buchstaben (A-Z) handelt. Bei diesem Vergleich wird die Groß-/Kleinschreibung nicht beachtet, da die [Regex.IsMatch](xref:System.Text.RegularExpressions.Regex.IsMatch(System.String,System.String,System.Text.RegularExpressions.RegexOptions))-Methode mit der [RegexOptions.IgnoreCase](xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase)-Option aufgerufen wird.
`\w+\.` | Übereinstimmung mit einem oder mehreren Wortzeichen, gefolgt von einem Punkt.
`((?=[A-Z])\w+\.)*` | Übereinstimmung mit dem Muster aus einem oder mehreren Wortzeichen, gefolgt von keinem oder mehreren Vorkommen eines Punkts. Das erste Wortzeichen muss ein Buchstabe sein. 
`[A-Z]\w*` | Übereinstimmung mit einem Buchstaben, gefolgt von keinem oder mehreren Wortzeichen.
`$` | Ende des Abgleichs am Ende der Eingabezeichenfolge.
 
## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)

[Quantifizierer in regulären Ausdrücken](quantifiers.md)

[Alternierungskonstrukte in regulären Ausdrücken](alternation.md)

[Gruppierungskonstrukte in regulären Ausdrücken](grouping.md)


