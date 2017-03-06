---
title: "Quantifizierer in regulären Ausdrücken"
description: "Quantifizierer in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 8e5124c4-20b5-4c57-ab68-301d1d7311c4
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: cd47cc351fb926bcf444bdcbd12f3cd61d9fb327
ms.lasthandoff: 03/02/2017

---

# <a name="quantifiers-in-regular-expressions"></a>Quantifizierer in regulären Ausdrücken

Quantifizierer geben an, wie viele Instanzen eines Zeichens, einer Gruppe oder einer Zeichenklasse in der Eingabe vorhanden sein müssen, damit eine Übereinstimmung gefunden wird. In der folgenden Tabelle werden die von .NET unterstützten Quantifizierer aufgeführt.

Gieriger Quantifizierer | Träger Quantifizierer | Beschreibung
----------------- | --------------- | ----------- 
**\*** | **\*?** | Übereinstimmung mit null oder mehr Vorkommen.
**+** | **+?** | Übereinstimmung mit einem oder mehr Vorkommen.
**?** | **??** | Übereinstimmung mit null oder einem Vorkommen.
**{**_n_**}** | **{**_n_**}?** | Übereinstimmung mit genau n Vorkommen.
**{**_n_**,}** | **{**_n_**,}?** | Übereinstimmung mit mindestens n Vorkommen.
**{**_n_**,**_m_**}** | **{**_n_**,**_m_**}?** | Übereinstimmung mit n bis m Vorkommen.
 
