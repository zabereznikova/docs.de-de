---
title: Typzeichen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bd017db40fc28c78e960a889947cc7323e3e156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="4759d-102">Geben Sie die Zeichen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4759d-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="4759d-103">Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, Sie können erzwingen, dass den Datentyp der einige Programmierelemente mit einem *-Typzeichen*.</span><span class="sxs-lookup"><span data-stu-id="4759d-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="4759d-104">Das Typzeichen muss unmittelbar auf das Element, ohne dazwischenliegende Zeichen jeglicher Art folgen.</span><span class="sxs-lookup"><span data-stu-id="4759d-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="4759d-105">Das Typzeichen ist nicht Teil des Namens des Elements.</span><span class="sxs-lookup"><span data-stu-id="4759d-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="4759d-106">Ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4759d-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="4759d-107">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="4759d-107">Identifier type characters</span></span>

<span data-ttu-id="4759d-108">Visual Basic stellt eine Reihe von *Typkennzeichen* , dass Sie in einer Deklaration verwenden können, um den Datentyp einer Variable oder Konstante angeben.</span><span class="sxs-lookup"><span data-stu-id="4759d-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="4759d-109">Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="4759d-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="4759d-110">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="4759d-110">Identifier type character</span></span>|<span data-ttu-id="4759d-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4759d-111">Data type</span></span>|<span data-ttu-id="4759d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4759d-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="4759d-113">Keine Typkennzeichen vorhanden, für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder für ein Zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="4759d-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="4759d-114">In einigen Fällen können Sie Anfügen der `$` Zeichen für eine Visual Basic-Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert vom Typ erhalten `String`.</span><span class="sxs-lookup"><span data-stu-id="4759d-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="4759d-115">In allen Fällen muss die Typkennzeichen den Bezeichnernamen unmittelbar folgen.</span><span class="sxs-lookup"><span data-stu-id="4759d-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="4759d-116">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="4759d-116">Literal type characters</span></span>

<span data-ttu-id="4759d-117">Ein *literal* ist eine Textdarstellung eines bestimmten Werts einen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4759d-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="4759d-118">Standardliteraltypen</span><span class="sxs-lookup"><span data-stu-id="4759d-118">Default literal types</span></span>

<span data-ttu-id="4759d-119">Die Form eines Literals, wie er im Code, in der Regel enthalten Angabe des Datentyps bestimmt.</span><span class="sxs-lookup"><span data-stu-id="4759d-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="4759d-120">Die folgende Tabelle zeigt diese Standarddatentypen.</span><span class="sxs-lookup"><span data-stu-id="4759d-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="4759d-121">Textform Literal</span><span class="sxs-lookup"><span data-stu-id="4759d-121">Textual form of literal</span></span>|<span data-ttu-id="4759d-122">Standard-Datentyp</span><span class="sxs-lookup"><span data-stu-id="4759d-122">Default data type</span></span>|<span data-ttu-id="4759d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4759d-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="4759d-124">Numerisch, kein Bruchteil</span><span class="sxs-lookup"><span data-stu-id="4759d-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="4759d-125">Numerisch, kein Bruchteil Teil, zu groß für`Integer`</span><span class="sxs-lookup"><span data-stu-id="4759d-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="4759d-126">Numerisch, Bruchteil</span><span class="sxs-lookup"><span data-stu-id="4759d-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="4759d-127">Eingeschlossen in doppelte Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="4759d-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="4759d-128">Eingeschlossen in Nummernzeichen</span><span class="sxs-lookup"><span data-stu-id="4759d-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="4759d-129">Erzwungene Literaltypen</span><span class="sxs-lookup"><span data-stu-id="4759d-129">Forced literal types</span></span>

<span data-ttu-id="4759d-130">Visual Basic stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, um ein Literal an einen anderen Datentyp als dem seiner Form anzunehmen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="4759d-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="4759d-131">Dazu müssen Sie das Zeichen am Ende das Literal anfügen.</span><span class="sxs-lookup"><span data-stu-id="4759d-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="4759d-132">Die folgende Tabelle zeigt die verfügbaren Literalzeichen mit Beispielen für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="4759d-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="4759d-133">(Literalzeichen)</span><span class="sxs-lookup"><span data-stu-id="4759d-133">Literal type character</span></span>|<span data-ttu-id="4759d-134">Datentyp</span><span class="sxs-lookup"><span data-stu-id="4759d-134">Data type</span></span>|<span data-ttu-id="4759d-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4759d-135">Example</span></span>|  
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

