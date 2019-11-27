---
title: Typzeichen
ms.date: 01/31/2018
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
ms.openlocfilehash: 628461c8136946dd902c0a52048eee7c516c52cd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352926"
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="3a9ef-102">Typzeichen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a9ef-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="3a9ef-103">Zusätzlich zur Angabe eines Datentyps in einer Deklarations Anweisung können Sie den Datentyp einiger Programmier Elemente mit einem *Typzeichen*erzwingen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="3a9ef-104">Das Typzeichen muss unmittelbar auf das-Element folgen, ohne dass dabei dazwischen liegende Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="3a9ef-105">Das Typzeichen ist nicht Teil des Namens des Elements.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="3a9ef-106">Auf ein Element, das mit einem Typzeichen definiert ist, kann ohne das Typzeichen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="3a9ef-107">Bezeichnertyp Zeichen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-107">Identifier type characters</span></span>

<span data-ttu-id="3a9ef-108">Visual Basic stellt einen Satz von *Bezeichnertyp Zeichen* bereit, die Sie in einer-Deklaration verwenden können, um den Datentyp einer Variablen oder Konstanten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="3a9ef-109">In der folgenden Tabelle werden die verfügbaren Bezeichnertyp Zeichen und Verwendungs Beispiele angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="3a9ef-110">Bezeichnertyp Zeichen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-110">Identifier type character</span></span>|<span data-ttu-id="3a9ef-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3a9ef-111">Data type</span></span>|<span data-ttu-id="3a9ef-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a9ef-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="3a9ef-113">Es sind keine Bezeichnertyp Zeichen für die Datentypen "`Boolean`", "`Byte`", "`Char`", "`Date`", "`Object`", "`SByte`", "`Short`", "`UInteger`", "`ULong`" oder "`UShort`" vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="3a9ef-114">In einigen Fällen können Sie das `$` Zeichen an eine Visual Basic Funktion anfügen, z. b. `Left$` anstelle `Left`, um einen Rückgabewert vom Typ `String`zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="3a9ef-115">In allen Fällen muss das Bezeichnertyp Zeichen direkt auf den Bezeichnernamen folgen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="3a9ef-116">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-116">Literal type characters</span></span>

<span data-ttu-id="3a9ef-117">Ein *Literalwert* ist eine Textdarstellung eines bestimmten Werts eines Datentyps.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="3a9ef-118">Standardliteraltypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-118">Default literal types</span></span>

<span data-ttu-id="3a9ef-119">Die Form eines Literals, wie er im Code angezeigt wird, bestimmt normalerweise seinen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="3a9ef-120">In der folgenden Tabelle sind diese Standardtypen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="3a9ef-121">Textform des Literals</span><span class="sxs-lookup"><span data-stu-id="3a9ef-121">Textual form of literal</span></span>|<span data-ttu-id="3a9ef-122">Standard Datentyp</span><span class="sxs-lookup"><span data-stu-id="3a9ef-122">Default data type</span></span>|<span data-ttu-id="3a9ef-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a9ef-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="3a9ef-124">Numerisch, kein Bruchteil</span><span class="sxs-lookup"><span data-stu-id="3a9ef-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="3a9ef-125">Numerisch, kein Bruchteile, zu groß für `Integer`</span><span class="sxs-lookup"><span data-stu-id="3a9ef-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="3a9ef-126">Numerisch, Bruchteile</span><span class="sxs-lookup"><span data-stu-id="3a9ef-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="3a9ef-127">Eingeschlossen in doppelte Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="3a9ef-128">Eingeschlossen in Nummern Zeichen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="3a9ef-129">Erzwungene Literaltypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-129">Forced literal types</span></span>

<span data-ttu-id="3a9ef-130">Visual Basic stellt einen Satz von *Literaltypzeichen*bereit, die Sie verwenden können, um zu erzwingen, dass ein Literale einen anderen Datentyp annimmt als den, der vom Formular angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="3a9ef-131">Dies erreichen Sie, indem Sie das Zeichen an das Ende des Literals anhängen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="3a9ef-132">In der folgenden Tabelle sind die verfügbaren Literaltypzeichen und Verwendungs Beispiele aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="3a9ef-133">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-133">Literal type character</span></span>|<span data-ttu-id="3a9ef-134">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3a9ef-134">Data type</span></span>|<span data-ttu-id="3a9ef-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a9ef-135">Example</span></span>|  
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

