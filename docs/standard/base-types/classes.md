---
title: "Zeichenklassen in regulären Ausdrücken"
description: "Zeichenklassen in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c7a9305f-7144-4fe8-80e8-a727bf7d223f
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: f8ebb1db670669e2e8666cd5ef90f72237c105e4

---

# <a name="character-classes-in-regular-expressions"></a>Zeichenklassen in regulären Ausdrücken

Eine Zeichenklasse definiert einen Satz von Zeichen, von denen jedes in einer Eingabezeichenfolge enthalten sein kann, damit eine Übereinstimmung vorliegt. Die Sprache für reguläre Ausdrücke in .NET unterstützt die folgenden Zeichenklassen:

* Positive Zeichengruppen. Ein Zeichen in der Eingabezeichenfolge muss mit einem Zeichen in einem angegebenen Zeichensatz übereinstimmen. Weitere Informationen finden Sie unter [Positive Zeichengruppe](#positive-character-group--).

* Negative Zeichengruppen. Ein Zeichen in der Eingabezeichenfolge darf nicht mit einem Zeichen in einem angegebenen Zeichensatz übereinstimmen. Weitere Informationen finden Sie unter [Negative Zeichengruppe](#negative-character-group-).

* Jedes Zeichen. Die  .-Zeichen (Punkt) in einem regulären Ausdruck ist ein Platzhalterzeichen, das mit Ausnahme von **\n** mit jedem Zeichen übereinstimmt. Weitere Informationen finden Sie unter [Alle Zeichen](#any-character-). 

* Eine allgemeine Unicode-Kategorie oder ein benannter Block. Ein Zeichen in der Eingabezeichenfolge muss einer bestimmten Unicode-Kategorie oder einem zusammenhängenden Bereich von Unicode-Zeichen angehören, damit eine Übereinstimmung vorliegt. Weitere Informationen finden Sie unter [Unicode-Kategorie oder Unicode-Block](#unicode-category-or-unicode-block-p).

* Eine negative allgemeine Unicode-Kategorie oder ein benannter Block. Ein Zeichen in der Eingabezeichenfolge darf weder einer bestimmten Unicode-Kategorie noch einem zusammenhängenden Bereich von Unicode-Zeichen angehören, damit eine Übereinstimmung vorliegt. Weitere Informationen finden Sie unter [Negative Unicode-Kategorie oder negativer Unicode-Block](#negative-unicode-category-or-unicode-block-p).

* Ein Wortzeichen. Ein Zeichen in der Eingabezeichenfolge kann allen Unicode-Kategorien angehören, die für Zeichen in Wörtern geeignet sind. Weitere Informationen finden Sie unter [Wortzeichen](#word-character-w).

* Ein Nicht-Wortzeichen. Ein Zeichen in der Eingabezeichenfolge kann jeder Unicode-Kategorie angehören, bei der es sich nicht um ein Wortzeichen handelt. Weitere Informationen finden Sie unter [Nicht-Wortzeichen](#non-word-character-w).

* Ein Leerzeichen. Ein Zeichen in der Eingabezeichenfolge kann sowohl jedes Unicode-Trennzeichen als auch jedes Zeichen aus einer Anzahl von Steuerzeichen sein. Weitere Informationen finden Sie unter [Leerzeichen](#white-space-character-s).

* Ein Nicht-Leerzeichen. Ein Zeichen in der Eingabezeichenfolge kann jedes Nicht-Leerzeichen sein. Weitere Informationen finden Sie unter [Nicht-Leerzeichen](#non-white-space-character-s).

* Eine Dezimalzahl. Ein Zeichen in der Eingabezeichenfolge kann jedes als Unicode-Dezimalzeichen klassifiziertes Zeichen sein. Weitere Informationen finden Sie unter [Dezimalzeichen](#decimal-digit-character-d).

* Ein Nicht-Dezimalzeichen. Ein Zeichen in der Eingabezeichenfolge kann mit Ausnahme von Unicode-Dezimalzeichen jedes Zeichen sein. Weitere Informationen finden Sie unter [Nicht-Zahlen](#non-digit-character-d).


.NET unterstützt Zeichenklassensubtraktions-Ausdrücke. Hierdurch können Sie einen Zeichensatz definieren, der das Ergebnis des Ausschlusses einer Zeichenklasse von einer anderen darstellt. Weitere Informationen finden Sie unter [Zeichenklassensubtraktion](#character-class-subtraction).

## <a name="positive-character-group-"></a>Positive Zeichengruppe: [ ]

In einer positiven Zeichengruppe wird eine Liste von Zeichen festgelegt. Wenn eine Eingabezeichenfolge eines dieser Zeichen aufweist, liegt eine Übereinstimmung vor. Diese Zeichenliste kann einzeln, als Bereich oder beides angegeben werden. 

Die Syntax zum Angeben einer Liste einzelner Zeichen lautet wie folgt: 

[*Zeichen*_*Gruppe*]

wobei *Zeichen_Gruppe* eine Liste der einzelnen Zeichen ist, die in der Eingabezeichenfolge vorkommen können, damit eine Übereinstimmung vorliegt. *Zeichen*_*Gruppe* kann aus einer beliebigen Kombination von mindestens einem Literalzeichen, [Escapezeichen](escapes.md) oder Zeichenklassen bestehen. 

Die Syntax zum Angeben eines Zeichenbereichs lautet wie folgt:

```
[firstCharacter-lastCharacter]
```

wobei *firstCharacter* das Zeichen ist, mit dem der Bereich beginnt, und *lastCharacter* das Zeichen, mit dem der Bereich endet. Ein Zeichenbereich besteht aus einer Reihe zusammenhängender Zeichen, der durch Angabe des ersten Zeichens der Reihe, eines Bindestrichs (-) und des letzten Zeichens in der Reihe definiert wird. Zwei Zeichen sind zusammenhängend, wenn sie benachbarte Unicode-Codepunkte aufweisen.

In der folgenden Tabelle werden einige allgemeine Muster für reguläre Ausdrücke mit positiven Zeichenklassen aufgeführt.

Muster | Beschreibung
------- | ----------- 
`[aeiou]` | Übereinstimmung mit allen Vokalen.
`[\p{P}\d]` | Übereinstimmung mit allen Interpunktions- und Dezimalzeichen.
`[\s\p{P}]` | Übereinstimmung mit allen Leerzeichen und Interpunktionszeichen.
 
Im folgenden Beispiel wird eine positive Zeichengruppe mit den Zeichen "a" und "e" definiert. Die Eingabezeichenfolge muss daher die Wörter "grey" oder "gray" (zwei gültige Schreibweisen für die englische Form von "grau") gefolgt von einem anderen Wort aufweisen, damit eine Übereinstimmung vorliegt.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"gr[ae]y\s\S+?[\s\p{P}]";
      string input = "The gray wolf jumped over the grey wall.";
      MatchCollection matches = Regex.Matches(input, pattern);
      foreach (Match match in matches)
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       gray wolf
//       grey wall.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "gr[ae]y\s\S+?[\s\p{P}]"
      Dim input As String = "The gray wolf jumped over the grey wall."
      Dim matches As MatchCollection = Regex.Matches(input, pattern)
      For Each match As Match In matches
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       gray wolf
'       grey wall.
```

Der reguläre Ausdruck `gr[ae]y\s\S+?[\s|\p{P}]` ist wie folgt definiert:

Muster | Beschreibung
------- | ----------- 
`gr` | Übereinstimmung mit den Literalzeichen"gr".
`[ae]` | Übereinstimmung mit entweder "a" oder "e".
`y\s` | Übereinstimmung mit dem Literalzeichen "y" gefolgt von einem Leerzeichen.
`\S+?` | Übereinstimmung mit mindestens einem, jedoch möglichst wenigen Nicht-Leerzeichen.
`[\s\p{P}]` | Übereinstimmung mit entweder einem Leerzeichen oder einem Interpunktionszeichen.
 
Im folgenden Beispiel liegen Übereinstimmungen mit Wörtern vor, die mit einem die oft ausgegebene Befehlszeilen  Großbuchstaben beginnen. Der Großbuchstabenbereich von A bis Z wird durch den `[A-Z]`-Unterausdruck dargestellt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b[A-Z]\w*\b";
      string input = "A city Albany Zulu maritime Marseilles";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       A
//       Albany
//       Zulu
//       Marseilles
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b[A-Z]\w*\b"
      Dim input As String = "A city Albany Zulu maritime Marseilles"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
```

Der reguläre Ausdruck `\b[A-Z]\w*\b` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`[A-Z]` | Übereinstimmung mit einem die oft ausgegebene Befehlszeilen  Großbuchstaben von A bis Z.
`\w*` | Übereinstimmung mit keinem oder mehreren Wortzeichen.
`\b` | Übereinstimmung mit einer Wortgrenze.

## <a name="negative-character-group-"></a>Negative Zeichengruppe: [^]

In einer negativen Zeichengruppe wird eine Liste von Zeichen festgelegt. Eine Eingabezeichenfolge darf keines dieser Zeichen aufweisen, damit eine Übereinstimmung vorliegt. Die Zeichenliste kann einzeln, als Bereich oder beides angegeben werden. 

Die Syntax zum Angeben einer Liste einzelner Zeichen lautet wie folgt:

[^*Zeichen*_*Gruppe*]

wobei *Zeichen_Gruppe* eine Liste der einzelnen Zeichen ist, die in der Eingabezeichenfolge nicht vorkommen können, damit eine Übereinstimmung vorliegt. *Zeichen*_*Gruppe* kann aus einer beliebigen Kombination von mindestens einem Literalzeichen, [Escapezeichen](escapes.md) oder Zeichenklassen bestehen. 

Die Syntax zum Angeben eines Zeichenbereichs lautet wie folgt:

[^*erstesZeichen-letztesZeichen*]

wobei *erstesZeichen* das Zeichen ist, mit dem der Bereich beginnt, und *letztesZeichen* das Zeichen, mit dem der Bereich endet. Ein Zeichenbereich besteht aus einer Reihe zusammenhängender Zeichen, der durch Angabe des ersten Zeichens der Reihe, eines Bindestrichs (-) und des letzten Zeichens in der Reihe definiert wird. Zwei Zeichen sind zusammenhängend, wenn sie benachbarte Unicode-Codepunkte aufweisen.

Mindestens zwei Zeichenbereiche können miteinander verkettet werden. Beispiel: Verwenden Sie zum Angeben des Dezimalzeichenbereichs von "0" bis "9", des Kleinbuchstabenbereichs von "a" bis "f" und des Großbuchstabenbereichs von "A" bis "F" den Ausdruck `[0-9a-fA-F]`.

Das Zirkumflexzeichen (^) am Anfang einer negativen Zeichengruppe ist obligatorisch und gibt an, dass es sich um eine negative anstelle einer positiven Zeichengruppe handelt.

> [!IMPORTANT]
> Bei einer negativen Zeichengruppe in einem größeren Muster eines regulären Ausdrucks handelt es sich nicht um eine Assertion mit einer Breite von Null. Dies bedeutet, dass nach dem Auswerten der negativen Zeichengruppe das Modul für reguläre Ausdrücke in der Eingabezeichenfolge zum nachfolgenden Zeichen übergeht.

In der folgenden Tabelle werden einige allgemeine Muster für reguläre Ausdrücke mit negativen Zeichengruppen aufgeführt.

Muster | Beschreibung
------- | ----------- 
`[^aeiou]` | Übereinstimmung mit allen Zeichen mit Ausnahme von Vokalen.
`[^\p{P}\d]` | Übereinstimmung mit allen Zeichen mit Ausnahme von Interpunktions- und Dezimalzeichen.
 
Im folgenden Beispiel werden Übereinstimmungen für alle Wörter dargestellt, die mit den Zeichen "th" beginnen, wobei darauf kein "o" folgt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\bth[^o]\w+\b";
      string input = "thought thing though them through thus thorough this";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       thing
//       them
//       through
//       thus
//       this
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\bth[^o]\w+\b"
      Dim input As String = "thought thing though them through thus " + _
                            "thorough this"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       thing
'       them
'       through
'       thus
'       this
```

Der reguläre Ausdruck `\bth[^o]\w+\b` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`th` | Übereinstimmung mit den Literalzeichen"th".
`[^o]` | Übereinstimmung mit allen Zeichen außer "o".
`\w+` | Übereinstimmung mit mindestens einem Wortzeichen.
`\b` | An einer Wortgrenze beenden.

## <a name="any-character-"></a>Alle Zeichen: .

Das Punktzeichen (.) stimmt mit Ausnahme von **\n** (dem Zeichen für einen Zeilenumbruch, **\u000A**) mit allen Zeichen überein. Hierfür gelten die folgenden beiden Qualifikationen:

* Wenn ein Muster für reguläre Ausdrücke durch die Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) geändert wird oder wenn der Teil des Musters mit der .-Zeichenklasse durch die **s**-Option geändert wird,  stimmt „.“ mit allen Zeichen überein. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](options.md).

  Das folgende Beispiel veranschaulicht das unterschiedliche Verhalten der  .-Zeichenklasse im Standardfall und mit der Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline). Der reguläre `^.+`-Ausdruck beginnt am Anfang der Zeichenfolge und stimmt mit jedem Zeichen überein. Standardmäßig endet die Übereinstimmung am Ende der ersten Zeile. Das Muster für den regulären Ausdruck stimmt mit dem Wagenrücklaufzeichen (**\r** oder **\u000D**), jedoch nicht mit **\n** überein. Da die gesamte Eingabezeichenfolge von der Option [RegexOptions.Singleline](xref:System.Text.RegularExpressions.RegexOptions.Singleline) als einzelne Zeile interpretiert wird, wird für jedes enthaltene Zeichen ein Abgleich vorgenommen, einschließlich **\n**.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = "^.+";
        string input = "This is one line and" + Environment.NewLine + "this is the second.";
        foreach (Match match in Regex.Matches(input, pattern))
           Console.WriteLine(Regex.Escape(match.Value));

        Console.WriteLine();
        foreach (Match match in Regex.Matches(input, pattern, RegexOptions.Singleline))
           Console.WriteLine(Regex.Escape(match.Value));
     }
  }
  // The example displays the following output:
  //       This\ is\ one\ line\ and\r
  //       
  //       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As String = "^.+"
        Dim input As String = "This is one line and" + vbCrLf + "this is the second."
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine(Regex.Escape(match.Value))
        Next
        Console.WriteLine()
        For Each match As Match In Regex.Matches(input, pattern, RegexOptions.SingleLine)
           Console.WriteLine(Regex.Escape(match.Value))
        Next
     End Sub
  End Module
  ' The example displays the following output:
  '       This\ is\ one\ line\ and\r
  '       
  '       This\ is\ one\ line\ and\r\nthis\ is\ the\ second\.
  ```

  > [!NOTE]
  > Da sie mit jedem Zeichen außer **\n** übereinstimmt, stimmt die  .-Zeichenklasse auch mit **\r** überein (Wagenrücklaufzeichen, **\u000D**).
 
* In einer positiven oder negativen Zeichengruppe wird ein Punkt anstatt einer Zeichenklasse als Literalzeichen behandelt. Weitere Informationen finden Sie weiter oben in diesem Thema unter [Positive Zeichengruppe](#positive-character-group--) und [Negative Zeichengruppe](#negative-character-group-). Im folgenden Beispiel wird zur Veranschaulichung ein regulärer Ausdruck definiert, der das Punktzeichen (**.**) sowohl als Zeichenklasse als auch als Mitglied einer positiven Zeichengruppe aufweist. Der reguläre Ausdruck `\b.*[.?!;:](\s|\z)` beginnt an einer Wortgrenze und stimmt bis zum Erreichen eines von vier Interpunktionszeichen (einschließlich eines Punkts) mit jedem Zeichen überein. Anschließend liegt entweder eine Übereinstimmung mit einem Leerzeichen oder dem Ende der Zeichenfolge vor.

  ```csharp
  using System;
  using System.Text.RegularExpressions;

  public class Example
  {
     public static void Main()
     {
        string pattern = @"\b.*[.?!;:](\s|\z)";
        string input = "this. what: is? go, thing.";
        foreach (Match match in Regex.Matches(input, pattern))
           Console.WriteLine(match.Value);
     }
  }
  // The example displays the following output:
  //       this. what: is? go, thing.
  ```

  ```vb
  Imports System.Text.RegularExpressions

  Module Example
     Public Sub Main()
        Dim pattern As STring = "\b.*[.?!;:](\s|\z)"
        Dim input As String = "this. what: is? go, thing."
        For Each match As Match In Regex.Matches(input, pattern)
           Console.WriteLine(match.Value)
        Next   
     End Sub
  End Module
  ' The example displays the following output:
  '       this. what: is? go, thing.
  ```

  > [!NOTE]
  > Da es mit jedem Zeichen übereinstimmt, wird das  .-Sprachelement häufig mit einem verzögerten Quantifizierer verwendet, wenn von einem Muster für einen regulären Ausdruck mehrere Versuche bezüglich der Übereinstimmung mit einem bestimmten Zeichen ausgeführt werden. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md). 
 
## <a name="unicode-category-or-unicode-block-p"></a>Unicode-Kategorie oder Unicode-Block: \p{}

Jedem Zeichen wird im Unicode-Standard eine allgemeine Kategorie zugewiesen. Beispiel: Bei einem bestimmten Zeichen kann es sich um einen Großbuchstaben (dargestellt durch die **Lu**-Kategorie), ein Dezimalzeichen (die **Nd**-Kategorie), ein mathematisches Symbol (die **Sm**-Kategorie) oder einen Absatzseparator (die **Zl**-Kategorie) handeln. Bestimmte Zeichensätze im Unicode-Standard nehmen auch einen bestimmten Bereich oder einen Block aufeinander folgender Codepunkte ein. Beispielsweise befindet sich der grundlegende lateinische Zeichensatz im Bereich von **\u0000** bis **\u007F**, während der arabische Zeichensatz zwischen **\u0600** und **\u06FF** liegt. 

Konstrukt des regulären Ausdrucks

**\p{**_Name_**}**

Übereinstimmung mit jedem Zeichen, das einer allgemeinen Unicode-Kategorie oder einem benannten Block angehört, wobei „Name“ für die Abkürzung der Kategorie bzw. den Namen des benannten Blocks steht. Eine Liste von Kategorieabkürzungen finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte allgemeine Unicode-Kategorien](#supported-unicode-general-categories). Eine Liste von benannten Blöcken finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte benannte Blöcke](#supported-named-blocks). 

Im folgenden Beispiel wird das **\p{**_Name_**}**-Konstrukt für eine Übereinstimmung mit sowohl einer allgemeinen Unicode-Kategorie (in diesem Fall die **Pd**-Kategorie, oder Interpunktionszeichen und Bindestriche) als auch mit einem benannten Block (den benannten Blöcken **IsGreek** und **IsBasicLatin**) verwendet.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+";
      string input = "?ata ?a??a??? - The Gospel of Matthew";

      Console.WriteLine(Regex.IsMatch(input, pattern));        // Displays True.
   }
}
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+"
      Dim input As String = "Κατα Μαθθαίον - The Gospel of Matthew"

      Console.WriteLine(Regex.IsMatch(input, pattern))         ' Displays True.
   End Sub
End Module
```

Der reguläre Ausdruck `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` wird entsprechend der Darstellung in der folgenden Tabelle definiert:

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`\p{IsGreek}+` | Übereinstimmung mit mindestens einem griechischen Zeichen.
`(\s)?` | Übereinstimmung mit keinem oder einem Leerzeichen.
`(\p{IsGreek}+(\s)?)+` | Übereinstimmung mit dem Muster mindestens eines griechischen Zeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen. 
`\p{Pd}` | Übereinstimmung mit einem Interpunktionszeichen oder Bindestrich.
`\s` | Entsprechung für ein Leerraumzeichen finden.
`\p{IsBasicLatin}+` | Übereinstimmung mit mindestens einem grundlegenden lateinischen Zeichen.
`(\s)?` | Übereinstimmung mit keinem oder einem Leerzeichen.
`(\p{IsBasicLatin}+(\s)?)+` | Übereinstimmung mit dem Muster mindestens eines grundlegenden lateinischen Zeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen.

## <a name="negative-unicode-category-or-unicode-block-p"></a>Negative Unicode-Kategorie oder negativer Unicode-Block: \P{}

Jedem Zeichen wird im Unicode-Standard eine allgemeine Kategorie zugewiesen. Beispiel: Bei einem bestimmten Zeichen kann es sich um einen Großbuchstaben (dargestellt durch die **Lu**-Kategorie), ein Dezimalzeichen (die **Nd**-Kategorie), ein mathematisches Symbol (die **Sm**-Kategorie) oder einen Absatzseparator (die **Zl**-Kategorie) handeln. Bestimmte Zeichensätze im Unicode-Standard nehmen auch einen bestimmten Bereich oder einen Block aufeinander folgender Codepunkte ein. Beispielsweise befindet sich der grundlegende lateinische Zeichensatz im Bereich von **\u0000** bis **\u007F**, während der arabische Zeichensatz zwischen **\u0600** und **\u06FF** liegt. 

Konstrukt des regulären Ausdrucks

**\P{**_Name_**}**

Übereinstimmung mit jedem Zeichen, das einer allgemeinen Unicode-Kategorie oder einem benannten Block angehört, wobei „Name“ für die Abkürzung der Kategorie bzw. den Namen des benannten Blocks steht. Eine Liste von Kategorieabkürzungen finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte allgemeine Unicode-Kategorien](#supported-unicode-general-categories). Eine Liste von benannten Blöcken finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte benannte Blöcke](#supported-named-blocks).

Im folgenden Beispiel wird das **\P{**_Name_**}**-Konstrukt zum Entfernen aller Währungssymbole (in diesem Fall die **Sc**-Kategorie oder Symbole und Währungen) aus numerischen Zeichenfolgen verwendet.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\P{Sc})+";

      string[] values = { "$164,091.78", "£1,073,142.68", "73¢", "€120" };
      foreach (string value in values)
         Console.WriteLine(Regex.Match(value, pattern).Value);
   }
}
// The example displays the following output:
//       164,091.78
//       1,073,142.68
//       73
//       120
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\P{Sc})+"

      Dim values() As String = { "$164,091.78", "£1,073,142.68", "73¢", "€120"}
      For Each value As String In values
         Console.WriteLine(Regex.Match(value, pattern).Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       164,091.78
'       1,073,142.68
'       73
'       120
```

Das Muster für den regulären `(\P{Sc})+`-Ausdruck stimmt mit mindestens einem Zeichen überein, bei dem es sich nicht um ein Währungssymbol handelt. Tatsächlich werden alle Währungssymbole aus der Ergebniszeichenfolge entfernt.

## <a name="word-character-w"></a>Wortzeichen: \w

**\w** stimmt mit jedem Wortzeichen überein. Ein Wortzeichen gehört einer der in der folgenden Tabelle aufgeführten Unicode-Kategorien an. 

Kategorie | Beschreibung
-------- | ----------- 
Ll | Letter, Lowercase (Buchstabe, Kleinschreibung)
Lu | Letter, Uppercase (Buchstabe, Großschreibung)
Lt | Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)
Lo | Letter, Other (Buchstabe, andere)
Lm | Letter, Modifier (Buchstabe, Modifizierer)
Mn | Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)
Nd | Number, Decimal Digit (Zahl, Dezimalzahl)
Pc | Punctuation, Connector (Interpunktion, Konnektor). Zu dieser Kategorie gehören zehn Zeichen, von denen das UNTERSTRICH-Zeichen "u+005F" (_) am häufigsten verwendet wird.
 
Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\w** `[a-zA-Z_0-9]`. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md). 

> [!NOTE]
> Aufgrund der Übereinstimmung des \w-Sprachelements mit jedem Wortzeichen wird es häufig mit einem verzögerten Quantifizierer verwendet, wenn von einem Muster für einen regulären Ausdruck mehrere Versuche bezüglich der Übereinstimmung eines von einem bestimmten Wortzeichen gefolgten Wortzeichens ausgeführt werden. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md).

Im folgenden Beispiel werden mit dem **\w**-Sprachelement übereinstimmende doppelte Zeichen innerhalb eines Worts ermittelt. Im Beispiel wird ein Muster für reguläre Ausdrücke definiert – **(\w)\1** – das wie folgt interpretiert werden kann.

Element | Beschreibung
------- | -----------
(\w) | Übereinstimmung mit einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
\1 | Übereinstimmung mit dem Wert der ersten Erfassung. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"(\w)\1";
      string[] words = { "trellis", "seer", "latter", "summer", 
                         "hoarse", "lesser", "aardvark", "stunned" };
      foreach (string word in words)
      {
         Match match = Regex.Match(word, pattern);
         if (match.Success)
            Console.WriteLine("'{0}' found in '{1}' at position {2}.", 
                              match.Value, word, match.Index);
         else
            Console.WriteLine("No double characters in '{0}'.", word);
      }                                                  
   }
}
// The example displays the following output:
//       'll' found in 'trellis' at position 3.
//       'ee' found in 'seer' at position 1.
//       'tt' found in 'latter' at position 2.
//       'mm' found in 'summer' at position 2.
//       No double characters in 'hoarse'.
//       'ss' found in 'lesser' at position 2.
//       'aa' found in 'aardvark' at position 0.
//       'nn' found in 'stunned' at position 3.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(\w)\1"
      Dim words() As String = { "trellis", "seer", "latter", "summer", _
                                "hoarse", "lesser", "aardvark", "stunned" }
      For Each word As String In words
         Dim match As Match = Regex.Match(word, pattern)
         If match.Success Then
            Console.WriteLine("'{0}' found in '{1}' at position {2}.", _
                              match.Value, word, match.Index)
         Else
            Console.WriteLine("No double characters in '{0}'.", word)
         End If
      Next                                                  
   End Sub
End Module
' The example displays the following output:
'       'll' found in 'trellis' at position 3.
'       'ee' found in 'seer' at position 1.
'       'tt' found in 'latter' at position 2.
'       'mm' found in 'summer' at position 2.
'       No double characters in 'hoarse'.
'       'ss' found in 'lesser' at position 2.
'       'aa' found in 'aardvark' at position 0.
'       'nn' found in 'stunned' at position 3.
```

## <a name="non-word-character-w"></a>Nicht-Wortzeichen: \W

**\W** stimmt mit jedem Nicht-Wortzeichen überein. Das **\W**-Sprachelement entspricht der folgenden Zeichenklasse:

```
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]
```

Anders ausgedrückt: Mit Ausnahme der Zeichen, die in den Unicode-Kategorien enthalten sind, die in der folgenden Tabelle aufgelistet werden, liegt eine Übereinstimmung mit jedem Zeichen vor.

Kategorie | Beschreibung
-------- | -----------
Ll | Letter, Lowercase (Buchstabe, Kleinschreibung)
Lu | Letter, Uppercase (Buchstabe, Großschreibung)
Lt | Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)
Lo | Letter, Other (Buchstabe, andere)
Lm | Letter, Modifier (Buchstabe, Modifizierer)
Mn | Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)
Nd | Number, Decimal Digit (Zahl, Dezimalzahl)
Pc | Punctuation, Connector (Interpunktion, Konnektor). Zu dieser Kategorie gehören zehn Zeichen, von denen das UNTERSTRICH-Zeichen "u+005F" (_) am häufigsten verwendet wird.
 
Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\w** `[^a-zA-Z_0-9]`. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md). 

> [!NOTE]
> Aufgrund der Übereinstimmung des \w-Sprachelements mit jedem Wortzeichen wird es häufig mit einem verzögerten Quantifizierer verwendet, wenn von einem Muster für einen regulären Ausdruck mehrere Versuche bezüglich der Übereinstimmung eines von einem bestimmten Wortzeichen gefolgten Wortzeichens ausgeführt werden. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](quantifiers.md). 

Das folgende Beispiel veranschaulicht die **\W**-Zeichenklasse. Hierfür wird ein Muster für einen regulären Ausdruck definiert (`\b(\w+)(\W){1,2}`), das mit einem von einem oder zwei Nichtwortzeichen (z. B. Leer- oder Interpunktionszeichen) gefolgten Wort übereinstimmt. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Element | Beschreibung
------- | ----------- 
\b | Der Vergleich beginnt an einer Wortgrenze.
(\w+) | Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.
(\W){1,2} | Übereinstimmung mit einem Nicht-Wortzeichen (ein- oder zweimal). Dies ist die zweite Erfassungsgruppe.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\w+)(\W){1,2}";
      string input = "The old, grey mare slowly walked across the narrow, green pasture.";
      foreach (Match match in Regex.Matches(input, pattern))
      {
         Console.WriteLine(match.Value);
         Console.Write("   Non-word character(s):");
         CaptureCollection captures = match.Groups[2].Captures;
         for (int ctr = 0; ctr < captures.Count; ctr++)
             Console.Write(@"'{0}' (\u{1}){2}", captures[ctr].Value, 
                           Convert.ToUInt16(captures[ctr].Value[0]).ToString("X4"), 
                           ctr < captures.Count - 1 ? ", " : "");
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The
//          Non-word character(s):' ' (\u0020)
//       old,
//          Non-word character(s):',' (\u002C), ' ' (\u0020)
//       grey
//          Non-word character(s):' ' (\u0020)
//       mare
//          Non-word character(s):' ' (\u0020)
//       slowly
//          Non-word character(s):' ' (\u0020)
//       walked
//          Non-word character(s):' ' (\u0020)
//       across
//          Non-word character(s):' ' (\u0020)
//       the
//          Non-word character(s):' ' (\u0020)
//       narrow,
//          Non-word character(s):',' (\u002C), ' ' (\u0020)
//       green
//          Non-word character(s):' ' (\u0020)
//       pasture.
//          Non-word character(s):'.' (\u002E)
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\w+)(\W){1,2}"
      Dim input As String = "The old, grey mare slowly walked across the narrow, green pasture."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)
         Console.Write("   Non-word character(s):")
         Dim captures As CaptureCollection = match.Groups(2).Captures
         For ctr As Integer = 0 To captures.Count - 1
             Console.Write("'{0}' (\u{1}){2}", captures(ctr).Value, _
                           Convert.ToUInt16(captures(ctr).Value.Chars(0)).ToString("X4"), _
                           If(ctr < captures.Count - 1, ", ", ""))
         Next
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'       The
'          Non-word character(s):' ' (\u0020)
'       old,
'          Non-word character(s):',' (\u002C), ' ' (\u0020)
'       grey
'          Non-word character(s):' ' (\u0020)
'       mare
'          Non-word character(s):' ' (\u0020)
'       slowly
'          Non-word character(s):' ' (\u0020)
'       walked
'          Non-word character(s):' ' (\u0020)
'       across
'          Non-word character(s):' ' (\u0020)
'       the
'          Non-word character(s):' ' (\u0020)
'       narrow,
'          Non-word character(s):',' (\u002C), ' ' (\u0020)
'       green
'          Non-word character(s):' ' (\u0020)
'       pasture.
'          Non-word character(s):'.' (\u002E)
```

Da das `Group`-Objekt für die zweite Erfassungsgruppe nur ein einzelnes erfasstes Nicht-Wortzeichen aufweist, werden im Beispiel alle erfassten Nicht-Wortzeichen aus dem von der `CaptureCollection`-Eigenschaft zurückgegebenen `Group.Captures`-Objekt abgerufen.

## <a name="white-space-character-s"></a>Leerzeichen: \s

**\s** entspricht einem beliebigen Leerraumzeichen. Dies ist zu den in der folgenden Tabelle aufgeführten Escapesequenzen und Unicode-Kategorien äquivalent. 

Kategorie | Beschreibung
-------- | ----------- 
**\f** | Seitenvorschubzeichen, "\u000C".
**\n** | Zeilenumbruchzeichen, "\u000A".
**\r** | Wagenrücklaufzeichen, "\u000D".
**\t** | Tabstoppzeichen, "\u0009".
**\v** | Vertikales Tabstoppzeichen, "\u000B".
**\x85** | Auslassungs- oder NÄCHSTE ZEILE (NEL)-Zeichen (…), "\u0085".
**\p{Z}** | Übereinstimmung mit jedem Trennzeichen.
 

Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\s** `[ \f\n\r\t\v]`.  Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md). 

Das folgende Beispiel veranschaulicht die \s-Zeichenklasse. Hierfür wird ein Muster für einen regulären Ausdruck definiert (`\b\w+(e)?s(\s|$)`), das mit einem entweder auf "s" oder "es" endenden Wort übereinstimmt. Auf dieses Wort muss ein Leerzeichen oder das Ende der Eingabezeichenfolge folgen. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Element | Beschreibung
------- | -----------
\b | Der Vergleich beginnt an einer Wortgrenze.
\w+ | Übereinstimmung mit mindestens einem Wortzeichen. 
(e)? | Übereinstimmung mit "e", entweder null- oder einmal.
s | Übereinstimmung mit "s".
(\s&#124;$) | Übereinstimmung mit entweder einem Leerzeichen oder dem Ende der Eingabezeichenfolge.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b\w+(e)?s(\s|$)";
      string input = "matches stores stops leave leaves";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Value);
   }
}
// The example displays the following output:
//       matches
//       stores
//       stops
//       leaves
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b\w+(e)?s(\s|$)"
      Dim input As String = "matches stores stops leave leaves"
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Value)      
      Next
   End Sub
