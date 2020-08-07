---
title: Literale
description: 'Erfahren Sie mehr über die Literaltypen in der Programmiersprache F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855022"
---
# <a name="literals"></a>Literale

Dieser Artikel enthält eine Tabelle, in der gezeigt wird, wie der Typ eines Literals in F # angegeben wird.

> [!NOTE]
> Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig. Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="literal-types"></a>Literaltypen

In der folgenden Tabelle werden die Literaltypen in F# angegeben. Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.

|type|BESCHREIBUNG|Suffix oder Präfix|Beispiele|
|----|-----------|----------------|--------|
|sbyte|ganze 8-Bit-Zahl mit Vorzeichen|y|`86y`<br /><br />`0b00000101y`|
|byte|natürliche 8-Bit-Zahl ohne Vorzeichen|uy|`86uy`<br /><br />`0b00000101uy`|
|int16|16-Bit-Ganzzahl mit Vorzeichen|s|`86s`|
|uint16|ganze 16-Bit-Zahl ohne Vorzeichen|USA|`86us`|
|INT<br /><br />int32|32-Bit-Ganzzahl mit Vorzeichen|l oder None|`86`<br /><br />`86l`|
|uint<br /><br />uint32|Ganzzahl ohne Vorzeichen 32-Bit-natürlicher Zahl|u oder ul|`86u`<br /><br />`86ul`|
|nativeint|nativer Zeiger auf eine natürliche Zahl mit Vorzeichen|n|`123n`|
|unativeint|systemeigener Zeiger als natürliche Zahl ohne Vorzeichen|un|`0x00002D3Fun`|
|int64|64-Bit-Ganzzahl mit Vorzeichen|L|`86L`|
|uint64|Ganzzahl ohne Vorzeichen 64-Bit-natürlicher Zahl|UL|`86UL`|
|single, float32|32-Bit-Gleitkommazahl|F oder f|`4.14F` oder `4.14f`|
|||lf|`0x00000000lf`|
|float; double|64-Bit-Gleit Komma Zahl|none|`4.14` oder `2.3E+32` oder `2.3e+32`|
|||LF|`0x0000000000000000LF`|
|BIGINT|ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist|I|`9999999999999999999999999999I`|
|Decimal|als Festkommazahl oder rationale Zahl dargestellte Bruchzahl|M oder m|`0.7833M` oder `0.7833m`|
|Char|Unicode-Zeichen|none|`'a'` oder `'\u0061'`|
|String|Unicode-Zeichenfolge|none|`"text\n"`<br /><br />oder<br /><br />`@"c:\filename"`<br /><br />oder<br /><br />`"""<book title="Paradise Lost">"""`<br /><br />oder<br /><br />`"string1" + "string2"`<br /><br />Siehe auch [Zeichen](Strings.md)folgen.|
|byte|ASCII-Zeichen|B|`'a'B`|
|byte[]|ASCII-Zeichenfolge|B|`"text"B`|
|String oder byte[]|wörtliche Zeichenfolge|@-Präfix|`@"\\server\share"`Unicode-<br /><br />`@"\\server\share"B`ASCII-|

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

## <a name="remarks"></a>Bemerkungen

Unicode-Zeichen folgen können explizite Codierungen enthalten, die Sie mithilfe von `\u` gefolgt von einem 16-Bit-Hexadezimal Code (0000-FFFF) oder UTF-32-Codierungen angeben können, die Sie mithilfe von angeben können, `\U` gefolgt von 32 einem hexadezimalen 32-Bit-Code, der jeden Unicode-Codepunkt (00000000-0010FFFF) darstellt.

Die Verwendung anderer bitweiser Operatoren als `|||` ist nicht zulässig.

## <a name="integers-in-other-bases"></a>Ganze Zahlen in anderen Basen

Ganzzahlige 32-Bit-Ganzzahlen können auch in Hexadezimal-, Oktal-oder Binärdatei mit dem `0x` `0o` `0b` Präfix bzw. angegeben werden.

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a>Unterstriche in numerischen Literalen

Sie können Ziffern mit dem Unterstrich () voneinander trennen `_` .

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a>Weitere Informationen

- [Core. LiteralAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
