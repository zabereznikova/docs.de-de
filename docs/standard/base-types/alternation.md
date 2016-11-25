---
title: "Alternierungskonstrukte in regulären Ausdrücken"
description: "Alternierungskonstrukte in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 59ffac4d-fc6e-461f-8783-d9f8dc88ce2c
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 2c31622ff97f30e565ed2cd82128518d04d5d1dc

---

# <a name="alternation-constructs-in-regular-expressions"></a>Alternierungskonstrukte in regulären Ausdrücken

Alternierungskonstrukte ändern einen regulären Ausdruck, um Entweder-Oder-Vergleiche oder eine bedingte Übereinstimmung zuzulassen. .NET unterstützt drei Alternierungskonstrukte:

* Musterabgleich mit **|**

* Bedingte Übereinstimmung mit **(?(**_Ausdruck_**)**_ja_**|**_nein_**)**

* Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe

## <a name="pattern-matching-with-"></a>Musterabgleich mit |

Sie können das vertikale Balkenzeichen (|) für Vergleiche mit einem oder mehreren aus einer Reihe von Mustern verwenden, wobei das |-Zeichen als Trennzeichen für die einzelnen Muster dient. 

Wie bei der positiven Zeichenklasse kann das |-Zeichen für Vergleiche mit jedem beliebigen Zeichen aus einer Reihe einzelner Zeichen verwendet werden. Im folgenden Beispiel wird sowohl eine positive Zeichenklasse als auch ein Entweder-Oder-Musterabgleich mithilfe des |-Zeichens verwendet, um Vorkommen der Wörter „gray“ oder „grey“ in einer Zeichenfolge zu finden. In diesem Fall ergibt das |-Zeichen einen regulären Ausdruck, der eine ausführlichere Ausgabe bewirkt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      // Regular expression using character class.
      string pattern1 = @"\bgr[ae]y\b";
      // Regular expression using either/or.
      string pattern2 = @"\bgr(a|e)y\b";

      string input = "The gray wolf blended in among the grey rocks.";
      foreach (Match match in Regex.Matches(input, pattern1))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, pattern2))
         Console.WriteLine("'{0}' found at position {1}", 
                           match.Value, match.Index);
   }
}
// The example displays the following output:
//       'gray' found at position 4
//       'grey' found at position 35
//       
//       'gray' found at position 4
//       'grey' found at position 35           
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      ' Regular expression using character class.
      Dim pattern1 As String = "\bgr[ae]y\b"
      ' Regular expression using either/or.
      Dim pattern2 As String = "\bgr(a|e)y\b"

      Dim input As String = "The gray wolf blended in among the grey rocks."
      For Each match As Match In Regex.Matches(input, pattern1)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, pattern2)
         Console.WriteLine("'{0}' found at position {1}", _
                           match.Value, match.Index)
      Next      
   End Sub
End Module
' The example displays the following output:
'       'gray' found at position 4
'       'grey' found at position 35
'       
'       'gray' found at position 4
'       'grey' found at position 35 
```

Der reguläre Ausdruck, der das |-Zeichen verwendet, `\bgr(a|e)y\b,`, wird wie in der folgenden Tabelle dargestellt interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`gr` | Übereinstimmung mit den Zeichen "gr".
`(a|e)` | Übereinstimmung mit entweder "a" oder "e".
`y\b` | Übereinstimmung mit "y" an einer Wortgrenze.


Das |-Zeichen kann auch verwendet werden, um einen Entweder-Oder-Vergleich mit mehreren Zeichen oder Teilausdrücken durchzuführen, wobei eine beliebige Kombination von Zeichenliteralen und Sprachelementen für reguläre Ausdrücke enthalten sein kann. (Die Zeichenklasse stellt diese Funktionalität nicht bereit.) Im folgenden Beispiel wird das |-Zeichen verwendet, um entweder eine Sozialversicherungsnummer in den USA, also eine neunstellige Zahl mit dem Format *ddd-dd-dddd*, oder eine Identifikationsnummer des Arbeitgebers in den USA (EIN, Employer Identification Number), also eine neunstellige Zahl mit dem Format *dd-ddddddd*, zu extrahieren.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Der reguläre Ausdruck `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`(\d{2}-\d{7}|;\d{3}-\d{2}-\d{4})` | Eine der folgenden Varianten muss übereinstimmen: zwei Dezimalstellen gefolgt von einem Bindestrich gefolgt von sieben Dezimalstellen; oder drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen. 
`\d` | Der Vergleich endet an einer Wortgrenze.
                                         
## <a name="conditional-matching-with-an-expression"></a>Bedingte Übereinstimmung mit einem Ausdruck

Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es ein ursprüngliches Muster zuordnen kann. Die Syntax lautet:

**(? (**_Ausdruck_**)**_ja_**|**_nein_**)**

wobei *Ausdruck* das ursprüngliche zu entsprechende Muster ist. *ja* ist das entsprechende Muster, wenn „Ausdruck“ zutrifft, und *nein* ist das entsprechende optionale Muster, wenn *Ausdruck* nicht zutrifft. Das Modul für reguläre Ausdrücke behandelt *Ausdruck* als Assertion mit einer Breite von Null, das heißt, dass das Modul für reguläre Ausdrücke im Eingabestream nicht weitergeführt wird, nachdem es *Ausdruck* auswertet. Daher entspricht dieses Konstrukt Folgendem:

**(?(?**=_Ausdruck_**)**_ja_**|**_nein_**)**