End Module
' The example displays the following output:
'       matches
'       stores
'       stops
'       leaves
```

## <a name="non-white-space-character-s"></a>Nicht-Leerzeichen: \S

**\S** stimmt mit jedem Nicht-Leerzeichen überein. Dies ist äquivalent zum Muster für den regulären `[^\f\n\r\t\v\x85\p{Z}]`-Ausdruck bzw. das Gegenteil des Musters für den regulären Ausdruck, der **\s** entspricht und daher mit Leerzeichen übereinstimmt. Weitere Informationen finden Sie im vorherigen Abschnitt, „Leerzeichen: \s“.

Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\S** `[^ \f\n\r\t\v]`. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md).

Im folgenden Beispiel wird das **\S**-Sprachelement veranschaulicht. Das Muster für den regulären Ausdruck \b(\S+)\s? stimmt mit durch Leerzeichen getrennten Zeichenfolgen überein. Das zweite Element im GroupCollection-Objekt der Übereinstimmung enthält die entsprechende Zeichenfolge. Der reguläre Ausdruck kann wie in der folgenden Tabelle dargestellt interpretiert werden.

Element | Beschreibung
------- | ----------- 
`\b` | Der Vergleich beginnt an einer Wortgrenze.
`(\S+)` | Übereinstimmung mit mindestens einem Nicht-Leerzeichen. Dies ist die erste Erfassungsgruppe.
`\s?` | Übereinstimmung mit keinem oder einem Leerzeichen. 
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\S+)\s?";
      string input = "This is the first sentence of the first paragraph. " + 
                            "This is the second sentence.\n" + 
                            "This is the only sentence of the second paragraph.";
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine(match.Groups[1]);
   }
}
// The example displays the following output:
//    This
//    is
//    the
//    first
//    sentence
//    of
//    the
//    first
//    paragraph.
//    This
//    is
//    the
//    second
//    sentence.
//    This
//    is
//    the
//    only
//    sentence
//    of
//    the
//    second
//    paragraph.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\S+)\s?"
      Dim input As String = "This is the first sentence of the first paragraph. " + _
                            "This is the second sentence." + vbCrLf + _
                            "This is the only sentence of the second paragraph."
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine(match.Groups(1))
      Next
   End Sub
End Module
' The example displays the following output:
'    This
'    is
'    the
'    first
'    sentence
'    of
'    the
'    first
'    paragraph.
'    This
'    is
'    the
'    second
'    sentence.
'    This
'    is
'    the
'    only
'    sentence
'    of
'    the
'    second
'    paragraph.
```

