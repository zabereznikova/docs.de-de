---
title: Zeichenfolgen
description: Erfahren Sie, wie der F#-Typ "String" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 05/16/2016
ms.openlocfilehash: 5b55b0c87b6636346677b973e093e7bcba324e98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755349"
---
# <a name="strings"></a><span data-ttu-id="96b6b-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="96b6b-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="96b6b-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="96b6b-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="96b6b-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="96b6b-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="96b6b-106">Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="96b6b-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="96b6b-107">`string` ist ein Alias für `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="96b6b-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="96b6b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96b6b-108">Remarks</span></span>

<span data-ttu-id="96b6b-109">Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="96b6b-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="96b6b-110">Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen codiert.</span><span class="sxs-lookup"><span data-stu-id="96b6b-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="96b6b-111">Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*.</span><span class="sxs-lookup"><span data-stu-id="96b6b-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="96b6b-112">Escape-Zeichensequenzen in unterstützt F# Zeichenfolgenliterale werden in der folgenden Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96b6b-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="96b6b-113">Zeichen</span><span class="sxs-lookup"><span data-stu-id="96b6b-113">Character</span></span>|<span data-ttu-id="96b6b-114">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="96b6b-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="96b6b-115">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="96b6b-115">Backspace</span></span>|`\b`|
|<span data-ttu-id="96b6b-116">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="96b6b-116">Newline</span></span>|`\n`|
|<span data-ttu-id="96b6b-117">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="96b6b-117">Carriage return</span></span>|`\r`|
|<span data-ttu-id="96b6b-118">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="96b6b-118">Tab</span></span>|`\t`|
|<span data-ttu-id="96b6b-119">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="96b6b-119">Backslash</span></span>|`\\`|
|<span data-ttu-id="96b6b-120">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="96b6b-120">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="96b6b-121">Apostrophe</span><span class="sxs-lookup"><span data-stu-id="96b6b-121">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="96b6b-122">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="96b6b-122">Unicode character</span></span>|<span data-ttu-id="96b6b-123">`\uXXXX` oder `\UXXXX` (wobei `X` eine hexadezimale Ziffer angibt)</span><span class="sxs-lookup"><span data-stu-id="96b6b-123">`\uXXXX` or `\UXXXX` (where `X` indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="96b6b-124">Wenn Sie mit der @-Zeichen, das Literal ist eine ausführliche Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="96b6b-124">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="96b6b-125">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="96b6b-125">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="96b6b-126">Darüber hinaus kann eine Zeichenfolge von dreifachen Anführungszeichen umschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="96b6b-126">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="96b6b-127">In diesem Fall werden alle Escape-Sequenzen ignoriert, einschließlich der doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="96b6b-127">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="96b6b-128">Um eine Zeichenfolge angeben, die Zeichenfolge in Anführungszeichen ein eingebettetes enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="96b6b-128">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="96b6b-129">Wenn Sie eine ausführliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen, um anzugeben, eine einfache Anführungszeichen angeben.</span><span class="sxs-lookup"><span data-stu-id="96b6b-129">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="96b6b-130">Wenn Sie eine Zeichenfolge in dreifachen Anführungszeichen verwenden, können Sie einzelne Anführungszeichen ohne diese als das Ende der Zeichenfolge analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="96b6b-130">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="96b6b-131">Diese Technik kann hilfreich sein, bei der Arbeit mit XML-Index oder andere Strukturen, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="96b6b-131">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="96b6b-132">Im Code Zeichenfolgen, die Zeilenumbrüche akzeptiert werden, und die Zeilenumbrüche werden als neue Zeilen, wörtlich interpretiert, es sei denn, ein umgekehrter Schrägstrich das letzte Zeichen vor dem Zeilenumbruch ein.</span><span class="sxs-lookup"><span data-stu-id="96b6b-132">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="96b6b-133">Führendes Leerzeichen in der nächsten Zeile wird ignoriert, wenn der umgekehrte Schrägstrich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="96b6b-133">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="96b6b-134">Der folgende Code erzeugt eine Zeichenfolge `str1` Wert `"abc\ndef"` und eine Zeichenfolge `str2` Wert `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="96b6b-134">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="96b6b-135">Sie können einzelne Zeichen in einer Zeichenfolge mithilfe einer arrayähnlichen Syntax wie folgt zugreifen.</span><span class="sxs-lookup"><span data-stu-id="96b6b-135">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="96b6b-136">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="96b6b-136">The output is `b`.</span></span>

<span data-ttu-id="96b6b-137">Oder Sie können mithilfe der Slice Arraysyntax zu verwenden, Teilzeichenfolgen extrahieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96b6b-137">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="96b6b-138">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="96b6b-138">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="96b6b-139">Sie können die ASCII-Zeichenfolgen darstellen, indem die Arrays von Bytes ohne Vorzeichen, Typ `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="96b6b-139">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="96b6b-140">Sie fügen Sie das Suffix `B` auf ein Zeichenfolgenliteral, um anzugeben, dass es sich um eine ASCII-Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="96b6b-140">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="96b6b-141">ASCII-Zeichenfolgenliterale mit Byte-Arrays unterstützt die gleichen Escapesequenzen, die als Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="96b6b-141">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="96b6b-142">Zeichenfolgenoperatoren</span><span class="sxs-lookup"><span data-stu-id="96b6b-142">String Operators</span></span>

<span data-ttu-id="96b6b-143">Es gibt zwei Möglichkeiten zum Verketten von Zeichenfolgen: mithilfe der `+` Operator oder mithilfe der `^` Operator.</span><span class="sxs-lookup"><span data-stu-id="96b6b-143">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="96b6b-144">Die `+` -Operator erhält die Kompatibilität mit der .NET Framework-Zeichenfolge, die Funktionen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="96b6b-144">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="96b6b-145">Das folgende Beispiel veranschaulicht die Verkettung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="96b6b-145">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="96b6b-146">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="96b6b-146">String Class</span></span>

<span data-ttu-id="96b6b-147">Da der Zeichenfolgentyp in F# tatsächlich eine .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="96b6b-147">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="96b6b-148">Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` -Eigenschaft, die die Zeichenfolge als ein Array von Unicode-Zeichen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="96b6b-148">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="96b6b-149">Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.</span><span class="sxs-lookup"><span data-stu-id="96b6b-149">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="96b6b-150">Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="96b6b-150">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="96b6b-151">String-Modul</span><span class="sxs-lookup"><span data-stu-id="96b6b-151">String Module</span></span>

<span data-ttu-id="96b6b-152">Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` -Modul in die `FSharp.Core` Namespace.</span><span class="sxs-lookup"><span data-stu-id="96b6b-152">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="96b6b-153">Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="96b6b-153">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="96b6b-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96b6b-154">See also</span></span>

- [<span data-ttu-id="96b6b-155">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="96b6b-155">F# Language Reference</span></span>](index.md)