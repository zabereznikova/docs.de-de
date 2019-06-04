---
title: Literale
description: Erfahren Sie, bis die Literaltypen in der Programmiersprache F#.
ms.date: 02/08/2019
ms.openlocfilehash: 032bc82d222cd34e7ac62e42ee4394c97d975b2e
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490978"
---
# <a name="literals"></a><span data-ttu-id="b56b2-103">Literale</span><span class="sxs-lookup"><span data-stu-id="b56b2-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="b56b2-104">Die API-Referenz-Links in diesem Artikel gelangen Sie zu MSDN (für den Moment).</span><span class="sxs-lookup"><span data-stu-id="b56b2-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="b56b2-105">Dieses Thema enthält eine Tabelle, die erläutert, wie in F# der Typ eines Literals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b56b2-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="b56b2-106">Literaltypen</span><span class="sxs-lookup"><span data-stu-id="b56b2-106">Literal Types</span></span>

<span data-ttu-id="b56b2-107">In der folgenden Tabelle werden die Literaltypen in F# angegeben.</span><span class="sxs-lookup"><span data-stu-id="b56b2-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="b56b2-108">Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="b56b2-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="b56b2-109">Typ</span><span class="sxs-lookup"><span data-stu-id="b56b2-109">Type</span></span>|<span data-ttu-id="b56b2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b56b2-110">Description</span></span>|<span data-ttu-id="b56b2-111">Suffix oder Präfix</span><span class="sxs-lookup"><span data-stu-id="b56b2-111">Suffix or prefix</span></span>|<span data-ttu-id="b56b2-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b56b2-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="b56b2-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="b56b2-113">sbyte</span></span>|<span data-ttu-id="b56b2-114">ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-114">signed 8-bit integer</span></span>|<span data-ttu-id="b56b2-115">y</span><span class="sxs-lookup"><span data-stu-id="b56b2-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="b56b2-116">byte</span><span class="sxs-lookup"><span data-stu-id="b56b2-116">byte</span></span>|<span data-ttu-id="b56b2-117">natürliche 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="b56b2-118">uy</span><span class="sxs-lookup"><span data-stu-id="b56b2-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="b56b2-119">int16</span><span class="sxs-lookup"><span data-stu-id="b56b2-119">int16</span></span>|<span data-ttu-id="b56b2-120">16-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-120">signed 16-bit integer</span></span>|<span data-ttu-id="b56b2-121">s</span><span class="sxs-lookup"><span data-stu-id="b56b2-121">s</span></span>|`86s`|
|<span data-ttu-id="b56b2-122">uint16</span><span class="sxs-lookup"><span data-stu-id="b56b2-122">uint16</span></span>|<span data-ttu-id="b56b2-123">16-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="b56b2-124">mehreren</span><span class="sxs-lookup"><span data-stu-id="b56b2-124">us</span></span>|`86us`|
|<span data-ttu-id="b56b2-125">int</span><span class="sxs-lookup"><span data-stu-id="b56b2-125">int</span></span><br /><br /><span data-ttu-id="b56b2-126">int32</span><span class="sxs-lookup"><span data-stu-id="b56b2-126">int32</span></span>|<span data-ttu-id="b56b2-127">32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-127">signed 32-bit integer</span></span>|<span data-ttu-id="b56b2-128">l oder none</span><span class="sxs-lookup"><span data-stu-id="b56b2-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="b56b2-129">uint</span><span class="sxs-lookup"><span data-stu-id="b56b2-129">uint</span></span><br /><br /><span data-ttu-id="b56b2-130">uint32</span><span class="sxs-lookup"><span data-stu-id="b56b2-130">uint32</span></span>|<span data-ttu-id="b56b2-131">32-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="b56b2-132">u oder ul</span><span class="sxs-lookup"><span data-stu-id="b56b2-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="b56b2-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="b56b2-133">nativeint</span></span>|<span data-ttu-id="b56b2-134">systemeigene Zeiger auf eine natürliche Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="b56b2-135">n</span><span class="sxs-lookup"><span data-stu-id="b56b2-135">n</span></span>|`123n`|
|<span data-ttu-id="b56b2-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="b56b2-136">unativeint</span></span>|<span data-ttu-id="b56b2-137">systemeigener Zeiger als natürliche Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="b56b2-138">un</span><span class="sxs-lookup"><span data-stu-id="b56b2-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="b56b2-139">int64</span><span class="sxs-lookup"><span data-stu-id="b56b2-139">int64</span></span>|<span data-ttu-id="b56b2-140">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-140">signed 64-bit integer</span></span>|<span data-ttu-id="b56b2-141">L</span><span class="sxs-lookup"><span data-stu-id="b56b2-141">L</span></span>|`86L`|
|<span data-ttu-id="b56b2-142">uint64</span><span class="sxs-lookup"><span data-stu-id="b56b2-142">uint64</span></span>|<span data-ttu-id="b56b2-143">64-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="b56b2-144">UL</span><span class="sxs-lookup"><span data-stu-id="b56b2-144">UL</span></span>|`86UL`|
|<span data-ttu-id="b56b2-145">single, float32</span><span class="sxs-lookup"><span data-stu-id="b56b2-145">single, float32</span></span>|<span data-ttu-id="b56b2-146">32-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="b56b2-146">32-bit floating point number</span></span>|<span data-ttu-id="b56b2-147">F oder f</span><span class="sxs-lookup"><span data-stu-id="b56b2-147">F or f</span></span>|<span data-ttu-id="b56b2-148">`4.14F` oder `4.14f`</span><span class="sxs-lookup"><span data-stu-id="b56b2-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="b56b2-149">lf</span><span class="sxs-lookup"><span data-stu-id="b56b2-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="b56b2-150">float; double</span><span class="sxs-lookup"><span data-stu-id="b56b2-150">float; double</span></span>|<span data-ttu-id="b56b2-151">64-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="b56b2-151">64-bit floating point number</span></span>|<span data-ttu-id="b56b2-152">Keine</span><span class="sxs-lookup"><span data-stu-id="b56b2-152">none</span></span>|<span data-ttu-id="b56b2-153">`4.14`, `2.3E+32` oder `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="b56b2-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="b56b2-154">LF</span><span class="sxs-lookup"><span data-stu-id="b56b2-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="b56b2-155">bigint</span><span class="sxs-lookup"><span data-stu-id="b56b2-155">bigint</span></span>|<span data-ttu-id="b56b2-156">ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist</span><span class="sxs-lookup"><span data-stu-id="b56b2-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="b56b2-157">I</span><span class="sxs-lookup"><span data-stu-id="b56b2-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="b56b2-158">decimal</span><span class="sxs-lookup"><span data-stu-id="b56b2-158">decimal</span></span>|<span data-ttu-id="b56b2-159">als Festkommazahl oder rationale Zahl dargestellte Bruchzahl</span><span class="sxs-lookup"><span data-stu-id="b56b2-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="b56b2-160">M oder m</span><span class="sxs-lookup"><span data-stu-id="b56b2-160">M or m</span></span>|<span data-ttu-id="b56b2-161">`0.7833M` oder `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="b56b2-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="b56b2-162">Char</span><span class="sxs-lookup"><span data-stu-id="b56b2-162">Char</span></span>|<span data-ttu-id="b56b2-163">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-163">Unicode character</span></span>|<span data-ttu-id="b56b2-164">Keine</span><span class="sxs-lookup"><span data-stu-id="b56b2-164">none</span></span>|`'a'`|
|<span data-ttu-id="b56b2-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b56b2-165">String</span></span>|<span data-ttu-id="b56b2-166">Unicode-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b56b2-166">Unicode string</span></span>|<span data-ttu-id="b56b2-167">Keine</span><span class="sxs-lookup"><span data-stu-id="b56b2-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="b56b2-168">oder</span><span class="sxs-lookup"><span data-stu-id="b56b2-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="b56b2-169">oder</span><span class="sxs-lookup"><span data-stu-id="b56b2-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="b56b2-170">oder</span><span class="sxs-lookup"><span data-stu-id="b56b2-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="b56b2-171">Siehe auch [Zeichenfolgen](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="b56b2-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="b56b2-172">byte</span><span class="sxs-lookup"><span data-stu-id="b56b2-172">byte</span></span>|<span data-ttu-id="b56b2-173">ASCII-Zeichen</span><span class="sxs-lookup"><span data-stu-id="b56b2-173">ASCII character</span></span>|<span data-ttu-id="b56b2-174">B</span><span class="sxs-lookup"><span data-stu-id="b56b2-174">B</span></span>|`'a'B`|
|<span data-ttu-id="b56b2-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="b56b2-175">byte[]</span></span>|<span data-ttu-id="b56b2-176">ASCII-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b56b2-176">ASCII string</span></span>|<span data-ttu-id="b56b2-177">B</span><span class="sxs-lookup"><span data-stu-id="b56b2-177">B</span></span>|`"text"B`|
|<span data-ttu-id="b56b2-178">String oder byte[]</span><span class="sxs-lookup"><span data-stu-id="b56b2-178">String or byte[]</span></span>|<span data-ttu-id="b56b2-179">wörtliche Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b56b2-179">verbatim string</span></span>|<span data-ttu-id="b56b2-180">@-Präfix</span><span class="sxs-lookup"><span data-stu-id="b56b2-180">@ prefix</span></span>|<span data-ttu-id="b56b2-181">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="b56b2-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="b56b2-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="b56b2-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="b56b2-183">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b56b2-183">Remarks</span></span>