<span data-ttu-id="3a9ef-136">Für die Datentypen "`Boolean`", "`Byte`", "`Date`", "`Object`", "`SByte`" oder "`String`" oder für zusammengesetzte Datentypen wie Arrays oder Strukturen sind keine Literaltypzeichen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="3a9ef-137">Literale können auch die Bezeichnertyp Zeichen (`%`, `&`, `@`, `!`, `#`, `$`) verwenden, ebenso wie Variablen, Konstanten und Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="3a9ef-138">Die Literaltypzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) können jedoch nur mit Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="3a9ef-139">In allen Fällen muss das Literaltypzeichen unmittelbar auf den Literalwert folgen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="3a9ef-140">Hexadezimale, binäre und oktale Literale</span><span class="sxs-lookup"><span data-stu-id="3a9ef-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="3a9ef-141">Der Compiler interpretiert normalerweise ein Ganzzahlliteral, das im Dezimalzahlen System (Base 10) liegt.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="3a9ef-142">Sie können ein Ganzzahlliteral auch als hexadezimale Zahl (Basis 16) mit dem `&H`-Präfix definieren, als binäre (Basis 2) Zahl mit dem `&B` Präfix und als oktale (Basis 8)-Nummer mit dem `&O` Präfix.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="3a9ef-143">Die Ziffern, die dem Präfix folgen, müssen für das Zahlensystem geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="3a9ef-144">Dies wird in der folgenden Tabelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="3a9ef-145">Zahlenbasis</span><span class="sxs-lookup"><span data-stu-id="3a9ef-145">Number base</span></span>|<span data-ttu-id="3a9ef-146">Präfix</span><span class="sxs-lookup"><span data-stu-id="3a9ef-146">Prefix</span></span>|<span data-ttu-id="3a9ef-147">Gültige Ziffern Werte</span><span class="sxs-lookup"><span data-stu-id="3a9ef-147">Valid digit values</span></span>|<span data-ttu-id="3a9ef-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3a9ef-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="3a9ef-149">Hexadezimalformat (Basis 16)</span><span class="sxs-lookup"><span data-stu-id="3a9ef-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="3a9ef-150">0-9 und A-F</span><span class="sxs-lookup"><span data-stu-id="3a9ef-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="3a9ef-151">Binary (Basis 2)</span><span class="sxs-lookup"><span data-stu-id="3a9ef-151">Binary (base 2)</span></span>|`&B`|<span data-ttu-id="3a9ef-152">0-1</span><span class="sxs-lookup"><span data-stu-id="3a9ef-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="3a9ef-153">Oktalformat (Basis 8)</span><span class="sxs-lookup"><span data-stu-id="3a9ef-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="3a9ef-154">0-7</span><span class="sxs-lookup"><span data-stu-id="3a9ef-154">0-7</span></span>|`&O77`|

<span data-ttu-id="3a9ef-155">Ab Visual Basic 2017 können Sie den Unterstrich (`_`) als Gruppen Trennzeichen verwenden, um die Lesbarkeit eines ganzzahligen Literals zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="3a9ef-156">Im folgenden Beispiel wird das `_` Zeichen verwendet, um ein binäres wahrsten in 8-Bit-Gruppen zu gruppieren:</span><span class="sxs-lookup"><span data-stu-id="3a9ef-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="3a9ef-157">Sie können einem Literalzeichen ein Literalzeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="3a9ef-158">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="3a9ef-159">Im vorherigen Beispiel hat `counter` den Dezimalwert-32768 und `flags` den Dezimalwert + 32768.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="3a9ef-160">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a9ef-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="3a9ef-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3a9ef-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="3a9ef-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a9ef-162">See also</span></span>

- [<span data-ttu-id="3a9ef-163">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="3a9ef-164">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="3a9ef-165">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="3a9ef-166">Typkonvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3a9ef-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="3a9ef-167">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="3a9ef-168">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="3a9ef-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="3a9ef-169">Datentypen</span><span class="sxs-lookup"><span data-stu-id="3a9ef-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
