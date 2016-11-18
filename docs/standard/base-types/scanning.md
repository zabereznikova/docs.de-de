---
title: "Beispiel für reguläre Ausdrücke: Suchen nach HREFs"
description: "Beispiel für reguläre Ausdrücke: Suchen nach HREFs"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d6484880-bdac-47cd-b5e5-9419c9ed14cd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 494ceeb2cc3bbf77098d2b6145690e7229ed3b9f

---

# <a name="regular-expression-example-scanning-for-hrefs"></a>Beispiel für reguläre Ausdrücke: Suchen nach HREFs

Im folgenden Beispiel wird eine Eingabezeichenfolge durchsucht, und es werden alle href="..."-Werte und ihre Positionen in der Zeichenfolge angezeigt. 

## <a name="the-regex-object"></a>Das Regex-Objekt

Da die `DumpHRefs`-Methode vom Benutzercode aus mehrmals aufgerufen werden kann, verwendet sie die `static`-Methode [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). Dies ermöglicht dem Modul für reguläre Ausdrücke, den regulären Ausdruck zwischenzuspeichern, und vermeidet den zusätzlichen Aufwand, bei jedem Aufruf der Methode ein neues [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt zu instanziieren. Ein [Match](xref:System.Text.RegularExpressions.Match)-Objekt wird anschließend verwendet, um alle Übereinstimmungen in der Zeichenfolge zu durchlaufen. 

```csharp
private static void DumpHRefs(string inputString) 
{
   Match m;
   string HRefPattern = "href\\s*=\\s*(?:[\"'](?<1>[^\"']*)[\"']|(?<1>\\S+))";

   try {
      m = Regex.Match(inputString, HRefPattern, 
                      RegexOptions.IgnoreCase | RegexOptions.Compiled, 
                      TimeSpan.FromSeconds(1));
      while (m.Success)
      {
         Console.WriteLine("Found href " + m.Groups[1] + " at " 
            + m.Groups[1].Index);
         m = m.NextMatch();
      }   
   }
   catch (RegexMatchTimeoutException) {
      Console.WriteLine("The matching operation timed out.");
   }
}
```

```vb
Private Sub DumpHRefs(inputString As String) 
   Dim m As Match
   Dim HRefPattern As String = "href\s*=\s*(?:[""'](?<1>[^""']*)[""']|(?<1>\S+))"

   Try
      m = Regex.Match(inputString, HRefPattern, _ 
                      RegexOptions.IgnoreCase Or RegexOptions.Compiled,
                      TimeSpan.FromSeconds(1))
      Do While m.Success
         Console.WriteLine("Found href {0} at {1}.", _
                           m.Groups(1), m.Groups(1).Index)
         m = m.NextMatch()
      Loop   
   Catch e As RegexMatchTimeoutException
      Console.WriteLine("The matching operation timed out.")
   End Try
End Sub
```

Im folgenden Beispiel wird ein Aufruf der `DumpHRefs`-Methode veranschaulicht.

```csharp
public static void Main()
{
   string inputString = "My favorite web sites include:</P>" +
                        "<A HREF=\"http://msdn2.microsoft.com\">" +
                        "MSDN Home Page</A></P>" +
                        "<A HREF=\"http://www.microsoft.com\">" +
                        "Microsoft Corporation Home Page</A></P>" +
                        "<A HREF=\"http://blogs.msdn.com/bclteam\">" +
                        ".NET Base Class Library blog</A></P>";
   DumpHRefs(inputString);                     

}
// The example displays the following output:
//       Found href http://msdn2.microsoft.com at 43
//       Found href http://www.microsoft.com at 102
//       Found href http://blogs.msdn.com/bclteam at 176
```

```vb
Public Sub Main()
   Dim inputString As String = "My favorite web sites include:</P>" & _
                               "<A HREF=""http://msdn2.microsoft.com"">" & _
                               "MSDN Home Page</A></P>" & _
                               "<A HREF=""http://www.microsoft.com"">" & _
                               "Microsoft Corporation Home Page</A></P>" & _
                               "<A HREF=""http://blogs.msdn.com/bclteam"">" & _
                               ".NET Base Class Library blog</A></P>"
   DumpHRefs(inputString)                     
End Sub
' The example displays the following output:
'       Found href http://msdn2.microsoft.com at 43
'       Found href http://www.microsoft.com at 102
'       Found href http://blogs.msdn.com/bclteam/) at 176
```

Das Muster für reguläre Ausdrücke `href\s*=\s*(?:["']&#40;?<1>[^"']*)["']|(?<1>\S+))` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | ----------- 
`href` | Sucht nach der Literalzeichenfolge „href“. Die Groß- und Kleinschreibung wird bei der Übereinstimmung nicht berücksichtigt.
`\s*` | Sucht nach 0 (null) oder mehr Leerzeichen.
`=` |Sucht nach dem Gleichheitszeichen.
`\s*` | Sucht nach 0 (null) oder mehr Leerzeichen.
`(?:["']&#40;?<1>[^"']*)"&#124;(?<1>\S+))` | Sucht nach einer der folgenden Zeichenkombinationen, ohne das Ergebnis einer erfassten Gruppe zuzuweisen: Ein Anführungszeichen oder Apostroph, gefolgt von null oder mehr Vorkommen eines beliebigen anderen Zeichens als einem Anführungszeichen oder Apostroph, gefolgt von einem Anführungszeichen oder einem Apostroph. Die Gruppe namens `1` ist in diesem Muster enthalten. – oder – Ein oder mehr Nicht-Leerzeichen. Die Gruppe namens `1` ist in diesem Muster enthalten.
`(?<1>[^"']*)` | Weist der Erfassungsgruppe namens `1` null oder mehr Vorkommen eines beliebigen Zeichens außer Anführungszeichen oder Apostroph zu.
`"(?<1>\S+)` | Weist der Erfassungsgruppe namens `1` ein oder mehr Nicht-Leerzeichen zu.
 
## <a name="match-result-class"></a>Abgleichsergebnisklasse

Die Ergebnisse einer Suche werden in der [Match](xref:System.Text.RegularExpressions.Match)-Klasse gespeichert, die Zugriff auf alle von der Suche extrahierten Teilzeichenfolgen bietet. Die durchsuchte Zeichenfolge und der verwendete reguläre Ausdruck werden ebenfalls gespeichert, sodass die [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch)-Methode aufgerufen werden kann, um einen weiteren Suchvorgang ab der Stelle auszuführen, an der der letzte Suchvorgang beendet wurde.

## <a name="explicitly-named-captures"></a>Explizit benannte Erfassungen

In herkömmlichen regulären Ausdrücken werden Klammern für die Erfassung automatisch nach der Reihenfolge durchnummeriert. Daraus ergeben sich zwei Probleme. Zum einen muss nach dem Einfügen oder Entfernen von Klammern jeglicher Code, der auf die nummerierten Klammern verweist, der neuen Nummerierung entsprechend umgeschrieben werden. Zweitens werden häufig unterschiedliche Klammerpaare verwendet, um zwei Alternativausdrücke für eine Übereinstimmung zu erhalten. Dadurch wird es schwierig festzustellen, durch welchen der beiden Ausdrücke das Ergebnis zurückgegeben wurde.

Um diesen Schwierigkeiten zu begegnen, unterstützt die [Regex](xref:System.Text.RegularExpressions.Regex)-Klasse die `(?<name>…)`-Syntax zur Erfassung einer Übereinstimmung in einem festgelegten Slot. (Der Slot kann mit einer Zeichenfolge oder einer ganzen Zahl benannt werden; ganze Zahlen können schneller aufgerufen werden.) Damit können alle Suchergebnisse für dieselbe Zeichenfolge an denselben Ort geleitet werden. Im Fall eines Konflikts ist das zuletzt im Slot gespeicherte Suchergebnis gültig. (Eine vollständige Liste mehrerer Übereinstimmungen für einen einzelnen Slot steht jedoch zur Verfügung. Ausführliche Informationen finden Sie in der [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures)-Sammlung.)

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)

[Beispiele für reguläre Ausdrücke](regex-examples.md)




<!--HONumber=Nov16_HO3-->