, wobei **(?**=_Ausdruck_**)** ein Assertionskonstrukt mit einer Breite von Null ist. (Weitere Informationen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping.md).) Da das Modul für reguläre Ausdrücke *Ausdruck* als Anker (eine Assertion mit einer Breite von null) interpretiert, muss *Ausdruck* entweder eine Assertion mit einer Breite von null (weitere Informationen finden Sie unter [Anker in regulären Ausdrücken](anchors.md)) oder ein Teilausdruck sein, der auch in *ja* enthalten ist. Andernfalls kann das Muster *ja* nicht zugeordnet werden. 

> [!NOTE]
> Wenn *Ausdruck* eine benannte oder nummerierte Erfassungsgruppe ist, wird das Alternierungskonstrukt als Erfassungstest interpretiert. Weitere Informationen finden Sie im nächsten Abschnitt [Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe](#conditional-matching-based-on-a-valid-captured-group). Das heißt, dass das Modul für reguläre Ausdrücke nicht versucht, mit der erfassten Teilzeichenfolge übereinzustimmen. Stattdessen wird das Vorhandensein oder Fehlen der Gruppe getestet.
 

Das folgende Beispiel ist eine Abwandlung des Beispiels aus dem vorherigen Abschnitt. Es wird die bedingte Übereinstimmung verwendet, um zu ermitteln, ob die ersten drei Zeichen nach einer Wortgrenze zwei Ziffern gefolgt von einem Bindestrich sind. Wenn dies der Fall ist, wird eine Übereinstimmung mit einer Identifikationsnummer des Arbeitgebers in den USA versucht. Wenn dies nicht der Fall ist, wird eine Übereinstimmung mit einer Sozialversicherungsnummer in den USA versucht.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Das Muster für reguläre Ausdrücke `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`(?(\d{2}-)` | Bestimmen, ob die nächsten drei Zeichen aus zwei Ziffern gefolgt von einem Bindestrich bestehen.
`\d{2}-\d{7}` | Wenn das vorherige Muster übereinstimmt, stimmen zwei Ziffern gefolgt von einem Bindestrich gefolgt von sieben Ziffern überein.
`\d{3}-\d{2}-\d{4}` | Wenn das vorherige Muster nicht übereinstimmt, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein. 
`\b` | Übereinstimmung mit einer Wortgrenze.
 
## <a name="conditional-matching-based-on-a-valid-captured-group"></a>Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe

Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es mit einer angegebenen Erfassungsgruppe übereingestimmt hat. Die Syntax lautet:

**(?(**_Name_**)**_ja_**|**_nein_**)**

oder

**(?(**_Nummer_**)**_ja_**|**_nein_**)**

, wobei *Name* der Name und *Nummer* die Nummer einer Erfassungsgruppe ist. *ja* ist der Ausdruck, mit dem Übereinstimmung bestehen muss, wenn Name oder Nummer eine Übereinstimmung aufweisen, und *nein* ist der optionale Ausdruck, mit dem Übereinstimmung bestehen muss, wenn dies nicht der Fall ist.

Wenn *Name* nicht dem Namen einer Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, wird das Alternierungskonstrukt, wie im vorherigen Abschnitt erläutert, als Ausdruckstest interpretiert. In der Regel bedeutet dies, dass „Ausdruck“ `false` ergibt. Wenn `number` keiner nummerierten Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, löst das Modul für reguläre Ausdrücke eine [ArgumentException](xref:System.ArgumentException) aus.

Das folgende Beispiel ist eine Abwandlung des Beispiels aus dem vorherigen Abschnitt. Es wird eine Erfassungsgruppe mit dem Namen `n2` verwendet, die aus zwei Ziffern gefolgt von einem Bindestrich besteht. Das Alternierungskonstrukt testet, ob diese Erfassungsgruppe in der Eingabezeichenfolge abgeglichen wurde. Wenn dies der Fall ist, versucht das Alternierungskonstrukt, mit den letzten sieben Ziffern einer neunstelligen Identifikationsnummer des Arbeitgebers in den USA versucht. Wenn dies nicht der Fall ist, versucht es, mit einer neunstelligen Sozialversicherungsnummer in den USA versucht.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example displays the following output:
//       Matches for \b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
```

Das Muster für reguläre Ausdrücke `\b(?<n2>\d{2}-)*(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`(?<n2>\d{2}-)*` | Entspricht 0 (Null) oder einem Vorkommen von zwei Ziffern gefolgt von einem Bindestrich. Geben Sie für die Erfassungsgruppe `n2` als Namen an.
`(?(n2)` | Prüfen, ob `n2` in der Eingabezeichenfolge abgeglichen wurde. 
`)\d{7}` | Wenn `n2` abgeglichen wurde, stimmen sieben Dezimalstellen überein.
`|;\d{3}-\d{2}-\d{4}` | Wenn `n2` nicht abgeglichen wurde, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein. 
`\b` | Übereinstimmung mit einer Wortgrenze.
 
Eine Variante dieses Beispiels, die eine nummerierte Gruppe statt einer benannten Gruppe verwendet, wird im folgenden Beispiel gezeigt. Das entsprechende Muster des regulären Ausdrucks lautet `\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = @"\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b";
      string input = "01-9999999 020-333333 777-88-9999";
      Console.WriteLine("Matches for {0}:", pattern);
      foreach (Match match in Regex.Matches(input, pattern))
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index);
   }
}
// The example display the following output:
//       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
//          01-9999999 at position 0
//          777-88-9999 at position 22
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "\b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b"
      Dim input As String = "01-9999999 020-333333 777-88-9999"
      Console.WriteLine("Matches for {0}:", pattern)
      For Each match As Match In Regex.Matches(input, pattern)
         Console.WriteLine("   {0} at position {1}", match.Value, match.Index)
      Next   
   End Sub
End Module
' The example displays the following output:
'       Matches for \b(\d{2}-)*(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b:
'          01-9999999 at position 0
'          777-88-9999 at position 22
```

Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


