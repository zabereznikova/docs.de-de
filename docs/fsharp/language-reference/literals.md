---
title: Literale (F#)
description: Erfahren Sie, bis die Literaltypen in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="ac228-104">Literale</span><span class="sxs-lookup"><span data-stu-id="ac228-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="ac228-105">Die API-Referenz-Links in diesem Artikel auf MSDN (vorerst) gelangen Sie.</span><span class="sxs-lookup"><span data-stu-id="ac228-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="ac228-106">Dieses Thema enthält eine Tabelle, die erläutert, wie in F# der Typ eines Literals angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ac228-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="ac228-107">Literaltypen</span><span class="sxs-lookup"><span data-stu-id="ac228-107">Literal Types</span></span>
<span data-ttu-id="ac228-108">In der folgenden Tabelle werden die Literaltypen in F# angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac228-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="ac228-109">Bei Zeichen, die Ziffern in Hexadezimalschreibweise darstellen, wird die Groß-/Kleinschreibung nicht beachtet. Bei Zeichen, die den Typ angeben, wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="ac228-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="ac228-110">Typ</span><span class="sxs-lookup"><span data-stu-id="ac228-110">Type</span></span>|<span data-ttu-id="ac228-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac228-111">Description</span></span>|<span data-ttu-id="ac228-112">Suffix oder Präfix</span><span class="sxs-lookup"><span data-stu-id="ac228-112">Suffix or prefix</span></span>|<span data-ttu-id="ac228-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="ac228-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="ac228-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="ac228-114">sbyte</span></span>|<span data-ttu-id="ac228-115">ganze 8-Bit-Zahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-115">signed 8-bit integer</span></span>|<span data-ttu-id="ac228-116">y</span><span class="sxs-lookup"><span data-stu-id="ac228-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="ac228-117">byte</span><span class="sxs-lookup"><span data-stu-id="ac228-117">byte</span></span>|<span data-ttu-id="ac228-118">natürliche 8-Bit-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="ac228-119">uy</span><span class="sxs-lookup"><span data-stu-id="ac228-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="ac228-120">int16</span><span class="sxs-lookup"><span data-stu-id="ac228-120">int16</span></span>|<span data-ttu-id="ac228-121">16-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-121">signed 16-bit integer</span></span>|<span data-ttu-id="ac228-122">s</span><span class="sxs-lookup"><span data-stu-id="ac228-122">s</span></span>|`86s`|
|<span data-ttu-id="ac228-123">uint16</span><span class="sxs-lookup"><span data-stu-id="ac228-123">uint16</span></span>|<span data-ttu-id="ac228-124">16-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="ac228-125">mehreren</span><span class="sxs-lookup"><span data-stu-id="ac228-125">us</span></span>|`86us`|
|<span data-ttu-id="ac228-126">int</span><span class="sxs-lookup"><span data-stu-id="ac228-126">int</span></span><br /><br /><span data-ttu-id="ac228-127">int32</span><span class="sxs-lookup"><span data-stu-id="ac228-127">int32</span></span>|<span data-ttu-id="ac228-128">32-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-128">signed 32-bit integer</span></span>|<span data-ttu-id="ac228-129">l oder none</span><span class="sxs-lookup"><span data-stu-id="ac228-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="ac228-130">uint</span><span class="sxs-lookup"><span data-stu-id="ac228-130">uint</span></span><br /><br /><span data-ttu-id="ac228-131">uint32</span><span class="sxs-lookup"><span data-stu-id="ac228-131">uint32</span></span>|<span data-ttu-id="ac228-132">32-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="ac228-133">u oder ul</span><span class="sxs-lookup"><span data-stu-id="ac228-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="ac228-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="ac228-134">unativeint</span></span>|<span data-ttu-id="ac228-135">systemeigener Zeiger als natürliche Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="ac228-136">un</span><span class="sxs-lookup"><span data-stu-id="ac228-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="ac228-137">int64</span><span class="sxs-lookup"><span data-stu-id="ac228-137">int64</span></span>|<span data-ttu-id="ac228-138">64-Bit-Ganzzahl mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-138">signed 64-bit integer</span></span>|<span data-ttu-id="ac228-139">L</span><span class="sxs-lookup"><span data-stu-id="ac228-139">L</span></span>|`86L`|
|<span data-ttu-id="ac228-140">uint64</span><span class="sxs-lookup"><span data-stu-id="ac228-140">uint64</span></span>|<span data-ttu-id="ac228-141">64-Bit-natürliche-Zahl ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="ac228-142">UL</span><span class="sxs-lookup"><span data-stu-id="ac228-142">UL</span></span>|`86UL`|
|<span data-ttu-id="ac228-143">single, float32</span><span class="sxs-lookup"><span data-stu-id="ac228-143">single, float32</span></span>|<span data-ttu-id="ac228-144">32-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ac228-144">32-bit floating point number</span></span>|<span data-ttu-id="ac228-145">F oder f</span><span class="sxs-lookup"><span data-stu-id="ac228-145">F or f</span></span>|<span data-ttu-id="ac228-146">`4.14F` oder `4.14f`</span><span class="sxs-lookup"><span data-stu-id="ac228-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="ac228-147">lf</span><span class="sxs-lookup"><span data-stu-id="ac228-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="ac228-148">float; double</span><span class="sxs-lookup"><span data-stu-id="ac228-148">float; double</span></span>|<span data-ttu-id="ac228-149">64-Bit-Gleitkommazahl</span><span class="sxs-lookup"><span data-stu-id="ac228-149">64-bit floating point number</span></span>|<span data-ttu-id="ac228-150">Keine</span><span class="sxs-lookup"><span data-stu-id="ac228-150">none</span></span>|<span data-ttu-id="ac228-151">`4.14`, `2.3E+32` oder `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="ac228-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="ac228-152">LF</span><span class="sxs-lookup"><span data-stu-id="ac228-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="ac228-153">bigint</span><span class="sxs-lookup"><span data-stu-id="ac228-153">bigint</span></span>|<span data-ttu-id="ac228-154">ganze Zahl, die nicht auf 64-Bit-Darstellung beschränkt ist</span><span class="sxs-lookup"><span data-stu-id="ac228-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="ac228-155">I</span><span class="sxs-lookup"><span data-stu-id="ac228-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="ac228-156">decimal</span><span class="sxs-lookup"><span data-stu-id="ac228-156">decimal</span></span>|<span data-ttu-id="ac228-157">als Festkommazahl oder rationale Zahl dargestellte Bruchzahl</span><span class="sxs-lookup"><span data-stu-id="ac228-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="ac228-158">M oder m</span><span class="sxs-lookup"><span data-stu-id="ac228-158">M or m</span></span>|<span data-ttu-id="ac228-159">`0.7833M` oder `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="ac228-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="ac228-160">Char</span><span class="sxs-lookup"><span data-stu-id="ac228-160">Char</span></span>|<span data-ttu-id="ac228-161">Unicodezeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-161">Unicode character</span></span>|<span data-ttu-id="ac228-162">Keine</span><span class="sxs-lookup"><span data-stu-id="ac228-162">none</span></span>|`'a'`|
|<span data-ttu-id="ac228-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ac228-163">String</span></span>|<span data-ttu-id="ac228-164">Unicode-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ac228-164">Unicode string</span></span>|<span data-ttu-id="ac228-165">Keine</span><span class="sxs-lookup"><span data-stu-id="ac228-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="ac228-166">oder</span><span class="sxs-lookup"><span data-stu-id="ac228-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="ac228-167">oder</span><span class="sxs-lookup"><span data-stu-id="ac228-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="ac228-168">oder</span><span class="sxs-lookup"><span data-stu-id="ac228-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="ac228-169">Siehe auch [Zeichenfolgen](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="ac228-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="ac228-170">byte</span><span class="sxs-lookup"><span data-stu-id="ac228-170">byte</span></span>|<span data-ttu-id="ac228-171">ASCII-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ac228-171">ASCII character</span></span>|<span data-ttu-id="ac228-172">B</span><span class="sxs-lookup"><span data-stu-id="ac228-172">B</span></span>|`'a'B`|
|<span data-ttu-id="ac228-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="ac228-173">byte[]</span></span>|<span data-ttu-id="ac228-174">ASCII-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ac228-174">ASCII string</span></span>|<span data-ttu-id="ac228-175">B</span><span class="sxs-lookup"><span data-stu-id="ac228-175">B</span></span>|`"text"B`|
|<span data-ttu-id="ac228-176">String oder byte[]</span><span class="sxs-lookup"><span data-stu-id="ac228-176">String or byte[]</span></span>|<span data-ttu-id="ac228-177">wörtliche Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ac228-177">verbatim string</span></span>|<span data-ttu-id="ac228-178">@-Präfix</span><span class="sxs-lookup"><span data-stu-id="ac228-178">@ prefix</span></span>|<span data-ttu-id="ac228-179">`@"\\server\share"`(Unicode)</span><span class="sxs-lookup"><span data-stu-id="ac228-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="ac228-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="ac228-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="ac228-181">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac228-181">Remarks</span></span>
<span data-ttu-id="ac228-182">Unicode-Zeichenfolgen darf explizite Codierungen, bei denen Sie angeben können, indem Sie mit `\u` gefolgt von einem hexadezimalen 16-Bit-Code oder UTF-32-Codierungen, bei denen Sie angeben können, indem Sie mit `\U` gefolgt von einer 32-Bit-Hexadezimalcode, der eine Unicode-darstellt Ersatzzeichenpaar.</span><span class="sxs-lookup"><span data-stu-id="ac228-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="ac228-183">Ab f# 3.1, können Sie die `+` melden beim Kombinieren von Zeichenfolgenliteralen.</span><span class="sxs-lookup"><span data-stu-id="ac228-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="ac228-184">Sie können auch das bitweise verwenden oder (`|||`) Operator, um Enumerationsflags zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="ac228-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="ac228-185">In F# 3.1 ist beispielsweise der folgende Code zulässig:</span><span class="sxs-lookup"><span data-stu-id="ac228-185">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="ac228-186">Die Verwendung anderer bitweiser Operatoren ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ac228-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="ac228-187">Benannte Literale</span><span class="sxs-lookup"><span data-stu-id="ac228-187">Named Literals</span></span>
<span data-ttu-id="ac228-188">Werte, die Konstanten sein sollen können gekennzeichnet werden, mit der [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) Attribut.</span><span class="sxs-lookup"><span data-stu-id="ac228-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="ac228-189">Dieses Attribut bewirkt, dass ein Wert als Konstante kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="ac228-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="ac228-190">In Musterabgleichsausdrücken werden Bezeichner, die mit Kleinbuchstaben beginnen, immer als zu bindende Variablen statt als Literale behandelt. Verwenden Sie daher im Allgemeinen Großbuchstaben am Wortanfang, wenn Sie Literale definieren.</span><span class="sxs-lookup"><span data-stu-id="ac228-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="ac228-191">Ganze Zahlen In andere Basiszahlen</span><span class="sxs-lookup"><span data-stu-id="ac228-191">Integers In Other Bases</span></span>

<span data-ttu-id="ac228-192">32-Bit-Ganzzahlen mit Vorzeichen können auch angegeben werden, in das hexadezimale, oktale oder binäre mithilfe einer `0x`, `0o` oder `0b` bzw. Präfix.</span><span class="sxs-lookup"><span data-stu-id="ac228-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="ac228-193">Unterstriche in numerische Literale</span><span class="sxs-lookup"><span data-stu-id="ac228-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="ac228-194">Ab f# 4.1, können Sie Ziffern mit einem Unterstrich trennen (`_`).</span><span class="sxs-lookup"><span data-stu-id="ac228-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="ac228-195">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac228-195">See Also</span></span>

[<span data-ttu-id="ac228-196">Core.LiteralAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="ac228-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
