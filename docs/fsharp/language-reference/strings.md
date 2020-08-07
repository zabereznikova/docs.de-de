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
# <a name="strings"></a><span data-ttu-id="ffdba-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="ffdba-103">Strings</span></span>

<span data-ttu-id="ffdba-104">Der- `string` Typ stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="ffdba-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="ffdba-105">`string` ist ein Alias für `System.String` in .NET.</span><span class="sxs-lookup"><span data-stu-id="ffdba-105">`string` is an alias for `System.String` in .NET.</span></span>

> [!NOTE]
> <span data-ttu-id="ffdba-106">Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig.</span><span class="sxs-lookup"><span data-stu-id="ffdba-106">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="ffdba-107">Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="ffdba-107">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="remarks"></a><span data-ttu-id="ffdba-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ffdba-108">Remarks</span></span>

<span data-ttu-id="ffdba-109">Zeichen folgen Literale werden durch das Anführungszeichen (") getrennt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="ffdba-110">Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu codieren.</span><span class="sxs-lookup"><span data-stu-id="ffdba-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="ffdba-111">Der umgekehrte Schrägstrich und das nächste Zeichen werden als *Escapesequenz*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffdba-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="ffdba-112">In F #-Zeichenfolgenliteralen unterstützte Escapesequenzen werden in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="ffdba-113">Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-113">Character</span></span>|<span data-ttu-id="ffdba-114">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="ffdba-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="ffdba-115">Warnung</span><span class="sxs-lookup"><span data-stu-id="ffdba-115">Alert</span></span>|`\a`|
|<span data-ttu-id="ffdba-116">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="ffdba-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="ffdba-117">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="ffdba-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="ffdba-118">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="ffdba-118">Newline</span></span>|`\n`|
|<span data-ttu-id="ffdba-119">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="ffdba-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="ffdba-120">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="ffdba-120">Tab</span></span>|`\t`|
|<span data-ttu-id="ffdba-121">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="ffdba-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="ffdba-122">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="ffdba-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="ffdba-123">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="ffdba-124">Apostroph</span><span class="sxs-lookup"><span data-stu-id="ffdba-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="ffdba-125">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-125">Unicode character</span></span>|<span data-ttu-id="ffdba-126">`\DDD`(wobei `D` eine Dezimal Ziffer angibt; Bereich von 000-255, z. b. `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ffdba-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="ffdba-127">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-127">Unicode character</span></span>|<span data-ttu-id="ffdba-128">`\xHH`(wobei `H` eine hexadezimale Ziffer angibt; Bereich von 00-FF, z. b. `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ffdba-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="ffdba-129">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-129">Unicode character</span></span>|<span data-ttu-id="ffdba-130">`\uHHHH`(UTF-16) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 0000-FFFF;  Beispiel: `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ffdba-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="ffdba-131">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-131">Unicode character</span></span>|<span data-ttu-id="ffdba-132">`\U00HHHHHH`(UTF-32) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 000000-10FFFF;  Beispiel: `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="ffdba-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ffdba-133">Die `\DDD` Escapesequenz ist eine Dezimal Schreibweise, keine oktale Notation wie in den meisten anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="ffdba-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="ffdba-134">Daher sind Ziffern `8` und `9` gültig, und eine Sequenz von `\032` stellt ein Leerzeichen (U + 0020) dar, während derselbe Codepunkt in der Oktalnotation ist `\040` .</span><span class="sxs-lookup"><span data-stu-id="ffdba-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="ffdba-135">Die Beschränkung auf einen Bereich von 0-255 (0xFF), die Escapesequenzen `\DDD` und `\x` sind effektiv der [ISO-8859-1-](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) Zeichensatz, da dieser mit den ersten 256 Unicode-Code Punkten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="ffdba-136">Wörtliche Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="ffdba-136">Verbatim Strings</span></span>

<span data-ttu-id="ffdba-137">Wenn das @-Symbol vorangestellt ist, ist das Literale eine wörtliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ffdba-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="ffdba-138">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="ffdba-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="ffdba-139">Zeichen folgen mit drei Zeichen</span><span class="sxs-lookup"><span data-stu-id="ffdba-139">Triple Quoted Strings</span></span>

<span data-ttu-id="ffdba-140">Außerdem kann eine Zeichenfolge durch dreifache Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="ffdba-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="ffdba-141">In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich doppelter Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ffdba-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="ffdba-142">Zum Angeben einer Zeichenfolge, die eine eingebettete Zeichenfolge in Anführungszeichen enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge mit drei Anführungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffdba-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="ffdba-143">Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen angeben, um ein einzelnes Anführungszeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ffdba-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="ffdba-144">Wenn Sie eine Zeichenfolge mit drei Anführungszeichen verwenden, können Sie die einfachen Anführungszeichen verwenden, ohne Sie als Ende der Zeichenfolge zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="ffdba-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="ffdba-145">Diese Technik kann nützlich sein, wenn Sie mit XML oder anderen Strukturen arbeiten, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ffdba-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="ffdba-146">Im Code werden Zeichen folgen, die Zeilenumbrüche aufweisen, akzeptiert, und die Zeilenumbrüche werden buchstäblich als Zeilenumbruch interpretiert, es sei denn, ein umgekehrter Schrägstrich ist das letzte Zeichen vor dem Zeilenumbruch.</span><span class="sxs-lookup"><span data-stu-id="ffdba-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="ffdba-147">Führende Leerzeichen in der nächsten Zeile werden ignoriert, wenn der umgekehrte Schrägstrich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffdba-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="ffdba-148">Der folgende Code erzeugt eine Zeichenfolge `str1` , die über `"abc\ndef"` einen-Wert und eine Zeichenfolge mit- `str2` Wert verfügt `"abcdef"` .</span><span class="sxs-lookup"><span data-stu-id="ffdba-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="ffdba-149">Indizierung und Slicing von Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="ffdba-149">String Indexing and Slicing</span></span>

<span data-ttu-id="ffdba-150">Sie können in einer Zeichenfolge auf einzelne Zeichen zugreifen, indem Sie wie folgt eine Array ähnliche Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="ffdba-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="ffdba-151">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="ffdba-151">The output is `b`.</span></span>

<span data-ttu-id="ffdba-152">Sie können auch Teil Zeichenfolgen extrahieren, indem Sie die Array Slice-Syntax verwenden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="ffdba-153">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="ffdba-154">Sie können ASCII-Zeichen folgen nach Arrays nicht signierter Bytes darstellen, indem Sie eingeben `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="ffdba-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="ffdba-155">Fügen Sie das Suffix `B` einem Zeichenfolgenliteralzeichen hinzu, um anzugeben, dass es sich um eine ASCII-</span><span class="sxs-lookup"><span data-stu-id="ffdba-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="ffdba-156">ASCII-Zeichenfolgenliterale, die mit Byte Arrays verwendet werden, unterstützen die gleichen Escapesequenzen wie Unicode-Zeichen folgen, mit Ausnahme der</span><span class="sxs-lookup"><span data-stu-id="ffdba-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="ffdba-157">Zeichen folgen Operatoren</span><span class="sxs-lookup"><span data-stu-id="ffdba-157">String Operators</span></span>

<span data-ttu-id="ffdba-158">Der- `+` Operator kann verwendet werden, um Zeichen folgen zu verketten und damit die Kompatibilität mit den Funktionen der .NET Framework-Zeichen folgen Behandlung aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="ffdba-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="ffdba-159">Das folgende Beispiel veranschaulicht die Verkettung von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="ffdba-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="ffdba-160">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="ffdba-160">String Class</span></span>

<span data-ttu-id="ffdba-161">Da der String-Typ in F # tatsächlich ein .NET Framework `System.String` Typ ist, sind alle Elemente `System.String` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ffdba-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="ffdba-162">Dies schließt den- `+` Operator ein, der zum Verketten von Zeichen folgen, der `Length` -Eigenschaft und der-Eigenschaft verwendet wird `Chars` , die die Zeichenfolge als Array von Unicode-Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="ffdba-163">Weitere Informationen zu Zeichen folgen finden Sie unter `System.String` .</span><span class="sxs-lookup"><span data-stu-id="ffdba-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="ffdba-164">Mithilfe der- `Chars` Eigenschaft von `System.String` können Sie auf die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ffdba-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="ffdba-165">Zeichen folgen Modul</span><span class="sxs-lookup"><span data-stu-id="ffdba-165">String Module</span></span>

<span data-ttu-id="ffdba-166">Zusätzliche Funktionen für die Zeichen folgen Behandlung sind im- `String` Modul im- `FSharp.Core` Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="ffdba-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="ffdba-167">Weitere Informationen finden Sie unter [Core. String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="ffdba-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="ffdba-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ffdba-168">See also</span></span>

- [<span data-ttu-id="ffdba-169">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ffdba-169">F# Language Reference</span></span>](index.md)