## <a name="decimal-digit-character-d"></a>Dezimalzahl: \d

**\d** stimmt mit jeder Dezimalzahl überein. Dies entspricht dem Muster des regulären `\\p{Nd}`-Ausdrucks, das neben den Standarddezimalzahlen 0 bis 9 auch die Dezimalzahlen einer Anzahl anderer Zeichensätze einschließt.

Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\d** `[0-9]`. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md).

Im folgenden Beispiel wird das **\d**-Sprachelement veranschaulicht. Anhand eines Tests soll ermittelt werden, ob eine Eingabezeichenfolge eine gültige Telefonnummer in den USA und Kanada darstellt. Das Muster für reguläre Ausdrücke `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` wird entsprechend der folgenden Tabelle definiert:

Element | Beschreibung
------- | ----------- 
`^` | Beginnt den Vergleich am Anfang der Eingabezeichenfolge.
`\(?` | Übereinstimmung mit null oder einem Literalzeichen ("("). 
`\d{3}` | Entsprechung für drei Dezimalstellen finden. 
`\)?` | Übereinstimmung mit null oder einem Literalzeichen (")").
`[\s-]` | Übereinstimmung mit einem Bindestrich oder Leerzeichen.
`(\(?\d{3}\)?[\s-])?` | Übereinstimmung mit einer optionalen öffnenden Klammer gefolgt von drei Dezimalzahlen, einer optionalen schließenden Klammer sowie entweder null- oder einmal von einem Leerzeichen oder Bindestrich. Dies ist die erste Erfassungsgruppe.
`\d{3}-\d{4}` | Übereinstimmung mit drei Dezimalzahlen gefolgt von einem Bindestrich und vier zusätzlichen Dezimalzahlen.
`$` | Entsprechung für das Ende der Eingabezeichenfolge finden.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$";
      string[] inputs = { "111 111-1111", "222-2222", "222 333-444", 
                          "(212) 111-1111", "111-AB1-1111", 
                          "212-111-1111", "01 999-9999" };

      foreach (string input in inputs)
      {
         if (Regex.IsMatch(input, pattern)) 
            Console.WriteLine(input + ": matched");
         else
            Console.WriteLine(input + ": match failed");
      }
   }
}
// The example displays the following output:
//       111 111-1111: matched
//       222-2222: matched
//       222 333-444: match failed
//       (212) 111-1111: matched
//       111-AB1-1111: match failed
//       212-111-1111: matched
//       01 999-9999: match failed
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$"
      Dim inputs() As String = { "111 111-1111", "222-2222", "222 333-444", _
                                 "(212) 111-1111", "111-AB1-1111", _
                                 "212-111-1111", "01 999-9999" }

      For Each input As String In inputs
         If Regex.IsMatch(input, pattern) Then 
            Console.WriteLine(input + ": matched")
         Else
            Console.WriteLine(input + ": match failed")
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
'       111 111-1111: matched
'       222-2222: matched
'       222 333-444: match failed
'       (212) 111-1111: matched
'       111-AB1-1111: match failed
'       212-111-1111: matched
'       01 999-9999: match failed
```

## <a name="non-digit-character-d"></a>Nicht-Zahlen: \D

**\D** stimmt mit jedem Zeichen außer Zahlen überein. Dies entspricht dem Muster des regulären Ausdrucks `\P{Nd}`.

Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht **\D** `[^0-9]`. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt [ECMAScript-Vergleichsverhalten](options.md#ecmascript-matching-behavior) unter [Optionen für reguläre Ausdrücke](options.md).

Im folgenden Beispiel wird das **\D**-Sprachelement veranschaulicht. Anhand eines Tests wird ermittelt, ob eine Zeichenfolge (z. B. eine Teilenummer) aus der gewünschten Kombination von Dezimalzahlen und Nicht-Dezimalzahlen besteht. Das Muster für reguläre Ausdrücke `^\D\d{1,5}\D*$` wird entsprechend der folgenden Tabelle definiert:

Element | Beschreibung
------- | ----------- 
`^` | Beginnt den Vergleich am Anfang der Eingabezeichenfolge.
`\D` | Übereinstimmung mit jedem Zeichen außer Zahlen. 
`\d{1,5}` | Übereinstimmung mit einer bis fünf Dezimalzahlen. 
`\D*` | Übereinstimmung mit null, einem oder mehreren Nichtdezimalzeichen. 
`$` | Entsprechung für das Ende der Eingabezeichenfolge finden.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"^\D\d{1,5}\D*$"; 
      string[] inputs = { "A1039C", "AA0001", "C18A", "Y938518" }; 

      foreach (string input in inputs)
      {
         if (Regex.IsMatch(input, pattern))
            Console.WriteLine(input + ": matched");
         else
            Console.WriteLine(input + ": match failed");
      }
   }
}
// The example displays the following output:
//       A1039C: matched
//       AA0001: match failed
//       C18A: matched
//       Y938518: match failed
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "^\D\d{1,5}\D*$" 
      Dim inputs() As String = { "A1039C", "AA0001", "C18A", "Y938518" } 

      For Each input As String In inputs
         If Regex.IsMatch(input, pattern) Then
            Console.WriteLine(input + ": matched")
         Else
            Console.WriteLine(input + ": match failed")
         End If   
      Next
   End Sub
End Module
' The example displays the following output:
```

