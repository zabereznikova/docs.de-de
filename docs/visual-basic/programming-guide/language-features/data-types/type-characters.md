---
title: Typzeichen (Visual Basic)
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: bdb675b9605d03829c95897382daa6d03cf1b041
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="e2b73-102">Geben Sie die Zeichen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2b73-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="e2b73-103">Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, Sie können erzwingen, dass den Datentyp der einige Programmierelemente mit einem *-Typzeichen*.</span><span class="sxs-lookup"><span data-stu-id="e2b73-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="e2b73-104">Das Typzeichen muss unmittelbar auf das Element, ohne dazwischenliegende Zeichen jeglicher Art folgen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="e2b73-105">Das Typzeichen ist nicht Teil des Namens des Elements.</span><span class="sxs-lookup"><span data-stu-id="e2b73-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="e2b73-106">Ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e2b73-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="e2b73-107">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="e2b73-107">Identifier type characters</span></span>

<span data-ttu-id="e2b73-108">Visual Basic stellt eine Reihe von *Typkennzeichen* , dass Sie in einer Deklaration verwenden können, um den Datentyp einer Variable oder Konstante angeben.</span><span class="sxs-lookup"><span data-stu-id="e2b73-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="e2b73-109">Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e2b73-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e2b73-110">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="e2b73-110">Identifier type character</span></span>|<span data-ttu-id="e2b73-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e2b73-111">Data type</span></span>|<span data-ttu-id="e2b73-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2b73-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="e2b73-113">Keine Typkennzeichen vorhanden, für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder für ein Zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e2b73-114">In einigen Fällen können Sie Anfügen der `$` Zeichen für eine Visual Basic-Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert vom Typ erhalten `String`.</span><span class="sxs-lookup"><span data-stu-id="e2b73-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="e2b73-115">In allen Fällen muss die Typkennzeichen den Bezeichnernamen unmittelbar folgen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="e2b73-116">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="e2b73-116">Literal type characters</span></span>

<span data-ttu-id="e2b73-117">Ein *literal* ist eine Textdarstellung eines bestimmten Werts einen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="e2b73-118">Standardliteraltypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-118">Default literal types</span></span>

<span data-ttu-id="e2b73-119">Die Form eines Literals, wie er im Code, in der Regel enthalten Angabe des Datentyps bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e2b73-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="e2b73-120">Die folgende Tabelle zeigt diese Standarddatentypen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="e2b73-121">Textform Literal</span><span class="sxs-lookup"><span data-stu-id="e2b73-121">Textual form of literal</span></span>|<span data-ttu-id="e2b73-122">Standard-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e2b73-122">Default data type</span></span>|<span data-ttu-id="e2b73-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2b73-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="e2b73-124">Numerisch, kein Bruchteil</span><span class="sxs-lookup"><span data-stu-id="e2b73-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="e2b73-125">Numerisch, kein Bruchteil Teil, zu groß für`Integer`</span><span class="sxs-lookup"><span data-stu-id="e2b73-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="e2b73-126">Numerisch, Bruchteil</span><span class="sxs-lookup"><span data-stu-id="e2b73-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="e2b73-127">Eingeschlossen in doppelte Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="e2b73-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="e2b73-128">Eingeschlossen in Nummernzeichen</span><span class="sxs-lookup"><span data-stu-id="e2b73-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="e2b73-129">Erzwungene Literaltypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-129">Forced literal types</span></span>

