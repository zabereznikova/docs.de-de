---
title: "Escapezeichen in regulären Ausdrücken"
description: "Escapezeichen in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 41d35531-2af9-47d4-9780-fbc1e682fbc2
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: e4f4b9cde90a98215c0aaab6da217ff68476cf88

---

# <a name="character-escapes-in-regular-expressions"></a>Escapezeichen in regulären Ausdrücken

Der umgekehrte Schrägstrich (\) in einem regulären Ausdruck kann für eine der folgenden Optionen stehen: 

* Das darauf folgende Zeichen ist ein Sonderzeichen, wie in der Tabelle im folgenden Abschnitt gezeigt. **\b** ist z.B. ein Anker, der angibt, dass die Übereinstimmung eines regulären Ausdrucks an einer Wortgrenze beginnen soll, **\t** stellt einen Tabulator dar, und **\x020** stellt ein Leerzeichen dar.

* Ein Zeichen, das andernfalls als Sprachkonstrukt ohne Escapezeichen interpretiert werden würde, sollte als Zeichenliteral interpretiert werden. Durch eine geschweifte Klammer (**{**) wird z.B. der Beginn der Definition eines Quantifizierers angezeigt, ein von einer geschweiften Klammer (**\{**) gefolgter umgekehrter Schrägstrich dagegen gibt an, dass das Modul für reguläre Ausdrücke eine Entsprechung für die geschweifte Klammer finden soll. Auf ähnliche Weise markiert ein einzelner umgekehrter Schrägstrich den Anfang eines Sprachkonstrukts mit Escapezeichen, aber zwei umgekehrte Schrägstriche (**\\**) geben an, dass das Modul für reguläre Ausdrücke eine Entsprechung für den umgekehrten Schrägstrich finden soll.

> [!NOTE]
> Escapezeichen werden in Mustern von regulären Ausdrücken, jedoch nicht in Ersetzungsmustern erkannt. 
 
## <a name="character-escapes-in-net"></a>Escapezeichen in .NET

In der folgenden Tabelle sind die Escapezeichen aufgeführt, die von regulären Ausdrücken in .NET unterstützt werden.

Zeichen oder Sequenz | Beschreibung
--------------------- | ----------- 
Alle Zeichen außer folgenden: **. $ ^ { [ ( &#124; ) * + ? \** | Andere als die in der Spalte **Zeichen oder Sequenz** aufgelistete Zeichen haben keine spezielle Bedeutung in regulären Ausdrücken, sie stehen für sich selbst. Die in der Spalte **Zeichen oder Sequenz** enthaltenen Zeichen sind spezielle Sprachelemente regulärer Ausdrücke. Um diese in einem regulären Ausdruck abzugleichen, müssen sie mit Escapezeichen versehen oder in eine positive Zeichengruppe einbezogen werden. Der reguläre Ausdruck `\$\d+ or [$]\d+` entspricht z.B. „$1200“. 
**\a** | Entspricht dem Klingelzeichen (Warnsignal) **\u0007**.
**\b** | Entspricht in einer __[__*character*_*group*__]_-Zeichenklasse dem Rücktastenzeichen **\u0008**. (Siehe [Zeichenklassen in regulären Ausdrücken](classes.md).) Außerhalb einer Zeichenklasse ist **\b** ein Anker, der einer Wortgrenze entspricht. (Siehe [Anker in regulären Ausdrücken](anchors.md).)
**\t** | Entspricht dem Tabstoppzeichen **\u0009**.
**\r** | Entspricht dem Wagenrücklaufzeichen **\u000D**. Beachten Sie, dass **\r** ist nicht mit dem Zeilenumbruchzeichen (**\n**) identisch ist.
**\v** | Entspricht dem vertikalen Tabstoppzeichen **\u000B**.
**\f** | Entspricht dem Seitenvorschubzeichen **\u000C**.
**\n** | Entspricht einer neuen Zeile, **\u000A**.
**\e** | Entspricht dem Escapezeichen **\u001B**.
**\**_nnn_ | Entspricht einem ASCII-Zeichen, wobei „nnn“ aus zwei oder drei Ziffern besteht, die den oktalen Zeichencode darstellen. Beispielsweise stellt `\040` ein Leerzeichen dar. Dieses Konstrukt wird als Rückverweis interpretiert, wenn es nur eine Ziffer (z. B. `\2`) hat oder wenn es der Nummer einer Erfassungsgruppe entspricht. (Siehe [Rückverweiskonstrukte in regulären Ausdrücken](backreference.md).) 
**\x**_nn_ | Entspricht einem ASCII-Zeichen, wobei *nn* ein zweistelliger Hexadezimalzeichencode ist.
**\c**_X_ | Entspricht einem ASCII-Steuerzeichen, wobei *X* der Buchstabe des Steuerzeichens ist. Beispielsweise ist `\cC` STRG+C.
**\u**_nnnn_ | Entspricht einer UTF-16-Codeeinheit, deren Wert *nnnn* hexadezimal ist. **Hinweis** Das Perl 5-Escapezeichen, das zum Festlegen von Unicode verwendet wird, wird von .NET Framework nicht unterstützt. Das Perl 5-Zeichen weist das Format **\x{####…}** auf, wobei **####…** eine Reihe von Hexadezimalstellen ist. Verwenden Sie stattdessen **\u**_nnnn_. 
**\** | Folgt diesem Zeichen ein Zeichen, das nicht als Escapezeichen erkannt wird, entspricht es diesem Zeichen. `\*` entspricht beispielsweise einem Sternchen (*) und ist gleich `\x2A`.
 
## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Verwendung von Escapezeichen in einem regulären Ausdruck. Es analysiert eine Zeichenfolge, die die Namen der größten Städte der Welt und deren Einwohnerzahlen im Jahr 2009 enthält. Jeder Ortsname wird durch ein Tabstoppzeichen (**\t**) oder einen senkrechten Strich (| oder `\u007c`) von der zugehörigen Einwohnerzahl getrennt. Einzelne Orte und ihre Einwohnerzahlen werden durch einen Wagenrücklauf und einen Zeilenvorschub von einander getrennt. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string delimited = @"\G(.+)[\t\u007c](.+)\r?\n";
      string input = "Mumbai, India|13,922,125\t\n" + 
                            "Shanghai, China\t13,831,900\n" + 
                            "Karachi, Pakistan|12,991,000\n" + 
                            "Delhi, India\t12,259,230\n" + 
                            "Istanbul, Turkey|11,372,613\n";
      Console.WriteLine("Population of the World's Largest Cities, 2009");
      Console.WriteLine();
      Console.WriteLine("{0,-20} {1,10}", "City", "Population");
      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, delimited))
         Console.WriteLine("{0,-20} {1,10}", match.Groups[1].Value, 
                                            match.Groups[2].Value);
   }
}
// The example displyas the following output:
//       Population of the World's Largest Cities, 2009
//       
//       City                 Population
//       
//       Mumbai, India        13,922,125
//       Shanghai, China      13,831,900
//       Karachi, Pakistan    12,991,000
//       Delhi, India         12,259,230
//       Istanbul, Turkey     11,372,613
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim delimited As String = "\G(.+)[\t\u007c](.+)\r?\n"
      Dim input As String = "Mumbai, India|13,922,125" + vbCrLf + _
                            "Shanghai, China" + vbTab + "13,831,900" + vbCrLf + _
                            "Karachi, Pakistan|12,991,000" + vbCrLf + _
                            "Delhi, India" + vbTab + "12,259,230" + vbCrLf + _
                            "Istanbul, Turkey|11,372,613" + vbCrLf
      Console.WriteLine("Population of the World's Largest Cities, 2009")
      Console.WriteLine()
      Console.WriteLine("{0,-20} {1,10}", "City", "Population")
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, delimited)
         Console.WriteLine("{0,-20} {1,10}", match.Groups(1).Value, _
                                            match.Groups(2).Value)
      Next                         
   End Sub
End Module
' The example displays the following output:
'       Population of the World's Largest Cities, 2009
'       
'       City                 Population
'       
'       Mumbai, India        13,922,125
'       Shanghai, China      13,831,900
'       Karachi, Pakistan    12,991,000
'       Delhi, India         12,259,230
'       Istanbul, Turkey     11,372,613
```

Der reguläre Ausdruck `\G(.+)[\t|\u007c](.+)\r?\n` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.

Muster | Beschreibung
------- | ----------- 
`\G` | Beginnen Sie den Abgleich an der Stelle, wo der letzte Abgleich geendet hat.
`(.+)` | Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen. Dies ist die erste Erfassungsgruppe.
`[\t\u007c]` | Entspricht einem Tabulator (**\t**) oder einen senkrechten Strich (&#124;).
`(.+)` | Entspricht einem oder mehreren die oft ausgegebene Befehlszeilen  Zeichen. Dies ist die zweite Erfassungsgruppe.
`\r?\n` | Entspricht 0 (Null) oder einem Vorkommen des Wagenrücklaufs, gefolgt von einer neuen Zeile.
 
## <a name="see-also"></a>Siehe auch

[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](quick-ref.md)




<!--HONumber=Nov16_HO3-->