## <a name="supported-unicode-general-categories"></a>Unterstützte allgemeine Unicode-Kategorien

In der folgenden Tabelle werden die allgemeinen, in Unicode definierten Kategorien aufgeführt. Weitere Informationen finden Sie in den Unterthemen „UCD File Format“ (UCD-Dateiformat) und „General Category Values“ (Allgemeine Kategorienwerte) der [Unicode Character Database](http://www.unicode.org/reports/tr44/).

Kategorie | Beschreibung
-------- | -----------
**Lu** | Letter, Uppercase (Buchstabe, Großschreibung)
**Ll** | Letter, Lowercase (Buchstabe, Kleinschreibung)
**Lt** | Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)
**Lm** | Letter, Modifier (Buchstabe, Modifizierer)
**Lo** | Letter, Other (Buchstabe, andere)
**L** | Alle Buchstaben. Dies schließt die Zeichen **Lu**, **Ll**, **Lt**, **Lm** und **Lo** ein.
**Mn** | Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)
**Mc** | Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)
**Me** | Mark, Enclosing (Satzzeichen, einschließend)
**M** | Alle diakritischen Zeichen. Dies schließt die Kategorien **Mn**, **Mc** und **Me** ein.
**Nd** | Number, Decimal Digit (Zahl, Dezimalzahl)
**Nl** | Number, Letter (Zahl, Buchstabe)
**No** | Number, Other (Zahl, andere)
**N** | Alle Zahlen. Dies schließt die Kategorien **Nd**, **Nl** und **No** ein.
**Pc** | Punctuation, Connector (Interpunktion, Konnektor)
**Pd** | Punctuation, Dash (Interpunktion, Bindestrich)
**Ps** | Punctuation, Open (Interpunktion, öffnend)
**Pe** | Punctuation, Close (Interpunktion, schließend)
**Pi** | Punctuation, Initial quote (Interpunktion, öffnendes Anführungszeichen; kann sich je nach Verwendung wie "Ps" oder "Pe" verhalten)
**Pf** | Punctuation, Final quote (Interpunktion, schließendes Anführungszeichen; kann sich je nach Verwendung wie "Ps" oder "Pe" verhalten)
**Po** | Punctuation, Other (Interpunktion, andere)
**P** | Alle Interpunktionszeichen. Dies schließt die Kategorien **Pc**, **Pd**, **Ps**, **Pe**, **Pi**, **Pf** und **Po** ein.
**Sm** | Symbol, Math (Symbol, Mathematik)
**Sc** | Symbol, Currency (Symbol, Währung)
**Sk** | Symbol, Modifier (Symbol, Modifizierer)
**So** | Symbol, Other (Symbol, andere)
**S** | Alle Symbole. Dies schließt die Kategorien **Sm**, **Sc**, **Sk** und **So** ein.
**Zs** | Separator, Space (Trennzeichen, Leerzeichen)
**Zl** | Separator, Line (Trennzeichen, Zeile)
**Zp** | Separator, Paragraph (Trennzeichen, Absatz)
**Z** | Alle Trennzeichen. Dies schließt die Kategorien **Zs**, **Zl** und **Zp** ein.
**Cc** | Other, Control (Andere, Steuerzeichen)
**Cf** | Other, Format (Andere, Format)
**Cs** | Other, Surrogate (Andere, Ersatzzeichen)
**Co** | Other, Private Use (Andere, persönliche Verwendung)
**Cn** | Other, Not Assigned (Andere, nicht zugewiesen; kein Zeichen weist diese Eigenschaft auf)
**C** | Alle Steuerzeichen. Dies schließt die Kategorien **Cc**, **Cf**, **Cs**, **Co** und **Cn** ein.
 