<span data-ttu-id="b56b2-184">Unicode-Zeichenfolgen können explizite Codierungen, die Sie angeben können, indem Sie mithilfe von enthalten `\u` gefolgt von einem hexadezimalen 16-Bit-Code oder UTF-32-Codierungen, die Sie angeben können, indem Sie mithilfe von `\U` gefolgt von eine hexadezimale 32-Bit-Code, der eine Unicode-darstellt das Ersatzzeichenpaar.</span><span class="sxs-lookup"><span data-stu-id="b56b2-184">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="b56b2-185">Ab F# 3.1, können Sie die `+` melden Sie beim Kombinieren von Zeichenfolgenliteralen.</span><span class="sxs-lookup"><span data-stu-id="b56b2-185">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="b56b2-186">Sie können auch das bitweise verwenden oder (`|||`) Operator, um Enumerationsflags zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="b56b2-186">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="b56b2-187">In F# 3.1 ist beispielsweise der folgende Code zulässig:</span><span class="sxs-lookup"><span data-stu-id="b56b2-187">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="b56b2-188">Die Verwendung anderer bitweiser Operatoren ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b56b2-188">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="b56b2-189">Benannte Literale</span><span class="sxs-lookup"><span data-stu-id="b56b2-189">Named Literals</span></span>

