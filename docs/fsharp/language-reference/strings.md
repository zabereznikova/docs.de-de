---
title: Zeichenfolgen
description: "Erfahren Sie, wie der F #-Typ ' String ' als Sequenz von Unicode-Zeichen unveränderlichen Text darstellt."
ms.date: 08/15/2020
ms.openlocfilehash: f6ec36feeb197bf785c702e7b626cf5cf80696ab
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812210"
---
# <a name="strings"></a><span data-ttu-id="5a865-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5a865-103">Strings</span></span>

<span data-ttu-id="5a865-104">Der- `string` Typ stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="5a865-104">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="5a865-105">`string` ist ein Alias für `System.String` in .NET.</span><span class="sxs-lookup"><span data-stu-id="5a865-105">`string` is an alias for `System.String` in .NET.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a865-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a865-106">Remarks</span></span>

<span data-ttu-id="5a865-107">Zeichen folgen Literale werden durch das Anführungszeichen (") getrennt.</span><span class="sxs-lookup"><span data-stu-id="5a865-107">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="5a865-108">Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu codieren.</span><span class="sxs-lookup"><span data-stu-id="5a865-108">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="5a865-109">Der umgekehrte Schrägstrich und das nächste Zeichen werden als *Escapesequenz*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5a865-109">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="5a865-110">In F #-Zeichenfolgenliteralen unterstützte Escapesequenzen werden in der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a865-110">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="5a865-111">Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-111">Character</span></span>|<span data-ttu-id="5a865-112">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="5a865-112">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="5a865-113">Warnung</span><span class="sxs-lookup"><span data-stu-id="5a865-113">Alert</span></span>|`\a`|
|<span data-ttu-id="5a865-114">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="5a865-114">Backspace</span></span>|`\b`|
|<span data-ttu-id="5a865-115">Seitenvorschub</span><span class="sxs-lookup"><span data-stu-id="5a865-115">Form feed</span></span>|`\f`|
|<span data-ttu-id="5a865-116">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="5a865-116">Newline</span></span>|`\n`|
|<span data-ttu-id="5a865-117">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="5a865-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="5a865-118">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="5a865-118">Tab</span></span>|`\t`|
|<span data-ttu-id="5a865-119">Vertikaler Tabulator</span><span class="sxs-lookup"><span data-stu-id="5a865-119">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="5a865-120">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="5a865-120">Backslash</span></span>|`\\`|
|<span data-ttu-id="5a865-121">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-121">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="5a865-122">Apostroph</span><span class="sxs-lookup"><span data-stu-id="5a865-122">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="5a865-123">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-123">Unicode character</span></span>|<span data-ttu-id="5a865-124">`\DDD` (wobei `D` eine Dezimal Ziffer angibt; Bereich von 000-255, z. b. `\231` = "ç")</span><span class="sxs-lookup"><span data-stu-id="5a865-124">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="5a865-125">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-125">Unicode character</span></span>|<span data-ttu-id="5a865-126">`\xHH` (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 00-FF, z. b. `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="5a865-126">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="5a865-127">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-127">Unicode character</span></span>|<span data-ttu-id="5a865-128">`\uHHHH` (UTF-16) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 0000-FFFF;  Beispiel: `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="5a865-128">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="5a865-129">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-129">Unicode character</span></span>|<span data-ttu-id="5a865-130">`\U00HHHHHH` (UTF-32) (wobei `H` eine hexadezimale Ziffer angibt; Bereich von 000000-10FFFF;  Beispiel: `\U0001F47D` = " 👽 ")</span><span class="sxs-lookup"><span data-stu-id="5a865-130">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="5a865-131">Die `\DDD` Escapesequenz ist eine Dezimal Schreibweise, keine oktale Notation wie in den meisten anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="5a865-131">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="5a865-132">Daher sind Ziffern `8` und `9` gültig, und eine Sequenz von `\032` stellt ein Leerzeichen (U + 0020) dar, während derselbe Codepunkt in der Oktalnotation ist `\040` .</span><span class="sxs-lookup"><span data-stu-id="5a865-132">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="5a865-133">Die Beschränkung auf einen Bereich von 0-255 (0xFF), die Escapesequenzen `\DDD` und `\x` sind effektiv der [ISO-8859-1-](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) Zeichensatz, da dieser mit den ersten 256 Unicode-Code Punkten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="5a865-133">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="5a865-134">Wörtliche Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="5a865-134">Verbatim Strings</span></span>

<span data-ttu-id="5a865-135">Wenn das @-Symbol vorangestellt ist, ist das Literale eine wörtliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5a865-135">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="5a865-136">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="5a865-136">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="5a865-137">Zeichen folgen mit drei Zeichen</span><span class="sxs-lookup"><span data-stu-id="5a865-137">Triple Quoted Strings</span></span>

<span data-ttu-id="5a865-138">Außerdem kann eine Zeichenfolge durch dreifache Anführungszeichen eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="5a865-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="5a865-139">In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich doppelter Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="5a865-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="5a865-140">Zum Angeben einer Zeichenfolge, die eine eingebettete Zeichenfolge in Anführungszeichen enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge mit drei Anführungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a865-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="5a865-141">Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen angeben, um ein einzelnes Anführungszeichen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5a865-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="5a865-142">Wenn Sie eine Zeichenfolge mit drei Anführungszeichen verwenden, können Sie die einfachen Anführungszeichen verwenden, ohne Sie als Ende der Zeichenfolge zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="5a865-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="5a865-143">Diese Technik kann nützlich sein, wenn Sie mit XML oder anderen Strukturen arbeiten, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a865-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="5a865-144">Im Code werden Zeichen folgen, die Zeilenumbrüche aufweisen, akzeptiert, und die Zeilenumbrüche werden buchstäblich als Zeilenumbruch interpretiert, es sei denn, ein umgekehrter Schrägstrich ist das letzte Zeichen vor dem Zeilenumbruch.</span><span class="sxs-lookup"><span data-stu-id="5a865-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="5a865-145">Führende Leerzeichen in der nächsten Zeile werden ignoriert, wenn der umgekehrte Schrägstrich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a865-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="5a865-146">Der folgende Code erzeugt eine Zeichenfolge `str1` , die über `"abc\ndef"` einen-Wert und eine Zeichenfolge mit- `str2` Wert verfügt `"abcdef"` .</span><span class="sxs-lookup"><span data-stu-id="5a865-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="5a865-147">Indizierung und Slicing von Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="5a865-147">String Indexing and Slicing</span></span>

<span data-ttu-id="5a865-148">Sie können in einer Zeichenfolge auf einzelne Zeichen zugreifen, indem Sie wie folgt eine Array ähnliche Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="5a865-148">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="5a865-149">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="5a865-149">The output is `b`.</span></span>

<span data-ttu-id="5a865-150">Sie können auch Teil Zeichenfolgen extrahieren, indem Sie die Array Slice-Syntax verwenden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5a865-150">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="5a865-151">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5a865-151">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="5a865-152">Sie können ASCII-Zeichen folgen nach Arrays nicht signierter Bytes darstellen, indem Sie eingeben `byte[]` .</span><span class="sxs-lookup"><span data-stu-id="5a865-152">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="5a865-153">Fügen Sie das Suffix `B` einem Zeichenfolgenliteralzeichen hinzu, um anzugeben, dass es sich um eine ASCII-</span><span class="sxs-lookup"><span data-stu-id="5a865-153">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="5a865-154">ASCII-Zeichenfolgenliterale, die mit Byte Arrays verwendet werden, unterstützen die gleichen Escapesequenzen wie Unicode-Zeichen folgen, mit Ausnahme der</span><span class="sxs-lookup"><span data-stu-id="5a865-154">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="5a865-155">Zeichen folgen Operatoren</span><span class="sxs-lookup"><span data-stu-id="5a865-155">String Operators</span></span>

<span data-ttu-id="5a865-156">Der- `+` Operator kann verwendet werden, um Zeichen folgen zu verketten und damit die Kompatibilität mit den Funktionen der .NET Framework-Zeichen folgen Behandlung aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="5a865-156">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="5a865-157">Das folgende Beispiel veranschaulicht die Verkettung von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="5a865-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="5a865-158">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="5a865-158">String Class</span></span>

<span data-ttu-id="5a865-159">Da der String-Typ in F # tatsächlich ein .NET Framework `System.String` Typ ist, sind alle Elemente `System.String` verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5a865-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="5a865-160">Dies schließt den- `+` Operator ein, der zum Verketten von Zeichen folgen, der `Length` -Eigenschaft und der-Eigenschaft verwendet wird `Chars` , die die Zeichenfolge als Array von Unicode-Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5a865-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="5a865-161">Weitere Informationen zu Zeichen folgen finden Sie unter `System.String` .</span><span class="sxs-lookup"><span data-stu-id="5a865-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="5a865-162">Mithilfe der- `Chars` Eigenschaft von `System.String` können Sie auf die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5a865-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="5a865-163">Zeichen folgen Modul</span><span class="sxs-lookup"><span data-stu-id="5a865-163">String Module</span></span>

<span data-ttu-id="5a865-164">Zusätzliche Funktionen für die Zeichen folgen Behandlung sind im- `String` Modul im- `FSharp.Core` Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a865-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="5a865-165">Weitere Informationen finden Sie unter [Zeichen folgen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span><span class="sxs-lookup"><span data-stu-id="5a865-165">For more information, see [String Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-stringmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="5a865-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a865-166">See also</span></span>

- [<span data-ttu-id="5a865-167">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="5a865-167">F# Language Reference</span></span>](index.md)
