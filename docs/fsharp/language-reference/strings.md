---
title: Zeichenfolgen (F#)
description: Erfahren Sie, wie der f#-Typ "String" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 05/16/2016
ms.openlocfilehash: 21971602093bc84b0df47d4ae46a14fb936c28bb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43799342"
---
# <a name="strings"></a>Zeichenfolgen

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.

## <a name="remarks"></a>Hinweise

Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen ("). Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen codiert. Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*. Escape-Zeichensequenzen in F#-Zeichenfolge, die Literale in der folgenden Tabelle gezeigt werden unterstützt.

|Zeichen|Escapesequenz|
|---------|---------------|
|Rückschritt|`\b`|
|Zeilenumbruch|`\n`|
|Wagenrücklauf|`\r`|
|Registerkarte|`\t`|
|Umgekehrter Schrägstrich|`\\`|
|Anführungszeichen|`\"`|
|Apostroph|`\'`|
|Unicodezeichen|`\uXXXX` oder `\UXXXX` (wobei `X` eine hexadezimale Ziffer angibt)|

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

Da der Zeichenfolgentyp in f# tatsächlich eine .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind. Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` -Eigenschaft, die die Zeichenfolge als ein Array von Unicode-Zeichen zurückgibt. Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.

Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a>String-Modul

Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` -Modul in die `FSharp.Core` Namespace. Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