##<a name="supported-named-blocks"></a>Unterstützte benannte Blöcke

In der folgenden Tabelle werden die von .NET bereitgestellten benannten Blöcke aufgelistet. Der Satz von unterstützten benannten Blöcke basiert auf Unicode 4.0 und Perl 5.6.

Codepunktbereich | Blockname
---------------- | ---------- 
0000 - 007F | **IsBasicLatin**
0080 - 00FF | **IsLatin-1Supplement**
0100 - 017F | **IsLatinExtended-A**
0180 - 024F | **IsLatinExtended-B**
0250 - 02AF | **IsIPAExtensions**
02B0 - 02FF | **IsSpacingModifierLetters**
0300 - 036F | **IsCombiningDiacriticalMarks**
0370 - 03FF | **IsGreek** – oder – **IsGreekandCoptic**
0400 - 04FF | **IsCyrillic**
0500 - 052F | **IsCyrillicSupplement**
0530 - 058F | **IsArmenian**
0590 - 05FF | **IsHebrew**
0600 - 06FF | **IsArabic**
0700 - 074F | **IsSyriac**
0780 - 07BF | **IsThaana**
0900 - 097F | **IsDevanagari**
0980 - 09FF | **IsBengali**
0A00 - 0A7F | **IsGurmukhi**
0A80 - 0AFF | **IsGujarati**
0B00 - 0B7F | **IsOriya**
0B80 - 0BFF | **IsTamil**
0C00 - 0C7F | **IsTelugu**
0C80 - 0CFF | **IsKannada**
0D00 - 0D7F | **IsMalayalam**
0D80 - 0DFF | **IsSinhala**
0E00 - 0E7F | **IsThai**
0E80 - 0EFF | **IsLao**
0F00 - 0FFF | **IsTibetan**
1000 - 109F | **IsMyanmar**
10A0 - 10FF | **IsGeorgian**
1100 - 11FF | **IsHangulJamo**
1200 - 137F | **IsEthiopic**
13A0 - 13FF | **IsCherokee**
1400 - 167F | **IsUnifiedCanadianAboriginalSyllabics**
1680 - 169F | **IsOgham**
16A0 - 16FF | **IsRunic**
1700 - 171F | **IsTagalog**
1720 - 173F | **IsHanunoo**
1740 - 175F | **IsBuhid**
1760 - 177F | **IsTagbanwa**
1780 - 17FF | **IsKhmer**
1800 - 18AF | **IsMongolian**
1900 - 194F | **IsLimbu**
1950 - 197F | **IsTaiLe**
19E0 - 19FF | **IsKhmerSymbols**
1D00 - 1D7F | **IsPhoneticExtensions**
1E00 - 1EFF | **IsLatinExtendedAdditional**
1F00 - 1FFF | **IsGreekExtended**
2000 - 206F | **IsGeneralPunctuation**
2070 - 209F | **IsSuperscriptsandSubscripts**
20A0 - 20CF | **IsCurrencySymbols**
20D0 - 20FF | **IsCombiningDiacriticalMarksforSymbols** – oder – **IsCombiningMarksforSymbols**
2100 - 214F | **IsLetterlikeSymbols**
2150 - 218F | **IsNumberForms**
2190 - 21FF | **IsArrows**
2200 - 22FF | **IsMathematicalOperators**
2300 - 23FF | **IsMiscellaneousTechnical**
2400 - 243F | **IsControlPictures**
2440 - 245F | **IsOpticalCharacterRecognition**
2460 - 24FF | **IsEnclosedAlphanumerics**
2500 - 257F | **IsBoxDrawing**
2580 - 259F | **IsBlockElements**
25A0 - 25FF | **IsGeometricShapes**
2600 - 26FF | **IsMiscellaneousSymbols**
2700 - 27BF | **IsDingbats**
27C0 - 27EF | **IsMiscellaneousMathematicalSymbols-A**
27F0 - 27FF | **IsSupplementalArrows-A**
2800 - 28FF | **IsBraillePatterns**
2900 - 297F | **IsSupplementalArrows-B**
2980 - 29FF | **IsMiscellaneousMathematicalSymbols-B**
2A00 - 2AFF | **IsSupplementalMathematicalOperators**
2B00 - 2BFF | **IsMiscellaneousSymbolsandArrows**
2E80 - 2EFF | **IsCJKRadicalsSupplement**
2F00 - 2FDF | **IsKangxiRadicals**
2FF0 - 2FFF | **IsIdeographicDescriptionCharacters**
3000 - 303F | **IsCJKSymbolsandPunctuation**
3040 - 309F | **IsHiragana**
30A0 - 30FF | **IsKatakana**
3100 - 312F | **IsBopomofo**
3130 - 318F | **IsHangulCompatibilityJamo**
3190 - 319F | **IsKanbun**
31A0 - 31BF | **IsBopomofoExtended**
31F0 - 31FF | **IsKatakanaPhoneticExtensions**
3200 - 32FF | **IsEnclosedCJKLettersandMonths**
3300 - 33FF | **IsCJKCompatibility**
3400 - 4DBF | **IsCJKUnifiedIdeographsExtensionA**
4DC0 - 4DFF | **IsYijingHexagramSymbols**
4E00 - 9FFF | **IsCJKUnifiedIdeographs**
A000 - A48F | **IsYiSyllables**
A490 - A4CF | **IsYiRadicals**
AC00 - D7AF | **IsHangulSyllables**
D800 - DB7F | **IsHighSurrogates**
DB80 - DBFF | **IsHighPrivateUseSurrogates**
DC00 - DFFF | **IsLowSurrogates**
E000 - F8FF | **IsPrivateUse** oder **IsPrivateUseArea**
F900 - FAFF | **IsCJKCompatibilityIdeographs**
FB00 - FB4F | **IsAlphabeticPresentationForms** 
FB50 - FDFF | **IsArabicPresentationForms-A** 
FE00 - FE0F | **IsVariationSelectors** 
FE20 - FE2F | **IsCombiningHalfMarks** 
FE30 - FE4F | **IsCJKCompatibilityForms** 
FE50 - FE6F | **IsSmallFormVariants**
FE70 - FEFF | **IsArabicPresentationForms-B** 
FF00 - FFEF | **IsHalfwidthandFullwidthForms** 
FFF0 - FFFF | **IsSpecials**
 