<span data-ttu-id="4759d-136">Keine Literalzeichen für die `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder für zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="4759d-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="4759d-137">Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücke können.</span><span class="sxs-lookup"><span data-stu-id="4759d-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="4759d-138">Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4759d-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="4759d-139">In allen Fällen muss das literal-Typzeichen den Literalwert unmittelbar folgen.</span><span class="sxs-lookup"><span data-stu-id="4759d-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="4759d-140">Hexadezimal, binäre und oktale Literale</span><span class="sxs-lookup"><span data-stu-id="4759d-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="4759d-141">Der Compiler interpretiert normalerweise ein Integer-literal um im System Anzahl Dezimalzahl (Basis 10) sein.</span><span class="sxs-lookup"><span data-stu-id="4759d-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="4759d-142">Sie können auch ein Integer-literal als Zahl mit Hexadezimalformat (Basis 16) definieren die `&H` Präfix, als Zahl Binärdatei (Basis 2) mit der `&B` Präfix, und als eine oktale (Basis 8) Zahl mit der `&O` Präfix.</span><span class="sxs-lookup"><span data-stu-id="4759d-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="4759d-143">Die Ziffern, die das Präfix folgen müssen für das System die Zahlen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="4759d-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="4759d-144">Dies wird anhand die folgende Tabelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4759d-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="4759d-145">Zahlenbasis</span><span class="sxs-lookup"><span data-stu-id="4759d-145">Number base</span></span>|<span data-ttu-id="4759d-146">Präfix</span><span class="sxs-lookup"><span data-stu-id="4759d-146">Prefix</span></span>|<span data-ttu-id="4759d-147">Gültige Werte</span><span class="sxs-lookup"><span data-stu-id="4759d-147">Valid digit values</span></span>|<span data-ttu-id="4759d-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4759d-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="4759d-149">Hexadezimalformat (Basis 16)</span><span class="sxs-lookup"><span data-stu-id="4759d-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="4759d-150">0-9 und A-F</span><span class="sxs-lookup"><span data-stu-id="4759d-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="4759d-151">Binär (Basis 2)</span><span class="sxs-lookup"><span data-stu-id="4759d-151">Binary (base 2)</span></span>|`0B`|<span data-ttu-id="4759d-152">0-1</span><span class="sxs-lookup"><span data-stu-id="4759d-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="4759d-153">Oktalformat (Basis 8)</span><span class="sxs-lookup"><span data-stu-id="4759d-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="4759d-154">0-7</span><span class="sxs-lookup"><span data-stu-id="4759d-154">0-7</span></span>|`&O77`|

<span data-ttu-id="4759d-155">In Visual Basic 2017 starten, können Sie das Unterstrich-Zeichen (`_`) als Gruppentrennzeichen um die Lesbarkeit der ein ganzzahliges Literal zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="4759d-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="4759d-156">Im folgenden Beispiel wird die `_` Zeichen um ein binäres literal in 8-Bit-Gruppen zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="4759d-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="4759d-157">Sie können einem Literal mit einem literal-Typzeichen Präfix folgen.</span><span class="sxs-lookup"><span data-stu-id="4759d-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="4759d-158">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="4759d-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="4759d-159">Im vorherigen Beispiel `counter` hat den Dezimalwert zwischen-32768, und `flags` hat den Dezimalwert + 32768.</span><span class="sxs-lookup"><span data-stu-id="4759d-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

## <a name="see-also"></a><span data-ttu-id="4759d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4759d-160">See Also</span></span>

 [<span data-ttu-id="4759d-161">Datentypen</span><span class="sxs-lookup"><span data-stu-id="4759d-161">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="4759d-162">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="4759d-162">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="4759d-163">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="4759d-163">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="4759d-164">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4759d-164">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="4759d-165">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="4759d-165">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="4759d-166">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="4759d-166">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="4759d-167">Datentypen</span><span class="sxs-lookup"><span data-stu-id="4759d-167">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
