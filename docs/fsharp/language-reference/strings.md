---
title: Zeichenfolgen
description: Erfahren Sie, wie der F#-Typ "String" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 07/05/2019
ms.openlocfilehash: b252aef7d7e6e299df8282407198714971e80cd5
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610162"
---
# <a name="strings"></a><span data-ttu-id="e79d3-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e79d3-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="e79d3-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="e79d3-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="e79d3-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="e79d3-106">Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="e79d3-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="e79d3-107">`string` ist ein Alias für `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e79d3-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="e79d3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e79d3-108">Remarks</span></span>

<span data-ttu-id="e79d3-109">Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="e79d3-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="e79d3-110">Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen codiert.</span><span class="sxs-lookup"><span data-stu-id="e79d3-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="e79d3-111">Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*.</span><span class="sxs-lookup"><span data-stu-id="e79d3-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="e79d3-112">Escape-Zeichensequenzen in unterstützt F# Zeichenfolgenliterale werden in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e79d3-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="e79d3-113">Zeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-113">Character</span></span>|<span data-ttu-id="e79d3-114">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="e79d3-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="e79d3-115">Warnung</span><span class="sxs-lookup"><span data-stu-id="e79d3-115">Alert</span></span>|`\a`|
|<span data-ttu-id="e79d3-116">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="e79d3-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="e79d3-117">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="e79d3-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="e79d3-118">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="e79d3-118">Newline</span></span>|`\n`|
|<span data-ttu-id="e79d3-119">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="e79d3-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="e79d3-120">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="e79d3-120">Tab</span></span>|`\t`|
|<span data-ttu-id="e79d3-121">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="e79d3-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="e79d3-122">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="e79d3-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="e79d3-123">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="e79d3-124">Apostrophe</span><span class="sxs-lookup"><span data-stu-id="e79d3-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="e79d3-125">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-125">Unicode character</span></span>|<span data-ttu-id="e79d3-126">`\DDD` (, in denen `D` gibt einen Dezimalwert Ziffer; Wertebereich 000 - 255, z. B. `\231` = "Ç")</span><span class="sxs-lookup"><span data-stu-id="e79d3-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; e.g. `\231` = "ç")</span></span>|
|<span data-ttu-id="e79d3-127">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-127">Unicode character</span></span>|<span data-ttu-id="e79d3-128">`\xHH` (wobei `H` gibt an, eine hexadezimale Ziffer, Bereich von 00: FF, z. B. `\xE7` = "Ç")</span><span class="sxs-lookup"><span data-stu-id="e79d3-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; e.g. `\xE7` = "ç")</span></span>|
|<span data-ttu-id="e79d3-129">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-129">Unicode character</span></span>|<span data-ttu-id="e79d3-130">`\uHHHH` (UTF-16) (wobei `H` gibt an, eine hexadezimale Ziffer; Bereich 0000 - FFFF;  z. B. `\u00E7` = "Ç")</span><span class="sxs-lookup"><span data-stu-id="e79d3-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  e.g. `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="e79d3-131">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="e79d3-131">Unicode character</span></span>|<span data-ttu-id="e79d3-132">`\U00HHHHHH` (UTF-32) (wobei `H` gibt an, eine hexadezimale Ziffer; Bereich 000000 - 10FFFF;  z. B. `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="e79d3-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  e.g. `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="e79d3-133">Die `\DDD` -Escapesequenz ist die Dezimalschreibweise, die nicht oktale Schreibweise wie in den meisten anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="e79d3-134">Aus diesem Grund Ziffern `8` und `9` gültig sind, und einer Folge von `\032` stellt ein Leerzeichen (U + 0020), es wäre, gleiche Codepunkt in der Oktalnotation `\040`.</span><span class="sxs-lookup"><span data-stu-id="e79d3-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="e79d3-135">Eingeschränkt auf einen Bereich von 0 – 255 (0xFF) die `\DDD` und `\x` Escapesequenzen sind gewissermaßen die [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) Zeichensatz, da die ersten 256 Unicode-Codepunkte entspricht.</span><span class="sxs-lookup"><span data-stu-id="e79d3-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="e79d3-136">Wenn Sie mit der @-Zeichen, das Literal ist eine ausführliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e79d3-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="e79d3-137">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e79d3-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="e79d3-138">Darüber hinaus kann eine Zeichenfolge von dreifachen Anführungszeichen umschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="e79d3-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="e79d3-139">In diesem Fall werden alle Escape-Sequenzen ignoriert, einschließlich der doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="e79d3-140">Um eine Zeichenfolge angeben, die Zeichenfolge in Anführungszeichen ein eingebettetes enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e79d3-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="e79d3-141">Wenn Sie eine ausführliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen, um anzugeben, eine einfache Anführungszeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="e79d3-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="e79d3-142">Wenn Sie eine Zeichenfolge in dreifachen Anführungszeichen verwenden, können Sie einzelne Anführungszeichen ohne diese als das Ende der Zeichenfolge analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="e79d3-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="e79d3-143">Diese Technik kann hilfreich sein, bei der Arbeit mit XML-Index oder andere Strukturen, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e79d3-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="e79d3-144">Im Code Zeichenfolgen, die Zeilenumbrüche akzeptiert werden, und die Zeilenumbrüche werden als neue Zeilen, wörtlich interpretiert, es sei denn, ein umgekehrter Schrägstrich das letzte Zeichen vor dem Zeilenumbruch ein.</span><span class="sxs-lookup"><span data-stu-id="e79d3-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="e79d3-145">Führendes Leerzeichen in der nächsten Zeile wird ignoriert, wenn der umgekehrte Schrägstrich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e79d3-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="e79d3-146">Der folgende Code erzeugt eine Zeichenfolge `str1` Wert `"abc\ndef"` und eine Zeichenfolge `str2` Wert `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="e79d3-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="e79d3-147">Sie können einzelne Zeichen in einer Zeichenfolge mithilfe einer arrayähnlichen Syntax wie folgt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="e79d3-148">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="e79d3-148">The output is `b`.</span></span>