<span data-ttu-id="b56b2-190">Werte, die Konstanten sein sollen können gekennzeichnet werden, mit der [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) Attribut.</span><span class="sxs-lookup"><span data-stu-id="b56b2-190">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="b56b2-191">Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="b56b2-191">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="b56b2-192">In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.</span><span class="sxs-lookup"><span data-stu-id="b56b2-192">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="b56b2-193">Ganze Zahlen In andere Basiszahlen</span><span class="sxs-lookup"><span data-stu-id="b56b2-193">Integers In Other Bases</span></span>

<span data-ttu-id="b56b2-194">32-Bit-Ganzzahlen mit Vorzeichen können auch angegeben werden, mithilfe von hexadezimalen, Oktal- oder binäre eine `0x`, `0o` oder `0b` bzw. voranstellen.</span><span class="sxs-lookup"><span data-stu-id="b56b2-194">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="b56b2-195">Unterstriche in numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="b56b2-195">Underscores in Numeric Literals</span></span>

<span data-ttu-id="b56b2-196">Ab F# 4.1, können Sie Ziffern mit einem Unterstrich trennen (`_`).</span><span class="sxs-lookup"><span data-stu-id="b56b2-196">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="b56b2-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b56b2-197">See also</span></span>

- [<span data-ttu-id="b56b2-198">Core.LiteralAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="b56b2-198">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
