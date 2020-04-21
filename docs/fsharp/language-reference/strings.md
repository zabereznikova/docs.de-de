---
title: Zeichenfolgen
description: Erfahren Sie, wie der Typ "String" von F unveränderlichen Text als folge von Unicode-Zeichen darstellt.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739573"
---
# <a name="strings"></a>Zeichenfolgen

> [!NOTE]
> Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Der `string` Typ stellt unveränderlichen Text als eine Folge von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.

## <a name="remarks"></a>Bemerkungen

Zeichenfolgenliterale werden durch das Anführungszeichen (") begrenzt. Das umgekehrte Schrägstrichzeichen ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu kodieren. Der umgekehrte Schrägstrich und das nächste Zeichen zusammen werden als *Escapesequenz*bezeichnet. Escape-Sequenzen, die in den Zeichenfolgenliteralen von F-Zeichenfolgen unterstützt werden, werden in der folgenden Tabelle angezeigt.

|Zeichen|Escapesequenz|
|---------|---------------|
|Warnung|`\a`|
|Rücktaste|`\b`|
|Seitenvorschub|`\f`|
|Zeilenumbruch|`\n`|
|Wagenrücklauf|`\r`|
|Registerkarte|`\t`|
|Vertikaler Tabstopp|`\v`|
|Umgekehrter Schrägstrich|`\\`|
|Anführungszeichen|`\"`|
|Apostroph|`\'`|
|Unicode-Zeichen|`\DDD`(wo `D` eine Dezimalstelle angegeben ist; Bereich von 000 `\231` - 255; z. B. = "A")|
|Unicode-Zeichen|`\xHH`(wo `H` eine hexadezimale Ziffer angegeben ist; Bereich `\xE7` von 00 - FF; z. B. = "-")|
|Unicode-Zeichen|`\uHHHH`(UTF-16) (wo `H` eine hexadezimale Ziffer angegeben ist; Bereich von 0000 - FFFF;  z. `\u00E7` B. = "A")|
|Unicode-Zeichen|`\U00HHHHHH`(UTF-32) (wo `H` eine hexadezimale Ziffer angegeben ist; Bereich von 000000 - 10FFFF;  z. `\U0001F47D` B.👽= " ")|

> [!IMPORTANT]
> Die `\DDD` Escape-Sequenz ist dezimale Notation, nicht oktale Notation wie in den meisten anderen Sprachen. Daher sind `8` Ziffern `9` und gültig, und `\032` eine Sequenz von stellt ein Leerzeichen (U+0020) `\040`dar, während derselbe Codepunkt in oktaler Notation wäre .

> [!NOTE]
> Da die `\DDD` Sequenzen und `\x` Escapesequenzen auf einen Bereich von 0 - 255 (0xFF) beschränkt sind, sind sie effektiv der [ISO-8859-1-Zeichensatz,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) da dieser den ersten 256 Unicode-Codepunkten entspricht.

## <a name="verbatim-strings"></a>Verbatim Strings

Wenn dem Symbol " vorangestellt wird, ist das Literal eine wörtliche Zeichenfolge. Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit der Ausnahme, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.

## <a name="triple-quoted-strings"></a>Dreifach zitierte Strings

Darüber hinaus kann eine Zeichenfolge durch dreifache Anführungszeichen eingeschlossen werden. In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich doppelter Anführungszeichenzeichen. Um eine Zeichenfolge anzugeben, die eine eingebettete Zeichenfolge in Anführungszeichen enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge mit dreifachem Anführungszeichen verwenden. Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen angeben, um ein einfaches Anführungszeichen anzuzeigen. Wenn Sie eine Zeichenfolge mit dreifachem Anführungszeichen verwenden, können Sie die Zeichen mit einem anführungszeichen verwenden, ohne dass sie als Ende der Zeichenfolge analysiert werden. Diese Technik kann nützlich sein, wenn Sie mit XML oder anderen Strukturen arbeiten, die eingebettete Anführungszeichen enthalten.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Im Code werden Zeichenfolgen mit Zeilenumbrüchen akzeptiert, und die Zeilenumbrüche werden wörtlich als Zeilenumbrüche interpretiert, es sei denn, ein umgekehrter Schrägstrich ist das letzte Zeichen vor dem Zeilenumbruch. Führender Leerraum in der nächsten Zeile wird ignoriert, wenn das umgekehrte Schrägstrichzeichen verwendet wird. Der folgende Code `str1` erzeugt eine `"abc\ndef"` Zeichenfolge `str2` mit Wert `"abcdef"`und eine Zeichenfolge mit Wert .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a>String-Indizierung und Slicing

Sie können wie folgt auf einzelne Zeichen in einer Zeichenfolge zugreifen, indem Sie die Array-ähnliche Syntax verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

Die Ausgabe lautet `b`.

Sie können auch Teilzeichenfolgen extrahieren, indem Sie die Array-Slice-Syntax verwenden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

Die Ausgabe lautet wie folgt.

```console
abc
def
```

Sie können ASCII-Zeichenfolgen nach Arrays `byte[]`von nicht signierten Bytes darstellen, geben Sie ein. Sie fügen das `B` Suffix zu einem Zeichenfolgenliteral hinzu, um anzugeben, dass es sich um eine ASCII-Zeichenfolge handelt. ASCII-Zeichenfolgenliterale, die mit Bytearrays verwendet werden, unterstützen dieselben Escapesequenzen wie Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a>String-Operatoren

Der `+` Operator kann zum Verketten von Zeichenfolgen verwendet werden, wobei die Kompatibilität mit den .NET Framework-Zeichenfolgenbehandlungsfeatures beibehalten wird. Das folgende Beispiel veranschaulicht die Zeichenfolgenverkettung.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a>String-Klasse

Da es sich bei dem Zeichenfolgentyp `System.String` in F' tatsächlich um einen .NET Framework-Typ handelt, sind alle `System.String` Member verfügbar. Dazu gehören `+` der Operator, der zum Verketten `Length` von Zeichenfolgen verwendet wird, die Eigenschaft und die `Chars` Eigenschaft, die die Zeichenfolge als Array von Unicode-Zeichen zurückgibt. Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.

Mithilfe der `Chars` Eigenschaft `System.String`von können Sie auf die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>String-Modul

Zusätzliche Funktionen für die Zeichenfolgenbehandlung sind im `String` Modul im `FSharp.Core` Namespace enthalten. Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Siehe auch

- [Sprachreferenz](index.md)
