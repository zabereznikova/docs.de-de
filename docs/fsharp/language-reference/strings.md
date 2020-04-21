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
# <a name="strings"></a><span data-ttu-id="44263-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="44263-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="44263-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="44263-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="44263-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="44263-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="44263-106">Der `string` Typ stellt unveränderlichen Text als eine Folge von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="44263-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="44263-107">`string` ist ein Alias für `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44263-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="44263-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="44263-108">Remarks</span></span>

<span data-ttu-id="44263-109">Zeichenfolgenliterale werden durch das Anführungszeichen (") begrenzt.</span><span class="sxs-lookup"><span data-stu-id="44263-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="44263-110">Das umgekehrte Schrägstrichzeichen ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu kodieren.</span><span class="sxs-lookup"><span data-stu-id="44263-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="44263-111">Der umgekehrte Schrägstrich und das nächste Zeichen zusammen werden als *Escapesequenz*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="44263-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="44263-112">Escape-Sequenzen, die in den Zeichenfolgenliteralen von F-Zeichenfolgen unterstützt werden, werden in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44263-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="44263-113">Zeichen</span><span class="sxs-lookup"><span data-stu-id="44263-113">Character</span></span>|<span data-ttu-id="44263-114">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="44263-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="44263-115">Warnung</span><span class="sxs-lookup"><span data-stu-id="44263-115">Alert</span></span>|`\a`|
|<span data-ttu-id="44263-116">Rücktaste</span><span class="sxs-lookup"><span data-stu-id="44263-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="44263-117">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="44263-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="44263-118">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="44263-118">Newline</span></span>|`\n`|
|<span data-ttu-id="44263-119">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="44263-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="44263-120">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="44263-120">Tab</span></span>|`\t`|
|<span data-ttu-id="44263-121">Vertikaler Tabstopp</span><span class="sxs-lookup"><span data-stu-id="44263-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="44263-122">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="44263-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="44263-123">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="44263-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="44263-124">Apostroph</span><span class="sxs-lookup"><span data-stu-id="44263-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="44263-125">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="44263-125">Unicode character</span></span>|<span data-ttu-id="44263-126">`\DDD`(wo `D` eine Dezimalstelle angegeben ist; Bereich von 000 `\231` - 255; z. B. = "A")</span><span class="sxs-lookup"><span data-stu-id="44263-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="44263-127">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="44263-127">Unicode character</span></span>|<span data-ttu-id="44263-128">`\xHH`(wo `H` eine hexadezimale Ziffer angegeben ist; Bereich `\xE7` von 00 - FF; z. B. = "-")</span><span class="sxs-lookup"><span data-stu-id="44263-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="44263-129">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="44263-129">Unicode character</span></span>|<span data-ttu-id="44263-130">`\uHHHH`(UTF-16) (wo `H` eine hexadezimale Ziffer angegeben ist; Bereich von 0000 - FFFF;  z. `\u00E7` B. = "A")</span><span class="sxs-lookup"><span data-stu-id="44263-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="44263-131">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="44263-131">Unicode character</span></span>|<span data-ttu-id="44263-132">`\U00HHHHHH`(UTF-32) (wo `H` eine hexadezimale Ziffer angegeben ist; Bereich von 000000 - 10FFFF;  z. `\U0001F47D` B.👽= " ")</span><span class="sxs-lookup"><span data-stu-id="44263-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="44263-133">Die `\DDD` Escape-Sequenz ist dezimale Notation, nicht oktale Notation wie in den meisten anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="44263-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="44263-134">Daher sind `8` Ziffern `9` und gültig, und `\032` eine Sequenz von stellt ein Leerzeichen (U+0020) `\040`dar, während derselbe Codepunkt in oktaler Notation wäre .</span><span class="sxs-lookup"><span data-stu-id="44263-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="44263-135">Da die `\DDD` Sequenzen und `\x` Escapesequenzen auf einen Bereich von 0 - 255 (0xFF) beschränkt sind, sind sie effektiv der [ISO-8859-1-Zeichensatz,](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) da dieser den ersten 256 Unicode-Codepunkten entspricht.</span><span class="sxs-lookup"><span data-stu-id="44263-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="44263-136">Verbatim Strings</span><span class="sxs-lookup"><span data-stu-id="44263-136">Verbatim Strings</span></span>

<span data-ttu-id="44263-137">Wenn dem Symbol " vorangestellt wird, ist das Literal eine wörtliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="44263-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="44263-138">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit der Ausnahme, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="44263-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="44263-139">Dreifach zitierte Strings</span><span class="sxs-lookup"><span data-stu-id="44263-139">Triple Quoted Strings</span></span>

<span data-ttu-id="44263-140">Darüber hinaus kann eine Zeichenfolge durch dreifache Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="44263-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="44263-141">In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich doppelter Anführungszeichenzeichen.</span><span class="sxs-lookup"><span data-stu-id="44263-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="44263-142">Um eine Zeichenfolge anzugeben, die eine eingebettete Zeichenfolge in Anführungszeichen enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge mit dreifachem Anführungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="44263-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="44263-143">Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen angeben, um ein einfaches Anführungszeichen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="44263-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="44263-144">Wenn Sie eine Zeichenfolge mit dreifachem Anführungszeichen verwenden, können Sie die Zeichen mit einem anführungszeichen verwenden, ohne dass sie als Ende der Zeichenfolge analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="44263-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="44263-145">Diese Technik kann nützlich sein, wenn Sie mit XML oder anderen Strukturen arbeiten, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="44263-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="44263-146">Im Code werden Zeichenfolgen mit Zeilenumbrüchen akzeptiert, und die Zeilenumbrüche werden wörtlich als Zeilenumbrüche interpretiert, es sei denn, ein umgekehrter Schrägstrich ist das letzte Zeichen vor dem Zeilenumbruch.</span><span class="sxs-lookup"><span data-stu-id="44263-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="44263-147">Führender Leerraum in der nächsten Zeile wird ignoriert, wenn das umgekehrte Schrägstrichzeichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="44263-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="44263-148">Der folgende Code `str1` erzeugt eine `"abc\ndef"` Zeichenfolge `str2` mit Wert `"abcdef"`und eine Zeichenfolge mit Wert .</span><span class="sxs-lookup"><span data-stu-id="44263-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="44263-149">String-Indizierung und Slicing</span><span class="sxs-lookup"><span data-stu-id="44263-149">String Indexing and Slicing</span></span>

<span data-ttu-id="44263-150">Sie können wie folgt auf einzelne Zeichen in einer Zeichenfolge zugreifen, indem Sie die Array-ähnliche Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="44263-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="44263-151">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="44263-151">The output is `b`.</span></span>

<span data-ttu-id="44263-152">Sie können auch Teilzeichenfolgen extrahieren, indem Sie die Array-Slice-Syntax verwenden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="44263-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="44263-153">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="44263-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="44263-154">Sie können ASCII-Zeichenfolgen nach Arrays `byte[]`von nicht signierten Bytes darstellen, geben Sie ein.</span><span class="sxs-lookup"><span data-stu-id="44263-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="44263-155">Sie fügen das `B` Suffix zu einem Zeichenfolgenliteral hinzu, um anzugeben, dass es sich um eine ASCII-Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="44263-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="44263-156">ASCII-Zeichenfolgenliterale, die mit Bytearrays verwendet werden, unterstützen dieselben Escapesequenzen wie Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="44263-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="44263-157">String-Operatoren</span><span class="sxs-lookup"><span data-stu-id="44263-157">String Operators</span></span>

<span data-ttu-id="44263-158">Der `+` Operator kann zum Verketten von Zeichenfolgen verwendet werden, wobei die Kompatibilität mit den .NET Framework-Zeichenfolgenbehandlungsfeatures beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="44263-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="44263-159">Das folgende Beispiel veranschaulicht die Zeichenfolgenverkettung.</span><span class="sxs-lookup"><span data-stu-id="44263-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="44263-160">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="44263-160">String Class</span></span>

<span data-ttu-id="44263-161">Da es sich bei dem Zeichenfolgentyp `System.String` in F' tatsächlich um einen .NET Framework-Typ handelt, sind alle `System.String` Member verfügbar.</span><span class="sxs-lookup"><span data-stu-id="44263-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="44263-162">Dazu gehören `+` der Operator, der zum Verketten `Length` von Zeichenfolgen verwendet wird, die Eigenschaft und die `Chars` Eigenschaft, die die Zeichenfolge als Array von Unicode-Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="44263-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="44263-163">Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.</span><span class="sxs-lookup"><span data-stu-id="44263-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="44263-164">Mithilfe der `Chars` Eigenschaft `System.String`von können Sie auf die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="44263-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="44263-165">String-Modul</span><span class="sxs-lookup"><span data-stu-id="44263-165">String Module</span></span>

<span data-ttu-id="44263-166">Zusätzliche Funktionen für die Zeichenfolgenbehandlung sind im `String` Modul im `FSharp.Core` Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="44263-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="44263-167">Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="44263-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="44263-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44263-168">See also</span></span>

- [<span data-ttu-id="44263-169">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="44263-169">F# Language Reference</span></span>](index.md)
