---
title: Zeichenfolgen
description: Erfahren Sie, wie der F#-Typ "String" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 07/05/2019
ms.openlocfilehash: ec895723cc6d21a701a27b5d70d053bb681ce2b3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660595"
---
# <a name="strings"></a>Zeichenfolgen

> [!NOTE]
> Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.

## <a name="remarks"></a>Hinweise

Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen ("). Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen codiert. Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*. Escape-Zeichensequenzen in unterstützt F# Zeichenfolgenliterale werden in der folgenden Tabelle angezeigt.

|Zeichen|Escapesequenz|
|---------|---------------|
|Warnung|`\a`|
|Rückschritt|`\b`|
|Seitenvorschub|`\f`|
|Zeilenumbruch|`\n`|
|Wagenrücklauf|`\r`|
|Registerkarte|`\t`|
|Vertikaler Tabulator|`\v`|
|Umgekehrter Schrägstrich|`\\`|
|Anführungszeichen|`\"`|
|Apostrophe|`\'`|
|Unicodezeichen|`\DDD` (, in denen `D` gibt die Dezimalzahl an Ziffern, Bereich von 000 - 255, z. B. `\231` = "Ç")|
|Unicodezeichen|`\xHH` (wobei `H` gibt an, eine hexadezimale Ziffer, Bereich von 00: FF, z. B. `\xE7` = "Ç")|
|Unicodezeichen|`\uHHHH` (UTF-16) (wobei `H` gibt an, eine hexadezimale Ziffer; Bereich 0000 - FFFF;  z. B. `\u00E7` = "Ç")|
|Unicodezeichen|`\U00HHHHHH` (UTF-32) (wobei `H` gibt an, eine hexadezimale Ziffer; Bereich 000000 - 10FFFF;  z. B. `\U0001F47D` = "👽")|

> [!IMPORTANT]
> Die `\DDD` -Escapesequenz ist die Dezimalschreibweise, die nicht oktale Schreibweise wie in den meisten anderen Sprachen. Aus diesem Grund Ziffern `8` und `9` gültig sind, und einer Folge von `\032` stellt ein Leerzeichen (U + 0020), es wäre, gleiche Codepunkt in der Oktalnotation `\040`.

> [!NOTE]
> Eingeschränkt auf einen Bereich von 0 – 255 (0xFF) die `\DDD` und `\x` Escapesequenzen sind gewissermaßen die [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) Zeichensatz, da die ersten 256 Unicode-Codepunkte entspricht.

Wenn Sie mit der @-Zeichen, das Literal ist eine ausführliche Zeichenfolge. Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.

Darüber hinaus kann eine Zeichenfolge von dreifachen Anführungszeichen umschlossen sein. In diesem Fall werden alle Escape-Sequenzen ignoriert, einschließlich der doppelten Anführungszeichen. Um eine Zeichenfolge angeben, die Zeichenfolge in Anführungszeichen ein eingebettetes enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen verwenden. Wenn Sie eine ausführliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen, um anzugeben, eine einfache Anführungszeichen angeben. Wenn Sie eine Zeichenfolge in dreifachen Anführungszeichen verwenden, können Sie einzelne Anführungszeichen ohne diese als das Ende der Zeichenfolge analysiert wird. Diese Technik kann hilfreich sein, bei der Arbeit mit XML-Index oder andere Strukturen, die eingebettete Anführungszeichen enthalten.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Im Code Zeichenfolgen, die Zeilenumbrüche akzeptiert werden, und die Zeilenumbrüche werden als neue Zeilen, wörtlich interpretiert, es sei denn, ein umgekehrter Schrägstrich das letzte Zeichen vor dem Zeilenumbruch ein. Führendes Leerzeichen in der nächsten Zeile wird ignoriert, wenn der umgekehrte Schrägstrich verwendet wird. Der folgende Code erzeugt eine Zeichenfolge `str1` Wert `"abc\ndef"` und eine Zeichenfolge `str2` Wert `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

Sie können einzelne Zeichen in einer Zeichenfolge mithilfe einer arrayähnlichen Syntax wie folgt zugreifen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

Die Ausgabe lautet `b`.

Oder Sie können mithilfe der Slice Arraysyntax zu verwenden, Teilzeichenfolgen extrahieren, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

Die Ausgabe lautet wie folgt.

```
abc
def
```

Sie können die ASCII-Zeichenfolgen darstellen, indem die Arrays von Bytes ohne Vorzeichen, Typ `byte[]`. Sie fügen Sie das Suffix `B` auf ein Zeichenfolgenliteral, um anzugeben, dass es sich um eine ASCII-Zeichenfolge ist. ASCII-Zeichenfolgenliterale mit Byte-Arrays unterstützt die gleichen Escapesequenzen, die als Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Zeichenfolgenoperatoren

Es gibt zwei Möglichkeiten zum Verketten von Zeichenfolgen: mithilfe der `+` Operator oder mithilfe der `^` Operator. Die `+` -Operator erhält die Kompatibilität mit der .NET Framework-Zeichenfolge, die Funktionen zu behandeln.

Das folgende Beispiel veranschaulicht die Verkettung von Zeichenfolgen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String-Klasse

Da der Zeichenfolgentyp in F# tatsächlich eine .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind. Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` -Eigenschaft, die die Zeichenfolge als ein Array von Unicode-Zeichen zurückgibt. Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.

Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>String-Modul

Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` -Modul in die `FSharp.Core` Namespace. Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