<a name="character-class-subtraction"></a>
## <a name="character-class-subtraction-basegroup---excludedgroup"></a>Zeichenklassensubtraktion: [base_group - [excluded_group]]

Eine Zeichenklasse definiert einen Satz von Zeichen. Durch Zeichenklassensubtraktion erhalten Sie einen Zeichensatz, der das Ergebnis des Ausschlusses der Zeichen einer Zeichenklasse von einer anderen darstellt. 

Ein Zeichenklassensubtraktionsausdruck weist folgende Form auf:

__[__*Basis*_*gruppe*-__[__*ausgeschlossene*_*Gruppe*__]]--

Die eckigen Klammern (**[]**) und der Bindestrich (-) sind obligatorisch. Bei der *Basis_gruppe* handelt es sich um eine positive Zeichengruppe oder eine negative Zeichengruppe. Die Komponente *ausgeschlossene_Gruppe* stellt eine andere positive oder negative Zeichengruppe bzw. einen anderen Zeichenklassensubtraktions-Ausdruck dar (d.h. Sie können Zeichenklassensubtraktions-Ausdrücke schachteln). 

Beispiel: Angenommen, Sie verfügen über eine Basisgruppe, die aus dem Zeichenbereich von "a" bis "z" besteht. Zum Definieren eines Zeichensatzes, der mit Ausnahme des Zeichens "m" aus der Basisgruppe besteht, verwenden Sie `[a-z-[m]]`. Zum Definieren eines Zeichensatzes, der mit Ausnahme der Zeichen "d", "j" und "p" aus der Basisgruppe besteht, verwenden Sie `[a-z-[djp]]`. Zum Definieren eines Zeichensatzes, der mit Ausnahme des Zeichenbereichs von "m" bis "p" aus der Basisgruppe besteht, verwenden Sie `[a-z-[m-p]]`. 

