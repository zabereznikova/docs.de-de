---
title: Literale
description: Erfahren Sie mehr über die Literaltypen in der F# Programmiersprache.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041030"
---
# <a name="literals"></a>Literale

> [!NOTE]
> Die API-Referenz Links in diesem Artikel gelangen zu MSDN (vorerst).

Dieses Thema enthält eine Tabelle, die erläutert, wie in F# der Typ eines Literals angegeben wird.

## <a name="literal-types"></a>Literaltypen

In der folgenden Tabelle werden die Literaltypen in F# angegeben. Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.

|Geben Sie Folgendes ein:|Beschreibung|Suffix oder Präfix|Beispiele|
|----|-----------|----------------|--------|
|sbyte|ganze 8-Bit-Zahl mit Vorzeichen|u|`86y`<br /><br />`0b00000101y`|
|byte|natürliche 8-Bit-Zahl ohne Vorzeichen|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|16-Bit-Ganzzahl mit Vorzeichen|s|`86s`|
|uint16|ganze 16-Bit-Zahl ohne Vorzeichen|mehreren|`86us`|
|int<br /><br />int32|32-Bit-Ganzzahl mit Vorzeichen|l oder None|`86`<br /><br />`86l`|
|uint<br /><br />uint32|Ganzzahl ohne Vorzeichen 32-Bit-natürlicher Zahl|u oder ul|`86u`<br /><br />`86ul`|
|nativeint|nativer Zeiger auf eine natürliche Zahl mit Vorzeichen|n|`123n`|
|unativeint|systemeigener Zeiger als natürliche Zahl ohne Vorzeichen|un|`0x00002D3Fun`|
|int64|64-Bit-Ganzzahl mit Vorzeichen|L|`86L`|
|uint64|Ganzzahl ohne Vorzeichen 64-Bit-natürlicher Zahl|UL|`86UL`|
|single, float32|32-Bit-Gleitkommazahl|F oder f|`4.14F` oder `4.14f`|
|||lf|`0x00000000lf`|
|float; double|64-Bit-Gleit Komma Zahl|Keine|`4.14`, `2.3E+32` oder `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|bigint|ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist|I|`9999999999999999999999999999I`|
|decimal|als Festkommazahl oder rationale Zahl dargestellte Bruchzahl|M oder m|`0.7833M` oder `0.7833m`|
|Char|Unicodezeichen|Keine|`'a'` oder `'\u0061'`|
|Zeichenfolge|Unicode-Zeichenfolge|Keine|`"text\n"`<br /><br />oder<br /><br />`@"c:\filename"`<br /><br />oder<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />oder<br /><br />`"string1" + "string2"`<br /><br />Siehe auch [Zeichen](Strings.md)folgen.|
|byte|ASCII-Zeichen|B|`'a'B`|
|byte[]|ASCII-Zeichenfolge|B|`"text"B`|
|String oder byte[]|wörtliche Zeichenfolge|@-Präfix|`@"\\server\share"` (Unicode)<br /><br />`@"\\server\share"B` (ASCII)|

## <a name="named-literals"></a>Benannte Literale

Werte, die als Konstanten gedacht sind, können mit dem [Literalattribut](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) gekennzeichnet werden. Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.

In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a>Hinweise

Unicode-Zeichen folgen können explizite Codierungen enthalten, die Sie angeben können, indem Sie `\u` gefolgt von einem 16-Bit-Hexadezimal Code (0000-FFFF) oder UTF-32-Codierungen angeben, die Sie mithilfe `\U` gefolgt von einem hexadezimalen 32-Bit-Code, der beliebige Unicode darstellt, angeben können. Codepunkt (00000000-0010FFFF).

Die Verwendung anderer bitweiser Operatoren als `|||` ist nicht zulässig.

## <a name="integers-in-other-bases"></a>Ganze Zahlen in anderen Basen

Ganzzahlige 32-Bit-Ganzzahlen können auch in Hexadezimal-, Oktal-oder Binärdatei mit einem `0x`, `0o` bzw. `0b`-Präfix angegeben werden.

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Unterstriche in numerischen Literalen

Sie können Ziffern mit dem Unterstrich (`_`) trennen.

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>Siehe auch

- [Core. LiteralAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
