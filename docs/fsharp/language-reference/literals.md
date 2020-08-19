---
title: Literale
description: 'Erfahren Sie mehr über die Literaltypen in der Programmiersprache F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559153"
---
# <a name="literals"></a><span data-ttu-id="4db23-103">Literale</span><span class="sxs-lookup"><span data-stu-id="4db23-103">Literals</span></span>

<span data-ttu-id="4db23-104">Dieser Artikel enthält eine Tabelle, in der gezeigt wird, wie der Typ eines Literals in F # angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4db23-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="4db23-105">Literaltypen</span><span class="sxs-lookup"><span data-stu-id="4db23-105">Literal types</span></span>

<span data-ttu-id="4db23-106">In der folgenden Tabelle werden die Literaltypen in F# angegeben.</span><span class="sxs-lookup"><span data-stu-id="4db23-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="4db23-107">Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="4db23-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="4db23-108">type</span><span class="sxs-lookup"><span data-stu-id="4db23-108">Type</span></span>|<span data-ttu-id="4db23-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4db23-109">Description</span></span>|<span data-ttu-id="4db23-110">Suffix oder Präfix</span><span class="sxs-lookup"><span data-stu-id="4db23-110">Suffix or prefix</span></span>|<span data-ttu-id="4db23-111">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4db23-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="4db23-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="4db23-112">sbyte</span></span>|<span data-ttu-id="4db23-113">ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-113">signed 8-bit integer</span></span>|<span data-ttu-id="4db23-114">y</span><span class="sxs-lookup"><span data-stu-id="4db23-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="4db23-115">byte</span><span class="sxs-lookup"><span data-stu-id="4db23-115">byte</span></span>|<span data-ttu-id="4db23-116">natürliche 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="4db23-117">uy</span><span class="sxs-lookup"><span data-stu-id="4db23-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="4db23-118">int16</span><span class="sxs-lookup"><span data-stu-id="4db23-118">int16</span></span>|<span data-ttu-id="4db23-119">16-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-119">signed 16-bit integer</span></span>|<span data-ttu-id="4db23-120">s</span><span class="sxs-lookup"><span data-stu-id="4db23-120">s</span></span>|`86s`|
|<span data-ttu-id="4db23-121">uint16</span><span class="sxs-lookup"><span data-stu-id="4db23-121">uint16</span></span>|<span data-ttu-id="4db23-122">ganze 16-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="4db23-123">USA</span><span class="sxs-lookup"><span data-stu-id="4db23-123">us</span></span>|`86us`|
|<span data-ttu-id="4db23-124">INT</span><span class="sxs-lookup"><span data-stu-id="4db23-124">int</span></span><br /><br /><span data-ttu-id="4db23-125">int32</span><span class="sxs-lookup"><span data-stu-id="4db23-125">int32</span></span>|<span data-ttu-id="4db23-126">32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-126">signed 32-bit integer</span></span>|<span data-ttu-id="4db23-127">l oder None</span><span class="sxs-lookup"><span data-stu-id="4db23-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="4db23-128">uint</span><span class="sxs-lookup"><span data-stu-id="4db23-128">uint</span></span><br /><br /><span data-ttu-id="4db23-129">uint32</span><span class="sxs-lookup"><span data-stu-id="4db23-129">uint32</span></span>|<span data-ttu-id="4db23-130">Ganzzahl ohne Vorzeichen 32-Bit-natürlicher Zahl</span><span class="sxs-lookup"><span data-stu-id="4db23-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="4db23-131">u oder ul</span><span class="sxs-lookup"><span data-stu-id="4db23-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="4db23-132">nativeint</span><span class="sxs-lookup"><span data-stu-id="4db23-132">nativeint</span></span>|<span data-ttu-id="4db23-133">nativer Zeiger auf eine natürliche Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="4db23-134">n</span><span class="sxs-lookup"><span data-stu-id="4db23-134">n</span></span>|`123n`|
|<span data-ttu-id="4db23-135">unativeint</span><span class="sxs-lookup"><span data-stu-id="4db23-135">unativeint</span></span>|<span data-ttu-id="4db23-136">systemeigener Zeiger als natürliche Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="4db23-137">un</span><span class="sxs-lookup"><span data-stu-id="4db23-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="4db23-138">int64</span><span class="sxs-lookup"><span data-stu-id="4db23-138">int64</span></span>|<span data-ttu-id="4db23-139">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-139">signed 64-bit integer</span></span>|<span data-ttu-id="4db23-140">L</span><span class="sxs-lookup"><span data-stu-id="4db23-140">L</span></span>|`86L`|
|<span data-ttu-id="4db23-141">uint64</span><span class="sxs-lookup"><span data-stu-id="4db23-141">uint64</span></span>|<span data-ttu-id="4db23-142">Ganzzahl ohne Vorzeichen 64-Bit-natürlicher Zahl</span><span class="sxs-lookup"><span data-stu-id="4db23-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="4db23-143">UL</span><span class="sxs-lookup"><span data-stu-id="4db23-143">UL</span></span>|`86UL`|
|<span data-ttu-id="4db23-144">single, float32</span><span class="sxs-lookup"><span data-stu-id="4db23-144">single, float32</span></span>|<span data-ttu-id="4db23-145">32-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="4db23-145">32-bit floating point number</span></span>|<span data-ttu-id="4db23-146">F oder f</span><span class="sxs-lookup"><span data-stu-id="4db23-146">F or f</span></span>|<span data-ttu-id="4db23-147">`4.14F` oder `4.14f`</span><span class="sxs-lookup"><span data-stu-id="4db23-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="4db23-148">lf</span><span class="sxs-lookup"><span data-stu-id="4db23-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="4db23-149">float; double</span><span class="sxs-lookup"><span data-stu-id="4db23-149">float; double</span></span>|<span data-ttu-id="4db23-150">64-Bit-Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="4db23-150">64-bit floating point number</span></span>|<span data-ttu-id="4db23-151">Keine</span><span class="sxs-lookup"><span data-stu-id="4db23-151">none</span></span>|<span data-ttu-id="4db23-152">`4.14` oder `2.3E+32` oder `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="4db23-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="4db23-153">LF</span><span class="sxs-lookup"><span data-stu-id="4db23-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="4db23-154">BIGINT</span><span class="sxs-lookup"><span data-stu-id="4db23-154">bigint</span></span>|<span data-ttu-id="4db23-155">ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist</span><span class="sxs-lookup"><span data-stu-id="4db23-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="4db23-156">I</span><span class="sxs-lookup"><span data-stu-id="4db23-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="4db23-157">Decimal</span><span class="sxs-lookup"><span data-stu-id="4db23-157">decimal</span></span>|<span data-ttu-id="4db23-158">als Festkommazahl oder rationale Zahl dargestellte Bruchzahl</span><span class="sxs-lookup"><span data-stu-id="4db23-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="4db23-159">M oder m</span><span class="sxs-lookup"><span data-stu-id="4db23-159">M or m</span></span>|<span data-ttu-id="4db23-160">`0.7833M` oder `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="4db23-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="4db23-161">Char</span><span class="sxs-lookup"><span data-stu-id="4db23-161">Char</span></span>|<span data-ttu-id="4db23-162">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-162">Unicode character</span></span>|<span data-ttu-id="4db23-163">Keine</span><span class="sxs-lookup"><span data-stu-id="4db23-163">none</span></span>|<span data-ttu-id="4db23-164">`'a'` oder `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="4db23-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="4db23-165">String</span><span class="sxs-lookup"><span data-stu-id="4db23-165">String</span></span>|<span data-ttu-id="4db23-166">Unicode-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4db23-166">Unicode string</span></span>|<span data-ttu-id="4db23-167">Keine</span><span class="sxs-lookup"><span data-stu-id="4db23-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="4db23-168">oder</span><span class="sxs-lookup"><span data-stu-id="4db23-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="4db23-169">oder</span><span class="sxs-lookup"><span data-stu-id="4db23-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="4db23-170">oder</span><span class="sxs-lookup"><span data-stu-id="4db23-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="4db23-171">Siehe auch [Zeichen](Strings.md)folgen.</span><span class="sxs-lookup"><span data-stu-id="4db23-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="4db23-172">byte</span><span class="sxs-lookup"><span data-stu-id="4db23-172">byte</span></span>|<span data-ttu-id="4db23-173">ASCII-Zeichen</span><span class="sxs-lookup"><span data-stu-id="4db23-173">ASCII character</span></span>|<span data-ttu-id="4db23-174">B</span><span class="sxs-lookup"><span data-stu-id="4db23-174">B</span></span>|`'a'B`|
|<span data-ttu-id="4db23-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="4db23-175">byte[]</span></span>|<span data-ttu-id="4db23-176">ASCII-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4db23-176">ASCII string</span></span>|<span data-ttu-id="4db23-177">B</span><span class="sxs-lookup"><span data-stu-id="4db23-177">B</span></span>|`"text"B`|
|<span data-ttu-id="4db23-178">String oder byte[]</span><span class="sxs-lookup"><span data-stu-id="4db23-178">String or byte[]</span></span>|<span data-ttu-id="4db23-179">wörtliche Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4db23-179">verbatim string</span></span>|<span data-ttu-id="4db23-180">@-Präfix</span><span class="sxs-lookup"><span data-stu-id="4db23-180">@ prefix</span></span>|<span data-ttu-id="4db23-181">`@"\\server\share"` Unicode-</span><span class="sxs-lookup"><span data-stu-id="4db23-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="4db23-182">`@"\\server\share"B` ASCII-</span><span class="sxs-lookup"><span data-stu-id="4db23-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="4db23-183">Benannte Literale</span><span class="sxs-lookup"><span data-stu-id="4db23-183">Named literals</span></span>

<span data-ttu-id="4db23-184">Werte, die als Konstanten gedacht sind, können mit dem [Literalattribut](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="4db23-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="4db23-185">Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4db23-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="4db23-186">In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.</span><span class="sxs-lookup"><span data-stu-id="4db23-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="4db23-187">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4db23-187">Remarks</span></span>

<span data-ttu-id="4db23-188">Unicode-Zeichen folgen können explizite Codierungen enthalten, die Sie mithilfe von `\u` gefolgt von einem 16-Bit-Hexadezimal Code (0000-FFFF) oder UTF-32-Codierungen angeben können, die Sie mithilfe von angeben können, `\U` gefolgt von 32 einem hexadezimalen 32-Bit-Code, der jeden Unicode-Codepunkt (00000000-0010FFFF) darstellt.</span><span class="sxs-lookup"><span data-stu-id="4db23-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="4db23-189">Die Verwendung anderer bitweiser Operatoren als `|||` ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4db23-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="4db23-190">Ganze Zahlen in anderen Basen</span><span class="sxs-lookup"><span data-stu-id="4db23-190">Integers in other bases</span></span>

<span data-ttu-id="4db23-191">Ganzzahlige 32-Bit-Ganzzahlen können auch in Hexadezimal-, Oktal-oder Binärdatei mit dem `0x` `0o` `0b` Präfix bzw. angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4db23-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="4db23-192">Unterstriche in numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="4db23-192">Underscores in numeric literals</span></span>

<span data-ttu-id="4db23-193">Sie können Ziffern mit dem Unterstrich () voneinander trennen `_` .</span><span class="sxs-lookup"><span data-stu-id="4db23-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