Betrachten Sie den geschachtelten `[a-z-[d-w-[m-o]]]`-Zeichenklassensubtraktionsausdruck. Der Ausdruck wird vom innersten Zeichenbereich nach außen ausgewertet. Zuerst wird der Zeichenbereich von "m" bis "o" vom Zeichenbereich "d" bis "w" subtrahiert. Das Ergebnis stellt einen Satz von Zeichen von "d" bis "l" und von "p" bis "w" dar. Dieser Satz wird anschließend vom Zeichenbereich "a" bis "z" subtrahiert, sodass sich der Zeichensatz `[abcmnoxyz]` ergibt.

Für die Zeichenklassensubtraktion kann jede Zeichenklasse verwendet werden. Zum Definieren eines Zeichensatzes, der aus allen Unicode-Zeichen von \u0000 bis \uFFFF mit Ausnahme von Leerzeichen (**\s**), der Zeichen in der allgemeinen Interpunktionskategorie (**\p{P}**), der Zeichen im benannten Block **IsGreek** (**\p{IsGreek}**) und des Unicode-Steuerzeichens NEXT LINE (\x85) besteht, verwenden Sie `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.

Wählen Sie für einen Zeichenklassensubtraktionsausdruck Zeichenklassen aus, mit denen nützliche Ergebnisse erzielt werden können. Vermeiden Sie Ausdrücke, die einen leeren Satz von Zeichen ergeben, mit nichts übereinstimmen oder ein Äquivalent der ursprünglichen Basisgruppe darstellen. Beispielsweise ergibt der Ausdruck `[\p{IsBasicLatin}-[\x00-\x7F]]`, durch den alle Zeichen des Zeichenbereichs **IsBasicLatin** von der allgemeinen Kategorie **IsBasicLatin** subtrahiert werden, einen leeren Zeichensatz. Gleichermaßen ist die ursprüngliche Basisgruppe das Ergebnis des Ausdrucks `[a-z-[0-9]]`. Der Grund hierfür ist, dass die Basisgruppe (der Zeichenbereich der Buchstaben von "a" bis "z") keine Zeichen aus der ausgeschlossenen Gruppe (dem Zeichenbereich der Dezimalzahlen von "0" bis "9") aufweist. 

Im folgenden Beispiel wird ein regulärer Ausdruck definiert (`^[0-9-[2468]]+$`), der in einer Eingabezeichenfolge Übereinstimmungen für Null und ungerade Zahlen ergibt. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Element | Beschreibung
------- | ----------- 
`^` | Beginnt am Anfang der Eingabezeichenfolge mit der Übereinstimmung.
`[0-9-[2468]]+` | Mindestens eine Übereinstimmung mit einem Zeichen von 0 bis 9 (mit Ausnahme von 2, 4, 6 und 8) liegt vor. Anders ausgedrückt: Es liegt mindestens eine Übereinstimmung mit Null oder einer ungeraden Zahl vor.
`$` | Ende des Abgleichs am Ende der Eingabezeichenfolge.
 
```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string[] inputs = { "123", "13579753", "3557798", "335599901" };
      string pattern = @"^[0-9-[2468]]+$";

      foreach (string input in inputs)
      {
         Match match = Regex.Match(input, pattern);
         if (match.Success) 
            Console.WriteLine(match.Value);
      }      
   }
}
// The example displays the following output:
//       13579753
//       335599901
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim inputs() As String = { "123", "13579753", "3557798", "335599901" }
      Dim pattern As String = "^[0-9-[2468]]+$"

      For Each input As String In inputs
         Dim match As Match = Regex.Match(input, pattern)
         If match.Success Then Console.WriteLine(match.Value)
      Next
   End Sub
End Module
' The example displays the following output:
'       13579753
'       335599901
```

## <a name="see-also"></a>Siehe auch

[Optionen für reguläre Ausdrücke](options.md)


<!--HONumber=Nov16_HO1-->


