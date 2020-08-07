---
title: Zeichenfolgen
description: "Erfahren Sie, wie der F #-Typ ' String ' als Sequenz von Unicode-Zeichen unveränderlichen Text darstellt."
ms.date: 07/05/2019
ms.openlocfilehash: 67a6506b4b8c479da1022c069a7f53402f904b4d
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855412"
---
# <a name="strings"></a>Zeichenfolgen

Der- `string` Typ stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET.

> [!NOTE]
> Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig. Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .

## <a name="remarks"></a>Bemerkungen

Zeichen folgen Literale werden durch das Anführungszeichen (") getrennt. Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu codieren. Der umgekehrte Schrägstrich und das nächste Zeichen werden als *Escapesequenz*bezeichnet. In F #-Zeichenfolgenliteralen unterstützte Escapesequenzen werden in der folgenden Tabelle gezeigt.

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
|Apostroph|`\'`|
|Unicode-Zeichen|`\DDD`(wobei `D` eine Dezimal Ziffer angibt; Bereich von 000-255, z. b. `\231` = "ç")|
|Unicode-Zeichen|`\xHH`(wobei `H` eine hexadezimale Ziffer angibt; Bereich von 00-FF, z. b. `\xE7` = "ç")|
|Unicode-Zeichen|`\uHHHH`(UTF-16) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 0000-FFFF;  Beispiel: `\u00E7` = "ç")|
|Unicode-Zeichen|`\U00HHHHHH`(UTF-32) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 000000-10FFFF;  Beispiel: `\U0001F47D` = " 👽 ")|

> [!IMPORTANT]
> Die `\DDD` Escapesequenz ist eine Dezimal Schreibweise, keine oktale Notation wie in den meisten anderen Sprachen. Daher sind Ziffern `8` und `9` gültig, und eine Sequenz von `\032` stellt ein Leerzeichen (U + 0020) dar, während derselbe Codepunkt in der Oktalnotation ist `\040` .

> [!NOTE]
> Die Beschränkung auf einen Bereich von 0-255 (0xFF), die Escapesequenzen `\DDD` und `\x` sind effektiv der [ISO-8859-1-](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) Zeichensatz, da dieser mit den ersten 256 Unicode-Code Punkten übereinstimmt.

## <a name="verbatim-strings"></a>Wörtliche Zeichen folgen

Wenn das @-Symbol vorangestellt ist, ist das Literale eine wörtliche Zeichenfolge. Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.

## <a name="triple-quoted-strings"></a>Zeichen folgen mit drei Zeichen

Außerdem kann eine Zeichenfolge durch dreifache Anführungszeichen eingeschlossen werden. In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich doppelter Anführungszeichen. Zum Angeben einer Zeichenfolge, die eine eingebettete Zeichenfolge in Anführungszeichen enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge mit drei Anführungszeichen verwenden. Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen angeben, um ein einzelnes Anführungszeichen anzugeben. Wenn Sie eine Zeichenfolge mit drei Anführungszeichen verwenden, können Sie die einfachen Anführungszeichen verwenden, ohne Sie als Ende der Zeichenfolge zu analysieren. Diese Technik kann nützlich sein, wenn Sie mit XML oder anderen Strukturen arbeiten, die eingebettete Anführungszeichen enthalten.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Im Code werden Zeichen folgen, die Zeilenumbrüche aufweisen, akzeptiert, und die Zeilenumbrüche werden buchstäblich als Zeilenumbruch interpretiert, es sei denn, ein umgekehrter Schrägstrich ist das letzte Zeichen vor dem Zeilenumbruch. Führende Leerzeichen in der nächsten Zeile werden ignoriert, wenn der umgekehrte Schrägstrich verwendet wird. Der folgende Code erzeugt eine Zeichenfolge `str1` , die über `"abc\ndef"` einen-Wert und eine Zeichenfolge mit- `str2` Wert verfügt `"abcdef"` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>Indizierung und Slicing von Zeichen folgen

Sie können in einer Zeichenfolge auf einzelne Zeichen zugreifen, indem Sie wie folgt eine Array ähnliche Syntax verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

Die Ausgabe lautet `b`.

Sie können auch Teil Zeichenfolgen extrahieren, indem Sie die Array Slice-Syntax verwenden, wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

Die Ausgabe lautet wie folgt.

```console
abc
def
```

Sie können ASCII-Zeichen folgen nach Arrays nicht signierter Bytes darstellen, indem Sie eingeben `byte[]` . Fügen Sie das Suffix `B` einem Zeichenfolgenliteralzeichen hinzu, um anzugeben, dass es sich um eine ASCII- ASCII-Zeichenfolgenliterale, die mit Byte Arrays verwendet werden, unterstützen die gleichen Escapesequenzen wie Unicode-Zeichen folgen, mit Ausnahme der

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>Zeichen folgen Operatoren

Der- `+` Operator kann verwendet werden, um Zeichen folgen zu verketten und damit die Kompatibilität mit den Funktionen der .NET Framework-Zeichen folgen Behandlung aufrechtzuerhalten. Das folgende Beispiel veranschaulicht die Verkettung von Zeichen folgen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String-Klasse

Da der String-Typ in F # tatsächlich ein .NET Framework `System.String` Typ ist, sind alle Elemente `System.String` verfügbar. Dies schließt den- `+` Operator ein, der zum Verketten von Zeichen folgen, der `Length` -Eigenschaft und der-Eigenschaft verwendet wird `Chars` , die die Zeichenfolge als Array von Unicode-Zeichen zurückgibt. Weitere Informationen zu Zeichen folgen finden Sie unter `System.String` .

Mithilfe der- `Chars` Eigenschaft von `System.String` können Sie auf die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>Zeichen folgen Modul

Zusätzliche Funktionen für die Zeichen folgen Behandlung sind im- `String` Modul im- `FSharp.Core` Namespace enthalten. Weitere Informationen finden Sie unter [Core. String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