Die Mengen *n* und *m* sind ganzzahlige Konstanten. Gewöhnlich sind Quantifizierer gierig; durch sie gleicht das Modul für reguläre Ausdrücke so viele Vorkommen bestimmter Muster wie möglich ab. Das Anhängen des `?`-Zeichens an einen Quantifizierer macht es träge; es bewirkt, dass das Modul für reguläre Ausdrücke so wenige Vorkommen wie möglich abgleicht. Eine vollständige Beschreibung des Unterschieds zwischen gierigen und trägen Quantifizierern finden Sie weiter unten in diesem Thema im Abschnitt [Gierige und träge Quantifizierer](#greedy-and-lazy-quantifiers).

> [!IMPORTANT]
> Das Schachteln von Quantifizierern (z.B. wie durch das Muster für reguläre Ausdrücke `(a*)*`) kann die Anzahl von Vergleichen, die das Modul für reguläre Ausdrücke ausführen muss, als Exponentialfunktion der Anzahl von Zeichen in der Eingabezeichenfolge erhöhen. Weitere Informationen zu diesem Verhalten und zu Problemumgehungen finden Sie unter [Backtracking in regulären Ausdrücken](backtracking.md).

## <a name="regular-expression-quantifiers"></a>Quantifizierer in regulären Ausdrücken

In den folgenden Abschnitten werden die Quantifizierer aufgeführt, die in regulären .NET-Ausdrücken unterstützt werden. 

> [!NOTE]
> Wenn die Zeichen \*, +, ?, { und } im Muster für reguläre Ausdrücke enthalten sind, interpretiert das Modul für reguläre Ausdrücke sie als Quantifizierer oder als Teil von Quantifiziererkonstrukten, sofern sie nicht in einer [Zeichenklasse](classes.md) enthalten sind. Um sie als Literalzeichen außerhalb einer Zeichenklasse zu interpretieren, müssen Sie sie mit Escapezeichen versehen, indem Sie ihnen einen umgekehrten Schrägstrich voranstellen. Die Zeichenfolge `\*` in einem Muster für reguläre Ausdrücke wird z.B. als literales Sternchenzeichen („*“) interpretiert.

### <a name="match-zero-or-more-times-"></a>Übereinstimmung mit null oder mehr Vorkommen: \*

Der \*-Quantifizierer gleicht das vorangehende Element nullmal oder häufiger ab. Dies entspricht dem **{0,}**-Quantifizierer. **\*** ist ein gieriger Quantifizierer, dessen träges Äquivalent **\*?** lautet.

Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Von den neun Ziffern in der Eingabezeichenfolge entsprechen fünf dem Muster, bei vier Ziffern (`95`, `929`, `9129` und `9919`) ist das nicht der Fall.

```csharp
string pattern = @"\b91*9*\b";   
string input = "99 95 919 929 9119 9219 999 9919 91119";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       '99' found at position 0.
//       '919' found at position 6.
//       '9119' found at position 14.
//       '999' found at position 24.
//       '91119' found at position 33.
```

```vb
Dim pattern As String = "\b91*9*\b"   
Dim input As String = "99 95 919 929 9119 9219 999 9919 91119"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '99' found at position 0.
'       '919' found at position 6.
'       '9119' found at position 14.
'       '999' found at position 24.
'       '91119' found at position 33.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`91*` | Übereinstimmung mit „9“, gefolgt von null oder mehr Zeichen „1“.
`9*` | Übereinstimmung mit null oder mehr Zeichen „9“.
`\b` | An einer Wortgrenze beenden.
 
### <a name="match-one-or-more-times-"></a>Übereinstimmung mit einem oder mehr Vorkommen: +

Der **+**-Quantifizierer gleicht das vorangehende Element einmal oder häufiger ab. Er entspricht **{1,}**. **+** ist ein gieriger Quantifizierer, dessen träges Äquivalent **+?** lautet.

Beispielsweise versucht der reguläre Ausdruck `\ban+\w*?\b` ganze Wörter abzugleichen, die mit dem Buchstaben `a` beginnen, gefolgt von mindestens einer Instanz des Buchstabens `n`. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Der reguläre Ausdruck gleicht die Wörter `an`, `annual`, `announcement` und `antique` ab und findet richtigerweise keine Übereinstimmung mit `autumn` und `all`.

```csharp
string pattern = @"\ban+\w*?\b";

string input = "Autumn is a great time for an annual announcement to all antique collectors.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//       'an' found at position 27.
//       'annual' found at position 30.
//       'announcement' found at position 37.
//       'antique' found at position 57.      
```

```vb
Dim pattern As String = "\ban+\w*?\b"

Dim input As String = "Autumn is a great time for an annual announcement to all antique collectors."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next   
' The example displays the following output:   
'       'an' found at position 27.
'       'annual' found at position 30.
'       'announcement' found at position 37.
'       'antique' found at position 57. 
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`an+` | Übereinstimmung mit „a“, gefolgt von einem oder mehr Zeichen „n“. 
`\w*?` | Gleicht ein Wortzeichen nullmal oder häufiger ab, jedoch so wenige Male wie möglich.
`\b` | An einer Wortgrenze beenden.
 
### <a name="match-zero-or-one-time-"></a>Übereinstimmung mit null oder einem Vorkommen: ?

Der **?**-Quantifizierer gleicht das vorangehende Element null- oder einmal ab. Er entspricht **{0,1}**. **?** ist ein gieriger Quantifizierer, dessen träges Äquivalent **??** lautet.

Beispielsweise versucht der reguläre Ausdruck `\ban?\b` ganze Wörter abzugleichen, die mit dem Buchstaben `a` beginnen, gefolgt von null oder einer Instanz des Buchstabens `n`. Das heißt, er versucht, die Wörter `a` und `an` abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.

```csharp
string pattern = @"\ban?\b";
string input = "An amiable animal with a large snount and an animated nose.";
foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:   
//        'An' found at position 0.
//        'a' found at position 23.
//        'an' found at position 42.
```

```vb
Dim pattern As String = "\ban?\b"
Dim input As String = "An amiable animal with a large snount and an animated nose."
For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next  
' The example displays the following output:   
'       'An' found at position 0.
'       'a' found at position 23.
'       'an' found at position 42.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`an?` | Übereinstimmung mit „a“, gefolgt von null oder einem Zeichen „n“. 
`\b` | An einer Wortgrenze beenden.
 
### <a name="match-exactly-n-times-n"></a>Übereinstimmung mit genau n Vorkommen: {n}

Der **{**_n_**}**-Quantifizierer gleicht das vorangehende Element genau *n*-mal ab, wobei *n* für eine beliebige ganze Zahl steht. **{**_n_**}** ist ein gieriger Quantifizierer, dessen träges Äquivalent **{**_n_**}?** lautet.

Beispielsweise versucht der reguläre Ausdruck `\b\d+\,\d{3}\b`, eine Wortgrenze, gefolgt von einer oder mehreren Dezimalziffern, gefolgt von drei Dezimalziffern, gefolgt von einer Wortgrenze abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. 

```csharp
string pattern = @"\b\d+\,\d{3}\b";
string input = "Sales totaled 103,524 million in January, " + 
                      "106,971 million in February, but only " + 
                      "943 million in March.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:   
//        '103,524' found at position 14.
//        '106,971' found at position 45.
```

```vb
Dim pattern As String = "\b\d+\,\d{3}\b"
Dim input As String = "Sales totaled 103,524 million in January, " + _
                      "106,971 million in February, but only " + _
                      "943 million in March."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:   
'       '103,524' found at position 14.
'       '106,971' found at position 45.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`\d+` | Entsprechung für mindestens eine Dezimalstelle finden. 
`\,` | Übereinstimmung mit einem Kommazeichen.
`\d{3}` | Entsprechung für drei Dezimalstellen finden.
`\b` | An einer Wortgrenze beenden.
 
### <a name="match-at-least-n-times-n"></a>Übereinstimmung mit mindestens n Vorkommen: {n,}

Der **{**_n_**}**-Quantifizierer gleicht das vorangehende Element mindestens *n*-mal ab, wobei *n* für eine beliebige ganze Zahl steht. **{**_n_**,}** ist ein gieriger Quantifizierer, dessen träges Äquivalent **{**_n_**}?** lautet.

Beispielsweise versucht der reguläre Ausdruck `\b\d{2,}\b\D+`, eine Wortgrenze, gefolgt von mindestens zwei Ziffern, gefolgt von einer Wortgrenze und einer Nicht-Dezimalziffer abzugleichen. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht. Der reguläre Ausdruck kann den Ausdruck „7 Tage“ nicht abgleichen, da er nur eine Dezimalziffer enthält, findet aber erfolgreich Übereinstimmungen mit den Phrasen „10 Wochen“ und „300 Jahre“.

```csharp
string pattern = @"\b\d{2,}\b\D+";   
string input = "7 days, 10 weeks, 300 years";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '10 weeks, ' found at position 8.
// 
``` 

```vb
Dim pattern As String = "\b\d{2,}\b\D+"  
 Dim input As String = "7 days, 10 weeks, 300 years"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '10 weeks, ' found at position 8.
'       '300 years' found at position 18.
      '300 years' found at position 18.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`\d{2,}` | Übereinstimmung mit mindestens zwei Dezimalziffern. 
`\b` | Übereinstimmung mit einer Wortgrenze.
`\D+` | Übereinstimmung mit mindestens einer Nicht-Dezimalziffer.
 
### <a name="match-between-n-and-m-times-nm"></a>Übereinstimmung mit n bis m Vorkommen: {n,m}

Der **{**_n_**,**_m_**}**-Quantifizierer gleicht das vorangehende Element mindestens *n*-mal, aber nicht mehr als *m*-mal ab, wobei *n* und *m* ganze Zahlen sind. **{**_n_**,**_m_**}** ist ein gieriger Quantifizierer, dessen träges Äquivalent **{**_n_**,**_m_**}?** lautet.

Im folgenden Beispiel versucht der reguläre Ausdruck `(00\s){2,4}`, zwei bis vier Vorkommen zweier&0;-Ziffern, gefolgt von einem Leerzeichen, abzugleichen. Beachten Sie, dass der letzte Teil der Eingabezeichenfolge dieses Muster fünfmal enthält und damit das Maximum von vier überschreitet. Allerdings stimmt nur der erste Teil dieser Teilzeichenfolge (bis zum Leerzeichen und fünften Nullpaar) mit dem Muster für reguläre Ausdrücke überein.

```csharp
string pattern = @"(00\s){2,4}";
string input = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        '00 00 ' found at position 8.
//        '00 00 00 ' found at position 23.
//        '00 00 00 00 ' found at position 35.
```

```vb
Dim pattern As String = "(00\s){2,4}"
Dim input As String = "0x00 FF 00 00 18 17 FF 00 00 00 21 00 00 00 00 00"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       '00 00 ' found at position 8.
'       '00 00 00 ' found at position 23.
'       '00 00 00 00 ' found at position 35.
```

### <a name="match-zero-or-more-times-lazy-match-"></a>Übereinstimmung mit null oder mehr Vorkommen (träger Abgleich): \*?

Der Quantifizierer **\*?** gleicht das vorangehende Element nullmal oder häufiger ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer **\***.

Im folgenden Beispiel gleicht der reguläre Ausdruck `\b\w*?oo\w*?\b` alle Wörter ab, die die Zeichenfolge `oo` enthalten. 

```csharp
 string pattern = @"\b\w*?oo\w*?\b";
 string input = "woof root root rob oof woo woe";
 foreach (Match match in Regex.Matches(input, pattern, RegexOptions.IgnoreCase))
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

 //  The example displays the following output:
//        'woof' found at position 0.
//        'root' found at position 5.
//        'root' found at position 10.
//        'oof' found at position 19.
//        'woo' found at position 23.
```

```vb
Dim pattern As String = "\b\w*?oo\w*?\b"
 Dim input As String = "woof root root rob oof woo woe"
 For Each match As Match In Regex.Matches(input, pattern, RegexOptions.IgnoreCase)
    Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
 Next 
 ' The example displays the following output:
'       'woof' found at position 0.
'       'root' found at position 5.
'       'root' found at position 10.
'       'oof' found at position 19.
'       'woo' found at position 23.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`\b` | An einer Wortgrenze beginnen.
`\w*?` | Übereinstimmung mit null oder mehr Wortzeichen, aber so wenigen Zeichen wie möglich. 
`oo` | Übereinstimmung mit der Zeichenfolge „Oo“.
`\w*?` | Übereinstimmung mit null oder mehr Wortzeichen, aber so wenigen Zeichen wie möglich.
`\b` | An einer Wortgrenze beenden.
 
### <a name="match-one-or-more-times-lazy-match-"></a>Übereinstimmung mit einem oder mehr Vorkommen (träger Abgleich): +?

Der **+?**-Quantifizierer gleicht das vorangehende Element einmal oder häufiger ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer **+**.

Beispielsweise gleicht der reguläre Ausdruck `\b\w+?\b` ein oder mehr Zeichen ab, die durch Wortgrenzen getrennt sind. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.

```csharp
string pattern = @"\b\w+?\b";
string input = "Aa Bb Cc Dd Ee Ff";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Aa' found at position 0.
//        'Bb' found at position 3.
//        'Cc' found at position 6.
//        'Dd' found at position 9.
//        'Ee' found at position 12.
//        'Ff' found at position 15.
```

```vb
Dim pattern As String = "\b\w+?\b"
 Dim input As String = "Aa Bb Cc Dd Ee Ff"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Aa' found at position 0.
'       'Bb' found at position 3.
'       'Cc' found at position 6.
'       'Dd' found at position 9.
'       'Ee' found at position 12.
'       'Ff' found at position 15.
```

### <a name="match-zero-or-one-time-lazy-match-"></a>Übereinstimmung mit null oder einem Vorkommen (träger Abgleich): ??

Der **??**-Quantifizierer gleicht das vorangehende Element null- oder einmal ab, jedoch so wenige Male wie möglich. Dies ist das träge Gegenstück zum gierigen Quantifizierer **?**.

Beispielsweise versucht der reguläre Ausdruck `^\s*(System.)??Console.Write(Line)??\(??`, die Zeichenfolgen „Console.Write“ oder „Console.WriteLine“ abzugleichen. Die Zeichenfolge kann auch „System.“ vor „Console“ enthalten und von einer öffnenden Klammer gefolgt sein. Die Zeichenfolge muss sich am Anfang einer Zeile befinden, ihr kann jedoch ein Leerzeichen vorangestellt sein. Im folgenden Beispiel wird dieser reguläre Ausdruck veranschaulicht.

```csharp
string pattern = @"^\s*(System.)??Console.Write(Line)??\(??";
string input = "System.Console.WriteLine(\"Hello!\")\n" + 
                      "Console.Write(\"Hello!\")\n" + 
                      "Console.WriteLine(\"Hello!\")\n" + 
                      "Console.ReadLine()\n" + 
                      "   Console.WriteLine";
foreach (Match match in Regex.Matches(input, pattern, 
                                      RegexOptions.IgnorePatternWhitespace | 
                                      RegexOptions.IgnoreCase | 
                                      RegexOptions.Multiline))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'System.Console.Write' found at position 0.
//        'Console.Write' found at position 36.
//        'Console.Write' found at position 61.
//        '   Console.Write' found at position 110.
```

```vb
Dim pattern As String = "^\s*(System.)??Console.Write(Line)??\(??"
Dim input As String = "System.Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.Write(""Hello!"")" + vbCrLf + _
                      "Console.WriteLine(""Hello!"")" + vbCrLf + _
                      "Console.ReadLine()" + vbCrLf + _
                      "   Console.WriteLine"
For Each match As Match In Regex.Matches(input, pattern, _
                                         RegexOptions.IgnorePatternWhitespace Or RegexOptions.IgnoreCase Or RegexOptions.MultiLine)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'System.Console.Write' found at position 0.
'       'Console.Write' found at position 36.
'       'Console.Write' found at position 61.
'       '   Console.Write' found at position 110.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | ----------- 
`^` | Übereinstimmung mit dem Beginn des Eingabestreams.
`\s*` | Sucht nach&0; (null) oder mehr Leerzeichen.
`(System.)??` | Übereinstimmung mit null oder einem Vorkommen der Zeichenfolge „System.“.
`Console.Write` | Übereinstimmung mit der Zeichenfolge „Console.Write“.
`(Line)??` | Übereinstimmung mit null oder einem Vorkommen der Zeichenfolge „Line“.
`\(??` | Übereinstimmung mit null oder einem Vorkommen der öffnenden Klammer.
 
### <a name="match-exactly-n-times-lazy-match-n"></a>Übereinstimmung mit genau n Vorkommen (träger Abgleich): {n}?

Der **{**_n_**}?**-Quantifizierer gleicht das vorangehende Element genau *n*-mal ab, wobei *n* für eine beliebige ganze Zahl steht. Dies ist das träge Gegenstück zum gierigen Quantifizierer **{**_n_**}+**.

Im folgenden Beispiel wird der reguläre Ausdruck `\b(\w{3,}?\.){2}?\w{3,}?\b` verwendet, um die Adresse einer Website zu identifizieren. Beachten Sie, dass „www.microsoft.com“ und „msdn.microsoft.com“ abgeglichen werden, aber nicht „mywebsite“ oder „mycompany.com“.

```csharp
string pattern = @"\b(\w{3,}?\.){2}?\w{3,}?\b";
string input = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'www.microsoft.com' found at position 0.
//        'msdn.microsoft.com' found at position 18.
```

```vb
Dim pattern As String = "\b(\w{3,}?\.){2}?\w{3,}?\b"
 Dim input As String = "www.microsoft.com msdn.microsoft.com mywebsite mycompany.com"
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next     
' The example displays the following output:
'       'www.microsoft.com' found at position 0.
'       'msdn.microsoft.com' found at position 18.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`(\w{3,}?\.)` | Übereinstimmung mit mindestens 3 Wortzeichen, aber so wenigen Zeichen wie möglich, gefolgt von einem Punktzeichen. Dies ist die erste Erfassungsgruppe.
`(\w{3,}?\.){2}?` | Übereinstimmung mit zwei Vorkommen im Muster in der ersten Gruppe, jedoch so wenige Male wie möglich.
`\b` | Beendet den Vergleich an einer Wortgrenze.
 
### <a name="match-at-least-n-times-lazy-match-n"></a>Übereinstimmung mit mindestens n Vorkommen (träger Abgleich): {n,}?

Der **{**_n_**,}?**-Quantifizierer gleicht das vorangehende Element mindestens *n*-mal ab, jedoch so wenige Male wie möglich, wobei *n* für eine beliebige ganze Zahl steht. Dies ist das träge Gegenstück zum gierigen Quantifizierer **{**_n_**,}**.

Eine Abbildung finden Sie im Beispiel für den **{**_n_**}?**-Quantifizierer im vorherigen Abschnitt. Der reguläre Ausdruck in diesem Beispiel verwendet den **{**_n_**,}**-Quantifizierer, um eine Zeichenfolge abzugleichen, die mindestens drei Zeichen umfasst, gefolgt von einem Punkt.

### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Übereinstimmung mit n bis m Vorkommen (träger Abgleich): {n,m}?

Der **{**_n_**,**_m_**}?**-Quantifizierer gleicht das vorangehende Element *n*- bis *m*-mal ab, jedoch so wenige Male wie möglich, wobei *n* und *m* für ganze Zahlen stehen. Dies ist das träge Gegenstück zum gierigen Quantifizierer **{**_n_**,**_m_**}**.

Im folgenden Beispiel gleicht der reguläre Ausdruck `\b[A-Z](\w*\s+){1,10}?[.!?]` Sätze ab, die zwischen ein und zehn Wörter enthalten. Er gleicht alle Sätze in der Eingabezeichenfolge ab mit Ausnahme eines Satzes, der 18 Wörter enthält.

```csharp
string pattern = @"\b[A-Z](\w*?\s*?){1,10}[.!?]";
string input = "Hi. I am writing a short note. Its purpose is " + 
                      "to test a regular expression that attempts to find " + 
                      "sentences with ten or fewer words. Most sentences " + 
                      "in this note are short.";
foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

//  The example displays the following output:
//        'Hi.' found at position 0.
//        'I am writing a short note.' found at position 4.
//        'Most sentences in this note are short.' found at position 132.
```

```vb
Dim pattern As String = "\b[A-Z](\w*\s?){1,10}?[.!?]"
Dim input As String = "Hi. I am writing a short note. Its purpose is " + _
                      "to test a regular expression that attempts to find " + _
                      "sentences with ten or fewer words. Most sentences " + _
                      "in this note are short."
For Each match As Match In Regex.Matches(input, pattern)
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index)
Next 
' The example displays the following output:
'       'Hi.' found at position 0.
'       'I am writing a short note.' found at position 4.
'       'Most sentences in this note are short.' found at position 132.
```

Das Muster für reguläre Ausdrücke ist wie in der folgenden Tabelle gezeigt definiert.

Muster | Beschreibung
------- | -----------
`\b` | An einer Wortgrenze beginnen.
`[A-Z]` | Übereinstimmung mit einem Großbuchstaben von A bis Z.
`(\w*\s+)` | Übereinstimmung mit null oder mehr Wortzeichen, gefolgt von einem oder mehreren Leerzeichen. Dies ist die erste Erfassungsgruppe.
`{1,10}?` | Übereinstimmung mit dem vorhergehenden Muster zwischen 1- und 10-mal, jedoch so wenige Male wie möglich.
`[.!?]` | Übereinstimmung mit einem der Interpunktionszeichen „.“, „!“ oder „?“.
 
## <a name="greedy-and-lazy-quantifiers"></a>Gierige und träge Quantifizierer

Eine Reihe von Quantifizierern gibt es in zwei Versionen: 

* Eine gierige Version. 

  Ein gieriger Quantifizierer versucht, ein Element so oft wie möglich abzugleichen. 


* •Eine nicht gierige (oder träge) Version. 

 Ein nicht gieriger Quantifizierer versucht, ein Element so selten wie möglich abzugleichen. Sie können einen gierigen Quantifizierer in einen trägen Quantifizierer umwandeln, indem Sie einfach ein **?** hinzufügen.

Nehmen Sie einen einfachen regulären Ausdruck, der die letzten vier Ziffern aus einer Zeichenfolge mit Zahlen extrahieren soll, beispielsweise aus einer Kreditkartennummer. Die Version des regulären Ausdrucks, die den gierigen **\***-Quantifizierer verwendet, ist `\b.*([0-9]{4})\b`. Wenn eine Zeichenfolge zwei Zahlen enthält, gleicht dieser reguläre Ausdruck jedoch nur die letzten vier Ziffern der zweiten Zahl ab, wie im folgenden Beispiel gezeigt.

```csharp
string greedyPattern = @"\b.*([0-9]{4})\b";
string input1 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input1, greedyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******1999.
```

```vb
Dim greedyPattern As String = "\b.*([0-9]{4})\b"
Dim input1 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input1, greedypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next
' The example displays the following output:
'       Account ending in ******1999.
```

Der reguläre Ausdruck kann die erste Zahl nicht abgleichen, da der **\***-Quantifizierer versucht, das vorherige Element so oft wie möglich in der gesamten Zeichenfolge abzugleichen. Daher wird die Übereinstimmung am Ende der Zeichenfolge gefunden.

Dies entspricht nicht dem gewünschten Verhalten. Stattdessen können Sie den trägen Quantifizierer **\*?** verwenden, um Ziffern aus beiden Zahlen zu extrahieren, wie im folgenden Beispiel veranschaulicht.

```csharp
string lazyPattern = @"\b.*?([0-9]{4})\b";
string input2 = "1112223333 3992991999";
foreach (Match match in Regex.Matches(input2, lazyPattern))
   Console.WriteLine("Account ending in ******{0}.", match.Groups[1].Value);

// The example displays the following output:
//       Account ending in ******3333.
//       Account ending in ******1999.
```

```vb
Dim lazyPattern As String = "\b.*?([0-9]{4})\b"
Dim input2 As String = "1112223333 3992991999"
For Each match As Match In Regex.Matches(input2, lazypattern)
   Console.WriteLine("Account ending in ******{0}.", match.Groups(1).Value)
Next     
' The example displays the following output:
'       Account ending in ******3333.
'       Account ending in ******1999.
```

In den meisten Fällen werden von regulären Ausdrücken mit gierigen und trägen Quantifizierern die gleichen Übereinstimmungen zurückgegeben. Im Allgemeinen geben sie unterschiedliche Ergebnisse zurück, wenn sie mit dem Platzhaltermetazeichen (**.**) verwendet werden, das jedes beliebige Zeichen abgleicht. 

## <a name="quantifiers-and-empty-matches"></a>Quantifizierer und leere Übereinstimmungen

Die Quantifizierer **\***, **+**, und **{**_n_**,**_m_**}** sowie ihre trägen Gegenstücke werden nach einer leeren Übereinstimmung nie wiederholt, wenn die Mindestanzahl von Erfassungen gefunden wurde. Diese Regel verhindert, dass Quantifizierer bei leeren Teilausdruckübereinstimmungen in Endlosschleifen geraten, wenn die maximale Anzahl möglicher Gruppenerfassungen unendlich oder nahezu unendlich ist.

Der folgende Code zeigt z.B. das Ergebnis eines Aufrufs der [Regex.Match](xref:System.Text.RegularExpressions.Regex.Match(System.String))-Methode mit dem Muster für reguläre Ausdrücke `(a?)*,`, bei dem null oder ein Zeichen „a“ nullmal oder häufiger abgeglichen wird. Beachten Sie, dass die einzelne Erfassungsgruppe jedes „a“ sowie [String.Empty](xref:System.String.Empty) abgleicht, dass es aber keine zweite leere Übereinstimmung gibt, weil der Quantifizierer nach der ersten leeren Übereinstimmung nicht mehr wiederholt wird.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern = "(a?)*";
      string input = "aaabbb";
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         GroupCollection groups = match.Groups;
         for (int grpCtr = 1; grpCtr <= groups.Count - 1; grpCtr++) {
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups[grpCtr].Value,
                              groups[grpCtr].Index);
            int captureCtr = 0;
            foreach (Capture capture in groups[grpCtr].Captures) {
               captureCtr++;
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index);
            }
         } 
      }   
   }
}
// The example displays the following output:
//       Match: 'aaa' at index 0
//          Group 1: '' at index 3
//             Capture 1: 'a' at index 0
//             Capture 2: 'a' at index 1
//             Capture 3: 'a' at index 2
//             Capture 4: '' at index 3
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern As String = "(a?)*"
      Dim input As String = "aaabbb"
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at index {1}", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         Dim groups As GroupCollection = match.Groups
         For grpCtr As Integer = 1 To groups.Count - 1
            Console.WriteLine("   Group {0}: '{1}' at index {2}", 
                              grpCtr, 
                              groups(grpCtr).Value,
                              groups(grpCtr).Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In groups(grpCtr).Captures
               captureCtr += 1
               Console.WriteLine("      Capture {0}: '{1}' at index {2}", 
                                 captureCtr, capture.Value, capture.Index)
            Next
         Next 
      End If   
   End Sub
End Module
' The example displays the following output:
'       Match: 'aaa' at index 0
'          Group 1: '' at index 3
'             Capture 1: 'a' at index 0
'             Capture 2: 'a' at index 1
'             Capture 3: 'a' at index 2
'             Capture 4: '' at index 3
```

Um den praktischen Unterschied zwischen einer Erfassungsgruppe, die eine Mindest- und eine Höchstzahl von Erfassungen definiert, und einer Erfassungsgruppe zu sehen, die eine feste Anzahl von Erfassungen definiert, betrachten Sie die Muster für reguläre Ausdrücke `(a\1|(?(1)\1)){0,2}` und `(a\1|(?(1)\1)){2}`. Beide reguläre Ausdrücke bestehen aus einer einzelnen Erfassungsgruppe, die wie in der folgenden Tabelle gezeigt definiert ist. 

Muster | Beschreibung
------- | -----------
`(a\1` | Entweder „a“ zusammen mit dem Wert der ersten Erfassungsgruppe abgleichen...
`&#124;(?(1)` | … oder testen, ob die erste Erfassungsgruppe definiert wurde. (Beachten Sie, dass das **(?(1)**-Konstrukt keine Erfassungsgruppe definiert.)
`\1))` | Wenn die erste Erfassungsgruppe vorhanden ist, deren Wert abgleichen. Wenn die Gruppe nicht vorhanden ist, gleicht die Gruppe [String.Empty](xref:System.String.Empty) ab. 
 
Der erste reguläre Ausdruck versucht, dieses Muster zwischen null- und zweimal abzugleichen; der zweite Ausdruck genau zweimal. Da das erste Muster die minimale Anzahl von Erfassungen mit der ersten Erfassung von [String.Empty](xref:System.String.Empty) erreicht, wird es nie wiederholt, um `a\1;` abzugleichen. Der `{0,2}`-Quantifizierer erlaubt nur leere Übereinstimmungen in der letzten Iteration. Im Gegensatz dazu gleicht der zweite reguläre Ausdruck „a“ ab, weil `a\1` ein zweites Mal ausgewertet wird; die Mindestanzahl von Iterationen (2) zwingt das Modul nach einer leeren Übereinstimmung zur Wiederholung.

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string pattern, input;

      pattern = @"(a\1|(?(1)\1)){0,2}";
      input = "aaabbb"; 

      Console.WriteLine("Regex pattern: {0}", pattern);
      Match match = Regex.Match(input, pattern);
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
      Console.WriteLine();

      pattern = @"(a\1|(?(1)\1)){2}";
      Console.WriteLine("Regex pattern: {0}", pattern);
      match = Regex.Match(input, pattern);
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index);
      if (match.Groups.Count > 1) {
         for (int groupCtr = 1; groupCtr <= match.Groups.Count - 1; groupCtr++)
         {
            Group group = match.Groups[groupCtr];         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index);
            int captureCtr = 0;
            foreach (Capture capture in group.Captures) {
               captureCtr++;
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index);
            }   
         }
      }
   }
}
// The example displays the following output:
//       Regex pattern: (a\1|(?(1)\1)){0,2}
//       Match: '' at position 0.
//          Group: 1: '' at position 0.
//             Capture: 1: '' at position 0.
//       
//       Regex pattern: (a\1|(?(1)\1)){2}
//       Matched 'a' at position 0.
//          Group: 1: 'a' at position 0.
//             Capture: 1: '' at position 0.
//             Capture: 2: 'a' at position 0.
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim pattern, input As String

      pattern = "(a\1|(?(1)\1)){0,2}"
      input = "aaabbb" 

      Console.WriteLine("Regex pattern: {0}", pattern)
      Dim match As Match = Regex.Match(input, pattern)
      Console.WriteLine("Match: '{0}' at position {1}.", 
                        match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
      Console.WriteLine()

      pattern = "(a\1|(?(1)\1)){2}"
      Console.WriteLine("Regex pattern: {0}", pattern)
      match = Regex.Match(input, pattern)
         Console.WriteLine("Matched '{0}' at position {1}.", 
                           match.Value, match.Index)
      If match.Groups.Count > 1 Then
         For groupCtr As Integer = 1 To match.Groups.Count - 1
            Dim group As Group = match.Groups(groupCtr)         
            Console.WriteLine("   Group: {0}: '{1}' at position {2}.", 
                              groupCtr, group.Value, group.Index)
            Dim captureCtr As Integer = 0
            For Each capture As Capture In group.Captures
               captureCtr += 1
               Console.WriteLine("      Capture: {0}: '{1}' at position {2}.", 
                                 captureCtr, capture.Value, capture.Index)
            Next   
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Regex pattern: (a\1|(?(1)\1)){0,2}
'       Match: '' at position 0.
'          Group: 1: '' at position 0.
'             Capture: 1: '' at position 0.
'       
'       Regex pattern: (a\1|(?(1)\1)){2}
'       Matched 'a' at position 0.
'          Group: 1: 'a' at position 0.
'             Capture: 1: '' at position 0.
'             Capture: 2: 'a' at position 0.
```

## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)

[Backtracking in regulären Ausdrücken](backtracking.md)


