---
title: Literale (F#)
description: Erfahren Sie, bis die Literaltypen in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: e6d34acd928edce8447c793105b08085ab0757b9
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "44087624"
---
# <a name="literals"></a>Literale

> [!NOTE]
Die API-Referenz-Links in diesem Artikel gelangen Sie zu MSDN (für den Moment).

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
|String oder byte[]|wörtliche Zeichenfolge|@-Präfix|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="remarks"></a>Hinweise

Unicode-Zeichenfolgen können explizite Codierungen, die Sie angeben können, indem Sie mithilfe von enthalten `\u` gefolgt von einem hexadezimalen 16-Bit-Code oder UTF-32-Codierungen, die Sie angeben können, indem Sie mithilfe von `\U` gefolgt von eine hexadezimale 32-Bit-Code, der eine Unicode-darstellt das Ersatzzeichenpaar.

Ab F# 3.1, können Sie die `+` melden Sie beim Kombinieren von Zeichenfolgenliteralen. Sie können auch das bitweise verwenden oder (`|||`) Operator, um Enumerationsflags zu kombinieren. In F# 3.1 ist beispielsweise der folgende Code zulässig:

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

32-Bit-Ganzzahlen mit Vorzeichen können auch angegeben werden, mithilfe von hexadezimalen, Oktal- oder binäre eine `0x`, `0o` oder `0b` bzw. voranstellen.

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Unterstriche in numerischen Literalen

Ab F# 4.1, können Sie Ziffern mit einem Unterstrich trennen (`_`).

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a>Siehe auch

- [Core.LiteralAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