<span data-ttu-id="e79d3-149">Oder Sie können mithilfe der Slice Arraysyntax zu verwenden, Teilzeichenfolgen extrahieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e79d3-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="e79d3-150">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="e79d3-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="e79d3-151">Sie können die ASCII-Zeichenfolgen darstellen, indem die Arrays von Bytes ohne Vorzeichen, Typ `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="e79d3-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="e79d3-152">Sie fügen Sie das Suffix `B` auf ein Zeichenfolgenliteral, um anzugeben, dass es sich um eine ASCII-Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="e79d3-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="e79d3-153">ASCII-Zeichenfolgenliterale mit Byte-Arrays unterstützt die gleichen Escapesequenzen, die als Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="e79d3-154">Zeichenfolgenoperatoren</span><span class="sxs-lookup"><span data-stu-id="e79d3-154">String Operators</span></span>

<span data-ttu-id="e79d3-155">Es gibt zwei Möglichkeiten zum Verketten von Zeichenfolgen: mithilfe der `+` Operator oder mithilfe der `^` Operator.</span><span class="sxs-lookup"><span data-stu-id="e79d3-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="e79d3-156">Die `+` -Operator erhält die Kompatibilität mit der .NET Framework-Zeichenfolge, die Funktionen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="e79d3-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="e79d3-157">Das folgende Beispiel veranschaulicht die Verkettung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="e79d3-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="e79d3-158">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="e79d3-158">String Class</span></span>

<span data-ttu-id="e79d3-159">Da der Zeichenfolgentyp in F# tatsächlich eine .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e79d3-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="e79d3-160">Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` -Eigenschaft, die die Zeichenfolge als ein Array von Unicode-Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e79d3-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="e79d3-161">Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.</span><span class="sxs-lookup"><span data-stu-id="e79d3-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="e79d3-162">Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e79d3-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="e79d3-163">String-Modul</span><span class="sxs-lookup"><span data-stu-id="e79d3-163">String Module</span></span>

<span data-ttu-id="e79d3-164">Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` -Modul in die `FSharp.Core` Namespace.</span><span class="sxs-lookup"><span data-stu-id="e79d3-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="e79d3-165">Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="e79d3-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="e79d3-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e79d3-166">See also</span></span>

- [<span data-ttu-id="e79d3-167">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="e79d3-167">F# Language Reference</span></span>](index.md)
