---
title: Zeichenfolgen (F#)
description: Erfahren Sie, wie die f#-Typ "Zeichenfolge" unveränderlichen Text als Sequenz von Unicode-Zeichen darstellt.
ms.date: 05/16/2016
ms.openlocfilehash: 80c08f5b768dd826745e07b8c5726093050ab730
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207104"
---
# <a name="strings"></a><span data-ttu-id="2b213-103">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="2b213-103">Strings</span></span>

> [!NOTE]
<span data-ttu-id="2b213-104">Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.</span><span class="sxs-lookup"><span data-stu-id="2b213-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="2b213-105">Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2b213-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="2b213-106">Die `string` stellt unveränderlichen Text als Sequenz von Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="2b213-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="2b213-107">`string` ist ein Alias für `System.String` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2b213-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="2b213-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b213-108">Remarks</span></span>
<span data-ttu-id="2b213-109">Als Trennzeichen für Zeichenfolgenliterale dient das Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="2b213-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="2b213-110">Der umgekehrte Schrägstrich ( \\ ) wird verwendet, um bestimmte Sonderzeichen zu codieren.</span><span class="sxs-lookup"><span data-stu-id="2b213-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="2b213-111">Der umgekehrte Schrägstrich und das nächste Zeichen, die zusammen als bekanntermaßen eine *Escapesequenz*.</span><span class="sxs-lookup"><span data-stu-id="2b213-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="2b213-112">Escape-Zeichensequenzen in F#-Zeichenfolge an, die Literale in der folgenden Tabelle gezeigt werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b213-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="2b213-113">Zeichen</span><span class="sxs-lookup"><span data-stu-id="2b213-113">Character</span></span>|<span data-ttu-id="2b213-114">Escapesequenz</span><span class="sxs-lookup"><span data-stu-id="2b213-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="2b213-115">Rückschritt</span><span class="sxs-lookup"><span data-stu-id="2b213-115">Backspace</span></span>|<span data-ttu-id="2b213-116">\b</span><span class="sxs-lookup"><span data-stu-id="2b213-116">\b</span></span>|
|<span data-ttu-id="2b213-117">Zeilenumbruch</span><span class="sxs-lookup"><span data-stu-id="2b213-117">Newline</span></span>|<span data-ttu-id="2b213-118">\n</span><span class="sxs-lookup"><span data-stu-id="2b213-118">\n</span></span>|
|<span data-ttu-id="2b213-119">Wagenrücklauf</span><span class="sxs-lookup"><span data-stu-id="2b213-119">Carriage return</span></span>|<span data-ttu-id="2b213-120">\r</span><span class="sxs-lookup"><span data-stu-id="2b213-120">\r</span></span>|
|<span data-ttu-id="2b213-121">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="2b213-121">Tab</span></span>|<span data-ttu-id="2b213-122">\t</span><span class="sxs-lookup"><span data-stu-id="2b213-122">\t</span></span>|
|<span data-ttu-id="2b213-123">Umgekehrter Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="2b213-123">Backslash</span></span>|\\|
|<span data-ttu-id="2b213-124">Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="2b213-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="2b213-125">Apostroph</span><span class="sxs-lookup"><span data-stu-id="2b213-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="2b213-126">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="2b213-126">Unicode character</span></span>|<span data-ttu-id="2b213-127">\u*XXXX* oder \U*XXXXXXXX* (wobei *X* eine hexadezimale Ziffer angibt)</span><span class="sxs-lookup"><span data-stu-id="2b213-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="2b213-128">Wenn vorangestellt das @-Zeichen, das Literal wörtliche Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="2b213-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="2b213-129">Dies bedeutet, dass alle Escapesequenzen ignoriert werden, mit dem Unterschied, dass zwei Anführungszeichen Zeichen als ein Anführungszeichen interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="2b213-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="2b213-130">Darüber hinaus kann eine Zeichenfolge in dreifachen Anführungszeichen eingeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="2b213-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="2b213-131">In diesem Fall werden alle Escapesequenzen ignoriert, einschließlich der doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="2b213-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="2b213-132">Um eine Zeichenfolge angeben, die Zeichenfolge in Anführungszeichen ein eingebetteter enthält, können Sie entweder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="2b213-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="2b213-133">Wenn Sie eine wörtliche Zeichenfolge verwenden, müssen Sie zwei Anführungszeichen um ein einzelnes Anführungszeichen angeben angeben.</span><span class="sxs-lookup"><span data-stu-id="2b213-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="2b213-134">Wenn Sie eine Zeichenfolge in dreifachen Anführungszeichen verwenden, können Sie einzelne Anführungszeichen ohne als das Ende der Zeichenfolge analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="2b213-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="2b213-135">Diese Technik kann hilfreich sein, bei der Arbeit mit XML-Index oder anderer Strukturen, die eingebettete Anführungszeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b213-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="2b213-136">Klicken Sie im Code Zeichenfolgen, die Zeilenumbrüche wurden akzeptiert werden, und die Zeilenumbrüche werden als Zeilenumbrüche, wörtlich interpretiert, es sei denn, ein umgekehrter Schrägstrich das letzte Zeichen vor der Zeilenumbruch ist.</span><span class="sxs-lookup"><span data-stu-id="2b213-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="2b213-137">Führende Leerzeichen in der nächsten Zeile wird ignoriert, wenn der umgekehrte Schrägstrich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2b213-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="2b213-138">Der folgende Code erzeugt eine Zeichenfolge `str1` Wert `"abc\n     def"` und eine Zeichenfolge `str2` Wert `"abcdef"`.</span><span class="sxs-lookup"><span data-stu-id="2b213-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="2b213-139">Sie können einzelne Zeichen in einer Zeichenfolge mithilfe einer arrayähnlichen Syntax folgendermaßen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2b213-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="2b213-140">Die Ausgabe lautet `b`.</span><span class="sxs-lookup"><span data-stu-id="2b213-140">The output is `b`.</span></span>

<span data-ttu-id="2b213-141">Oder Sie können mithilfe von slicesyntax Array, Teilzeichenfolgen extrahieren, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b213-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="2b213-142">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2b213-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="2b213-143">Sie können die ASCII-Zeichenfolgen darstellen, indem Arrays von Bytes ohne Vorzeichen, Typ `byte[]`.</span><span class="sxs-lookup"><span data-stu-id="2b213-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="2b213-144">Fügen Sie das Suffix `B` auf ein Zeichenfolgenliteral, um anzugeben, dass es sich um eine ASCII-Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="2b213-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="2b213-145">ASCII-Zeichenfolgenliterale mit Bytearrays unterstützen die gleichen Escapesequenzen als Unicode-Zeichenfolgen, mit Ausnahme der Unicode-Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="2b213-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="2b213-146">Zeichenfolgen-Operatoren</span><span class="sxs-lookup"><span data-stu-id="2b213-146">String Operators</span></span>
<span data-ttu-id="2b213-147">Es gibt zwei Möglichkeiten zum Verketten von Zeichenfolgen: mithilfe der `+` Operator oder mithilfe der `^` Operator.</span><span class="sxs-lookup"><span data-stu-id="2b213-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="2b213-148">Die `+` -Operator erhält die Kompatibilität mit der .NET Framework-Zeichenfolge, die Behandlung von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2b213-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="2b213-149">Das folgende Beispiel veranschaulicht die Verkettung von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2b213-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="2b213-150">String-Klasse</span><span class="sxs-lookup"><span data-stu-id="2b213-150">String Class</span></span>
<span data-ttu-id="2b213-151">Da der String-Datentyp in f# tatsächlich ein .NET Framework ist `System.String` eingeben, die alle die `System.String` Member verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2b213-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="2b213-152">Dies schließt die `+` -Operator, der zum Verketten von Zeichenfolgen verwendet wird, die `Length` -Eigenschaft, und die `Chars` Eigenschaft, die als Array von Unicode-Zeichen die Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2b213-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="2b213-153">Weitere Informationen zu Zeichenfolgen finden Sie unter `System.String`.</span><span class="sxs-lookup"><span data-stu-id="2b213-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="2b213-154">Mithilfe der `Chars` Eigenschaft `System.String`, Sie können die einzelnen Zeichen in einer Zeichenfolge zugreifen, indem Sie einen Index angeben, wie im folgenden Code gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2b213-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="2b213-155">String-Modul</span><span class="sxs-lookup"><span data-stu-id="2b213-155">String Module</span></span>
<span data-ttu-id="2b213-156">Zusätzliche Funktionen für die Behandlung von Zeichenfolgen ist enthalten, der `String` Modul in die `FSharp.Core` Namespace.</span><span class="sxs-lookup"><span data-stu-id="2b213-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="2b213-157">Weitere Informationen finden Sie unter [Core.String-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="2b213-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b213-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b213-158">See Also</span></span>
[<span data-ttu-id="2b213-159">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2b213-159">F# Language Reference</span></span>](index.md)
