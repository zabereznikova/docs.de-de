---
title: Literale (F#)
description: Erfahren Sie, bis die Literaltypen in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a>Literale

> [!NOTE]
Die API-Referenz-Links in diesem Artikel auf MSDN (vorerst) gelangen Sie.

Dieses Thema enthält eine Tabelle, die erläutert, wie in F# der Typ eines Literals angegeben wird.

## <a name="literal-types"></a>Literaltypen
In der folgenden Tabelle werden die Literaltypen in F# angegeben. Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.

|Typ|Beschreibung|Suffix oder Präfix|Beispiele|
|----|-----------|----------------|--------|
|sbyte|ganze 8-Bit-Zahl mit Vorzeichen|y|`86y`<br /><br />`0b00000101y`|
|byte|natürliche 8-Bit-Zahl ohne Vorzeichen|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|16-Bit-Ganzzahl mit Vorzeichen|s|`86s`|
|uint16|16-Bit-natürliche-Zahl ohne Vorzeichen|mehreren|`86us`|
|int<br /><br />int32|32-Bit-Ganzzahl mit Vorzeichen|l oder none|`86`<br /><br />`86l`|
|uint<br /><br />uint32|32-Bit-natürliche-Zahl ohne Vorzeichen|u oder ul|`86u`<br /><br />`86ul`|
|unativeint|systemeigener Zeiger als natürliche Zahl ohne Vorzeichen|un|`0x00002D3Fun`|
|int64|64-Bit-Ganzzahl mit Vorzeichen|L|`86L`|
|uint64|64-Bit-natürliche-Zahl ohne Vorzeichen|UL|`86UL`|
|single, float32|32-Bit-Gleitkommazahl|F oder f|`4.14F` oder `4.14f`|
|||lf|`0x00000000lf`|
|float; double|64-Bit-Gleitkommazahl|Keine|`4.14`, `2.3E+32` oder `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist|I|`9999999999999999999999999999I`|
|decimal|als Festkommazahl oder rationale Zahl dargestellte Bruchzahl|M oder m|`0.7833M` oder `0.7833m`|
|Char|Unicodezeichen|Keine|`'a'`|
|Zeichenfolge|Unicode-Zeichenfolge|Keine|`"text\n"`<br /><br />oder<br /><br />`@"c:\filename"`<br /><br />oder<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />oder<br /><br />`"string1" + "string2"`<br /><br />Siehe auch [Zeichenfolgen](Strings.md).|
|byte|ASCII-Zeichen|B|`'a'B`|
|byte[]|ASCII-Zeichenfolge|B|`"text"B`|
|String oder byte[]|wörtliche Zeichenfolge|@-Präfix|`@"\\server\share"`(Unicode)<br /><br />`@"\\server\share"B`(ASCII)|

## <a name="remarks"></a>Hinweise
Unicode-Zeichenfolgen darf explizite Codierungen, bei denen Sie angeben können, indem Sie mit `\u` gefolgt von einem hexadezimalen 16-Bit-Code oder UTF-32-Codierungen, bei denen Sie angeben können, indem Sie mit `\U` gefolgt von einer 32-Bit-Hexadezimalcode, der eine Unicode-darstellt Ersatzzeichenpaar.

Ab f# 3.1, können Sie die `+` melden beim Kombinieren von Zeichenfolgenliteralen. Sie können auch das bitweise verwenden oder (`|||`) Operator, um Enumerationsflags zu kombinieren. In F# 3.1 ist beispielsweise der folgende Code zulässig:

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

Die Verwendung anderer bitweiser Operatoren ist nicht zulässig.


## <a name="named-literals"></a>Benannte Literale
Werte, die Konstanten sein sollen können gekennzeichnet werden, mit der [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) Attribut. Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.

In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.

## <a name="integers-in-other-bases"></a>Ganze Zahlen In andere Basiszahlen

32-Bit-Ganzzahlen mit Vorzeichen können auch angegeben werden, in das hexadezimale, oktale oder binäre mithilfe einer `0x`, `0o` oder `0b` bzw. Präfix.

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Unterstriche in numerische Literale

Ab f# 4.1, können Sie Ziffern mit einem Unterstrich trennen (`_`).

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>Siehe auch

[Core.LiteralAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
