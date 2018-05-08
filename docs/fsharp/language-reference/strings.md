---
title: Zeichenfolgen (F#)
description: Erfahren Sie, wie die f#-Typ "Zeichenfolge" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 05/16/2016
ms.openlocfilehash: bdd1d1a542e70bcd95fce51e75d0c1ddffceb008
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="strings"></a>Zeichenfolgen

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar. `string` ist ein Alias für `System.String` in .NET Framework.

## <a name="remarks"></a>Hinweise
Als Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen ("). Der umgekehrte Schrägstrich (\) wird verwendet, um bestimmte Sonderzeichen zu codieren. Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*. Escape-Zeichensequenzen in F#-Zeichenfolge an, die Literale in der folgenden Tabelle gezeigt werden unterstützt.

|Zeichen|Escapesequenz|
|---------|---------------|
|Rückschritt|\b|
|Zeilenumbruch|\n|
|Wagenrücklauf|\r|
|Registerkarte|\t|
|Umgekehrter Schrägstrich|\\|
|Anführungszeichen|\"|
|Apostroph|\'|
|Unicodezeichen|\u*XXXX* oder \U*XXXXXXXX* (wobei *X* eine hexadezimale Ziffer angibt)|

Wenn vorangestellt das @-Zeichen, das Literal wörtliche Zeichenfolge ist. Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen Zeichen als ein Anführungszeichen interpretiert werden.

Darüber hinaus kann eine Zeichenfolge in dreifachen Anführungszeichen eingeschlossen sein. In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich der doppelten Anführungszeichen. Um eine Zeichenfolge angeben, die Zeichenfolge in Anführungszeichen ein eingebetteter enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen. Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen um ein einzelnes Anführungszeichen angeben angeben. Wenn Sie eine Zeichenfolge in dreifachen Anführungszeichen verwenden, können Sie einzelne Anführungszeichen ohne als das Ende der Zeichenfolge analysiert wird. Diese Technik kann hilfreich sein, bei der Arbeit mit XML-Index oder anderer Strukturen, die eingebettete Anführungszeichen enthalten.

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

Klicken Sie im Code Zeichenfolgen, die Zeilenumbrüche wurden akzeptiert werden, und die Zeilenumbrüche werden als Zeilenumbrüche, wörtlich interpretiert, es sei denn, ein umgekehrter Schrägstrich das letzte Zeichen vor der Zeilenumbruch ist. Führende Leerzeichen in der nächsten Zeile wird ignoriert, wenn der umgekehrte Schrägstrich verwendet wird. Der folgende Code erzeugt eine Zeichenfolge `str1` Wert `"abc\n     def"` und eine Zeichenfolge `str2` Wert `"abcdef"`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

Sie können einzelne Zeichen in einer Zeichenfolge mithilfe einer arrayähnlichen Syntax folgendermaßen zugreifen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

Die Ausgabe lautet `b`.

Oder Sie können mithilfe von slicesyntax Array, Teilzeichenfolgen extrahieren, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

Die Ausgabe lautet wie folgt.

```
abc
def
```

Sie können die ASCII-Zeichenfolgen darstellen, indem Arrays von Bytes ohne Vorzeichen, Typ `byte[]`. Fügen Sie das Suffix `B` auf ein Zeichenfolgenliteral, um anzugeben, dass es sich um eine ASCII-Zeichenfolge ist. ASCII-Zeichenfolgenliterale mit Bytearrays unterstützen die gleichen Escapesequenzen als Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a>Zeichenfolgen-Operatoren
Es gibt zwei Möglichkeiten zum Verketten von Zeichenfolgen: mithilfe der `+` Operator oder mithilfe der `^` Operator. Die `+` -Operator erhält die Kompatibilität mit der .NET Framework-Zeichenfolge, die Behandlung von Funktionen.

Das folgende Beispiel veranschaulicht die Verkettung von Zeichenfolgen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a>String-Klasse
Da der String-Datentyp in f# tatsächlich ein .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind. Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` Eigenschaft, die als Array von Unicode-Zeichen die Zeichenfolge zurückgibt. Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.

Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a>String-Modul
Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` Modul in die `FSharp.Core` Namespace. Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)
