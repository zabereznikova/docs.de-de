---
title: Literale
description: 'Erfahren Sie mehr über die Literaltypen in der Programmiersprache F #.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855022"
---
# <a name="literals"></a><span data-ttu-id="f4c1c-103">Literale</span><span class="sxs-lookup"><span data-stu-id="f4c1c-103">Literals</span></span>

<span data-ttu-id="f4c1c-104">Dieser Artikel enthält eine Tabelle, in der gezeigt wird, wie der Typ eines Literals in F # angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="f4c1c-105">Die docs.Microsoft.com-API-Referenz für F # ist nicht fertig.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="f4c1c-106">Wenn Sie auf unterbrochene Verknüpfungen stoßen, verweisen Sie stattdessen auf die [Dokumentation der F #-Kernbibliothek](https://fsharp.github.io/fsharp-core-docs/) .</span><span class="sxs-lookup"><span data-stu-id="f4c1c-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="f4c1c-107">Literaltypen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-107">Literal types</span></span>

<span data-ttu-id="f4c1c-108">In der folgenden Tabelle werden die Literaltypen in F# angegeben.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="f4c1c-109">Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="f4c1c-110">type</span><span class="sxs-lookup"><span data-stu-id="f4c1c-110">Type</span></span>|<span data-ttu-id="f4c1c-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f4c1c-111">Description</span></span>|<span data-ttu-id="f4c1c-112">Suffix oder Präfix</span><span class="sxs-lookup"><span data-stu-id="f4c1c-112">Suffix or prefix</span></span>|<span data-ttu-id="f4c1c-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f4c1c-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="f4c1c-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="f4c1c-114">sbyte</span></span>|<span data-ttu-id="f4c1c-115">ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-115">signed 8-bit integer</span></span>|<span data-ttu-id="f4c1c-116">y</span><span class="sxs-lookup"><span data-stu-id="f4c1c-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="f4c1c-117">byte</span><span class="sxs-lookup"><span data-stu-id="f4c1c-117">byte</span></span>|<span data-ttu-id="f4c1c-118">natürliche 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="f4c1c-119">uy</span><span class="sxs-lookup"><span data-stu-id="f4c1c-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="f4c1c-120">int16</span><span class="sxs-lookup"><span data-stu-id="f4c1c-120">int16</span></span>|<span data-ttu-id="f4c1c-121">16-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-121">signed 16-bit integer</span></span>|<span data-ttu-id="f4c1c-122">s</span><span class="sxs-lookup"><span data-stu-id="f4c1c-122">s</span></span>|`86s`|
|<span data-ttu-id="f4c1c-123">uint16</span><span class="sxs-lookup"><span data-stu-id="f4c1c-123">uint16</span></span>|<span data-ttu-id="f4c1c-124">ganze 16-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="f4c1c-125">USA</span><span class="sxs-lookup"><span data-stu-id="f4c1c-125">us</span></span>|`86us`|
|<span data-ttu-id="f4c1c-126">INT</span><span class="sxs-lookup"><span data-stu-id="f4c1c-126">int</span></span><br /><br /><span data-ttu-id="f4c1c-127">int32</span><span class="sxs-lookup"><span data-stu-id="f4c1c-127">int32</span></span>|<span data-ttu-id="f4c1c-128">32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-128">signed 32-bit integer</span></span>|<span data-ttu-id="f4c1c-129">l oder None</span><span class="sxs-lookup"><span data-stu-id="f4c1c-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="f4c1c-130">uint</span><span class="sxs-lookup"><span data-stu-id="f4c1c-130">uint</span></span><br /><br /><span data-ttu-id="f4c1c-131">uint32</span><span class="sxs-lookup"><span data-stu-id="f4c1c-131">uint32</span></span>|<span data-ttu-id="f4c1c-132">Ganzzahl ohne Vorzeichen 32-Bit-natürlicher Zahl</span><span class="sxs-lookup"><span data-stu-id="f4c1c-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="f4c1c-133">u oder ul</span><span class="sxs-lookup"><span data-stu-id="f4c1c-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="f4c1c-134">nativeint</span><span class="sxs-lookup"><span data-stu-id="f4c1c-134">nativeint</span></span>|<span data-ttu-id="f4c1c-135">nativer Zeiger auf eine natürliche Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="f4c1c-136">n</span><span class="sxs-lookup"><span data-stu-id="f4c1c-136">n</span></span>|`123n`|
|<span data-ttu-id="f4c1c-137">unativeint</span><span class="sxs-lookup"><span data-stu-id="f4c1c-137">unativeint</span></span>|<span data-ttu-id="f4c1c-138">systemeigener Zeiger als natürliche Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="f4c1c-139">un</span><span class="sxs-lookup"><span data-stu-id="f4c1c-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="f4c1c-140">int64</span><span class="sxs-lookup"><span data-stu-id="f4c1c-140">int64</span></span>|<span data-ttu-id="f4c1c-141">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-141">signed 64-bit integer</span></span>|<span data-ttu-id="f4c1c-142">L</span><span class="sxs-lookup"><span data-stu-id="f4c1c-142">L</span></span>|`86L`|
|<span data-ttu-id="f4c1c-143">uint64</span><span class="sxs-lookup"><span data-stu-id="f4c1c-143">uint64</span></span>|<span data-ttu-id="f4c1c-144">Ganzzahl ohne Vorzeichen 64-Bit-natürlicher Zahl</span><span class="sxs-lookup"><span data-stu-id="f4c1c-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="f4c1c-145">UL</span><span class="sxs-lookup"><span data-stu-id="f4c1c-145">UL</span></span>|`86UL`|
|<span data-ttu-id="f4c1c-146">single, float32</span><span class="sxs-lookup"><span data-stu-id="f4c1c-146">single, float32</span></span>|<span data-ttu-id="f4c1c-147">32-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="f4c1c-147">32-bit floating point number</span></span>|<span data-ttu-id="f4c1c-148">F oder f</span><span class="sxs-lookup"><span data-stu-id="f4c1c-148">F or f</span></span>|<span data-ttu-id="f4c1c-149">`4.14F` oder `4.14f`</span><span class="sxs-lookup"><span data-stu-id="f4c1c-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="f4c1c-150">lf</span><span class="sxs-lookup"><span data-stu-id="f4c1c-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="f4c1c-151">float; double</span><span class="sxs-lookup"><span data-stu-id="f4c1c-151">float; double</span></span>|<span data-ttu-id="f4c1c-152">64-Bit-Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="f4c1c-152">64-bit floating point number</span></span>|<span data-ttu-id="f4c1c-153">none</span><span class="sxs-lookup"><span data-stu-id="f4c1c-153">none</span></span>|<span data-ttu-id="f4c1c-154">`4.14` oder `2.3E+32` oder `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="f4c1c-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="f4c1c-155">LF</span><span class="sxs-lookup"><span data-stu-id="f4c1c-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="f4c1c-156">BIGINT</span><span class="sxs-lookup"><span data-stu-id="f4c1c-156">bigint</span></span>|<span data-ttu-id="f4c1c-157">ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist</span><span class="sxs-lookup"><span data-stu-id="f4c1c-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="f4c1c-158">I</span><span class="sxs-lookup"><span data-stu-id="f4c1c-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="f4c1c-159">Decimal</span><span class="sxs-lookup"><span data-stu-id="f4c1c-159">decimal</span></span>|<span data-ttu-id="f4c1c-160">als Festkommazahl oder rationale Zahl dargestellte Bruchzahl</span><span class="sxs-lookup"><span data-stu-id="f4c1c-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="f4c1c-161">M oder m</span><span class="sxs-lookup"><span data-stu-id="f4c1c-161">M or m</span></span>|<span data-ttu-id="f4c1c-162">`0.7833M` oder `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="f4c1c-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="f4c1c-163">Char</span><span class="sxs-lookup"><span data-stu-id="f4c1c-163">Char</span></span>|<span data-ttu-id="f4c1c-164">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-164">Unicode character</span></span>|<span data-ttu-id="f4c1c-165">none</span><span class="sxs-lookup"><span data-stu-id="f4c1c-165">none</span></span>|<span data-ttu-id="f4c1c-166">`'a'` oder `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="f4c1c-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="f4c1c-167">String</span><span class="sxs-lookup"><span data-stu-id="f4c1c-167">String</span></span>|<span data-ttu-id="f4c1c-168">Unicode-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4c1c-168">Unicode string</span></span>|<span data-ttu-id="f4c1c-169">none</span><span class="sxs-lookup"><span data-stu-id="f4c1c-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="f4c1c-170">oder</span><span class="sxs-lookup"><span data-stu-id="f4c1c-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="f4c1c-171">oder</span><span class="sxs-lookup"><span data-stu-id="f4c1c-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="f4c1c-172">oder</span><span class="sxs-lookup"><span data-stu-id="f4c1c-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="f4c1c-173">Siehe auch [Zeichen](Strings.md)folgen.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="f4c1c-174">byte</span><span class="sxs-lookup"><span data-stu-id="f4c1c-174">byte</span></span>|<span data-ttu-id="f4c1c-175">ASCII-Zeichen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-175">ASCII character</span></span>|<span data-ttu-id="f4c1c-176">B</span><span class="sxs-lookup"><span data-stu-id="f4c1c-176">B</span></span>|`'a'B`|
|<span data-ttu-id="f4c1c-177">byte[]</span><span class="sxs-lookup"><span data-stu-id="f4c1c-177">byte[]</span></span>|<span data-ttu-id="f4c1c-178">ASCII-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4c1c-178">ASCII string</span></span>|<span data-ttu-id="f4c1c-179">B</span><span class="sxs-lookup"><span data-stu-id="f4c1c-179">B</span></span>|`"text"B`|
|<span data-ttu-id="f4c1c-180">String oder byte[]</span><span class="sxs-lookup"><span data-stu-id="f4c1c-180">String or byte[]</span></span>|<span data-ttu-id="f4c1c-181">wörtliche Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f4c1c-181">verbatim string</span></span>|<span data-ttu-id="f4c1c-182">@-Präfix</span><span class="sxs-lookup"><span data-stu-id="f4c1c-182">@ prefix</span></span>|<span data-ttu-id="f4c1c-183">`@"\\server\share"`Unicode-</span><span class="sxs-lookup"><span data-stu-id="f4c1c-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="f4c1c-184">`@"\\server\share"B`ASCII-</span><span class="sxs-lookup"><span data-stu-id="f4c1c-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="f4c1c-185">Benannte Literale</span><span class="sxs-lookup"><span data-stu-id="f4c1c-185">Named literals</span></span>

<span data-ttu-id="f4c1c-186">Werte, die als Konstanten gedacht sind, können mit dem [Literalattribut](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="f4c1c-187">Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="f4c1c-188">In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="f4c1c-189">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-189">Remarks</span></span>

<span data-ttu-id="f4c1c-190">Unicode-Zeichen folgen können explizite Codierungen enthalten, die Sie mithilfe von `\u` gefolgt von einem 16-Bit-Hexadezimal Code (0000-FFFF) oder UTF-32-Codierungen angeben können, die Sie mithilfe von angeben können, `\U` gefolgt von 32 einem hexadezimalen 32-Bit-Code, der jeden Unicode-Codepunkt (00000000-0010FFFF) darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="f4c1c-191">Die Verwendung anderer bitweiser Operatoren als `|||` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="f4c1c-192">Ganze Zahlen in anderen Basen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-192">Integers in other bases</span></span>

<span data-ttu-id="f4c1c-193">Ganzzahlige 32-Bit-Ganzzahlen können auch in Hexadezimal-, Oktal-oder Binärdatei mit dem `0x` `0o` `0b` Präfix bzw. angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f4c1c-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="f4c1c-194">Unterstriche in numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-194">Underscores in numeric literals</span></span>

<span data-ttu-id="f4c1c-195">Sie können Ziffern mit dem Unterstrich () voneinander trennen `_` .</span><span class="sxs-lookup"><span data-stu-id="f4c1c-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="f4c1c-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4c1c-196">See also</span></span>

- [<span data-ttu-id="f4c1c-197">Core. LiteralAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="f4c1c-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