<span data-ttu-id="e2b73-130">Visual Basic stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, um ein Literal an einen anderen Datentyp als dem seiner Form anzunehmen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="e2b73-131">Dazu müssen Sie das Zeichen am Ende das Literal anfügen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="e2b73-132">Die folgende Tabelle zeigt die verfügbaren Literalzeichen mit Beispielen für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e2b73-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="e2b73-133">(Literalzeichen)</span><span class="sxs-lookup"><span data-stu-id="e2b73-133">Literal type character</span></span>|<span data-ttu-id="e2b73-134">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e2b73-134">Data type</span></span>|<span data-ttu-id="e2b73-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2b73-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="e2b73-136">Keine Literalzeichen für die `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder für zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="e2b73-137">Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücke können.</span><span class="sxs-lookup"><span data-stu-id="e2b73-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="e2b73-138">Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2b73-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="e2b73-139">In allen Fällen muss das literal-Typzeichen den Literalwert unmittelbar folgen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="e2b73-140">Hexadezimal, binäre und oktale Literale</span><span class="sxs-lookup"><span data-stu-id="e2b73-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="e2b73-141">Der Compiler interpretiert normalerweise ein Integer-literal um im System Anzahl Dezimalzahl (Basis 10) sein.</span><span class="sxs-lookup"><span data-stu-id="e2b73-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="e2b73-142">Sie können auch ein Integer-literal als Zahl mit Hexadezimalformat (Basis 16) definieren die `&H` Präfix, als Zahl Binärdatei (Basis 2) mit der `&B` Präfix, und als eine oktale (Basis 8) Zahl mit der `&O` Präfix.</span><span class="sxs-lookup"><span data-stu-id="e2b73-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="e2b73-143">Die Ziffern, die das Präfix folgen müssen für das System die Zahlen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="e2b73-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="e2b73-144">Dies wird anhand die folgende Tabelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e2b73-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="e2b73-145">Zahlenbasis</span><span class="sxs-lookup"><span data-stu-id="e2b73-145">Number base</span></span>|<span data-ttu-id="e2b73-146">Präfix</span><span class="sxs-lookup"><span data-stu-id="e2b73-146">Prefix</span></span>|<span data-ttu-id="e2b73-147">Gültige Werte</span><span class="sxs-lookup"><span data-stu-id="e2b73-147">Valid digit values</span></span>|<span data-ttu-id="e2b73-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2b73-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="e2b73-149">Hexadezimalformat (Basis 16)</span><span class="sxs-lookup"><span data-stu-id="e2b73-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="e2b73-150">0-9 und A-F</span><span class="sxs-lookup"><span data-stu-id="e2b73-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="e2b73-151">Binär (Basis 2)</span><span class="sxs-lookup"><span data-stu-id="e2b73-151">Binary (base 2)</span></span>|`0B`|<span data-ttu-id="e2b73-152">0-1</span><span class="sxs-lookup"><span data-stu-id="e2b73-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="e2b73-153">Oktalformat (Basis 8)</span><span class="sxs-lookup"><span data-stu-id="e2b73-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="e2b73-154">0-7</span><span class="sxs-lookup"><span data-stu-id="e2b73-154">0-7</span></span>|`&O77`|

<span data-ttu-id="e2b73-155">In Visual Basic 2017 starten, können Sie das Unterstrich-Zeichen (`_`) als Gruppentrennzeichen um die Lesbarkeit der ein ganzzahliges Literal zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e2b73-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="e2b73-156">Im folgenden Beispiel wird die `_` Zeichen um ein binäres literal in 8-Bit-Gruppen zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="e2b73-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="e2b73-157">Sie können einem Literal mit einem literal-Typzeichen Präfix folgen.</span><span class="sxs-lookup"><span data-stu-id="e2b73-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="e2b73-158">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="e2b73-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="e2b73-159">Im vorherigen Beispiel `counter` hat den Dezimalwert zwischen-32768, und `flags` hat den Dezimalwert + 32768.</span><span class="sxs-lookup"><span data-stu-id="e2b73-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="e2b73-160">Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern.</span><span class="sxs-lookup"><span data-stu-id="e2b73-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="e2b73-161">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e2b73-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="e2b73-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2b73-162">See Also</span></span>

 [<span data-ttu-id="e2b73-163">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="e2b73-164">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="e2b73-165">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="e2b73-166">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2b73-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="e2b73-167">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="e2b73-168">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="e2b73-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="e2b73-169">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e2b73-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
