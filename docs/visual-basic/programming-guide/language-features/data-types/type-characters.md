---
title: Geben Sie die Zeichen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 335306eca12070de456a72e918bcbba1e22ab55b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="dfc32-102">Typzeichen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfc32-102">Type Characters (Visual Basic)</span></span>
<span data-ttu-id="dfc32-103">Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, können Sie den Datentyp des einige Programmierelemente mit Erzwingen einer *Typzeichen*.</span><span class="sxs-lookup"><span data-stu-id="dfc32-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="dfc32-104">Das Typzeichen muss unmittelbar auf das Element, ohne dazwischenliegende Zeichen jeglicher Art folgen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>  
  
 <span data-ttu-id="dfc32-105">Das Typzeichen ist nicht Teil des Namens des Elements.</span><span class="sxs-lookup"><span data-stu-id="dfc32-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="dfc32-106">Ein mit einem Typzeichen definiertes Element kann ohne das Typzeichen verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dfc32-106">An element defined with a type character can be referenced without the type character.</span></span>  
  
## <a name="identifier-type-characters"></a><span data-ttu-id="dfc32-107">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-107">Identifier Type Characters</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dfc32-108">Stellt eine Reihe von *Typkennzeichen*, die Sie in einer Deklaration verwenden können, um den Datentyp einer Variablen oder Konstanten angeben.</span><span class="sxs-lookup"><span data-stu-id="dfc32-108"> supplies a set of *identifier type characters*, which you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="dfc32-109">Die folgende Tabelle zeigt die verfügbaren Typkennzeichen mit Beispielen für die Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dfc32-109">The following table shows the available identifier type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="dfc32-110">Typkennzeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-110">Identifier type character</span></span>|<span data-ttu-id="dfc32-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="dfc32-111">Data type</span></span>|<span data-ttu-id="dfc32-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfc32-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="dfc32-113">Keine Typkennzeichen für die `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort` Datentypen oder zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="dfc32-114">In einigen Fällen können Sie Anfügen der `$` das Zeichen eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Funktion, z. B. `Left$` anstelle von `Left`, um einen Rückgabewert vom Typ erhalten `String`.</span><span class="sxs-lookup"><span data-stu-id="dfc32-114">In some cases, you can append the `$` character to a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>  
  
 <span data-ttu-id="dfc32-115">In allen Fällen muss die Typkennzeichen unmittelbar auf den Namen des Bezeichners folgen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>  
  
## <a name="literal-type-characters"></a><span data-ttu-id="dfc32-116">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-116">Literal Type Characters</span></span>  
 <span data-ttu-id="dfc32-117">Ein *Zeichenfolgenliteral* ist eine Textdarstellung eines bestimmten Werts eines Datentyps.</span><span class="sxs-lookup"><span data-stu-id="dfc32-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  
  
### <a name="default-literal-types"></a><span data-ttu-id="dfc32-118">Standardliteraltypen</span><span class="sxs-lookup"><span data-stu-id="dfc32-118">Default Literal Types</span></span>  
 <span data-ttu-id="dfc32-119">Die Form eines Literals richtet in Ihrem Code in der Regel sich Datentyp.</span><span class="sxs-lookup"><span data-stu-id="dfc32-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="dfc32-120">Die folgende Tabelle zeigt diese Standardtypen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="dfc32-121">Textform literalen</span><span class="sxs-lookup"><span data-stu-id="dfc32-121">Textual form of literal</span></span>|<span data-ttu-id="dfc32-122">Standard-Datentyp</span><span class="sxs-lookup"><span data-stu-id="dfc32-122">Default data type</span></span>|<span data-ttu-id="dfc32-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfc32-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="dfc32-124">Numerisch, kein Bruchteil</span><span class="sxs-lookup"><span data-stu-id="dfc32-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="dfc32-125">Numerisch, kein Bruchteil Teil, zu groß für`Integer`</span><span class="sxs-lookup"><span data-stu-id="dfc32-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="dfc32-126">Numerisch, Bruchteil</span><span class="sxs-lookup"><span data-stu-id="dfc32-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="dfc32-127">Eingeschlossen in doppelte Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="dfc32-128">Eingeschlossen in Nummernzeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a><span data-ttu-id="dfc32-129">Erzwungene Literale</span><span class="sxs-lookup"><span data-stu-id="dfc32-129">Forced Literal Types</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="dfc32-130">Stellt eine Reihe von *Literaltypzeichen*, womit Sie verwenden können, erzwingen Sie ein Literal einen Datentyp als seine Form annimmt.</span><span class="sxs-lookup"><span data-stu-id="dfc32-130"> supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="dfc32-131">Dazu fügen Sie das Zeichen am Ende des Literals.</span><span class="sxs-lookup"><span data-stu-id="dfc32-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="dfc32-132">Die folgende Tabelle zeigt die verfügbaren Literalzeichen und Beispiele für deren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="dfc32-132">The following table shows the available literal type characters with examples of usage.</span></span>  
  
|<span data-ttu-id="dfc32-133">Literaltypzeichen</span><span class="sxs-lookup"><span data-stu-id="dfc32-133">Literal type character</span></span>|<span data-ttu-id="dfc32-134">Datentyp</span><span class="sxs-lookup"><span data-stu-id="dfc32-134">Data type</span></span>|<span data-ttu-id="dfc32-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfc32-135">Example</span></span>|  
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
  
 <span data-ttu-id="dfc32-136">Keine Literalzeichen für die `Boolean`, `Byte`, `Date`, `Object`, `SByte`, oder `String` Datentypen oder zusammengesetzte Datentypen wie z. B. Arrays oder Strukturen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>  
  
 <span data-ttu-id="dfc32-137">Literale können auch die Typkennzeichen (`%`, `&`, `@`, `!`, `#`, `$`), wie Variablen, Konstanten und Ausdrücken können.</span><span class="sxs-lookup"><span data-stu-id="dfc32-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="dfc32-138">Allerdings die Literalzeichen (`S`, `I`, `L`, `D`, `F`, `R`, `C`) kann nur mit Literalen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dfc32-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>  
  
 <span data-ttu-id="dfc32-139">In allen Fällen muss das Literalzeichen unmittelbar auf den Literalwert folgen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-139">In all cases, the literal type character must immediately follow the literal value.</span></span>  
  
## <a name="hexadecimal-and-octal-literals"></a><span data-ttu-id="dfc32-140">Hexadezimale und oktale Literale</span><span class="sxs-lookup"><span data-stu-id="dfc32-140">Hexadecimal and Octal Literals</span></span>  
 <span data-ttu-id="dfc32-141">Der Compiler construes normalerweise ein Ganzzahlliteral im Dezimalformat (Basis 10) Zahlensystem.</span><span class="sxs-lookup"><span data-stu-id="dfc32-141">The compiler normally construes an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="dfc32-142">Sie können erzwingen, dass eine ganze Zahl literal werden Hexadezimalformat (Basis 16) mit der `&H` Präfix, und Sie können erzwingen, dass oktale (Basis 8) werden die `&O` Präfix.</span><span class="sxs-lookup"><span data-stu-id="dfc32-142">You can force an integer literal to be hexadecimal (base 16) with the `&H` prefix, and you can force it to be octal (base 8) with the `&O` prefix.</span></span> <span data-ttu-id="dfc32-143">Die Ziffern, die dem Präfix folgen müssen Zahlensystem geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="dfc32-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="dfc32-144">Dies wird in die folgende Tabelle veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dfc32-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="dfc32-145">Zahlenbasis</span><span class="sxs-lookup"><span data-stu-id="dfc32-145">Number base</span></span>|<span data-ttu-id="dfc32-146">Präfix</span><span class="sxs-lookup"><span data-stu-id="dfc32-146">Prefix</span></span>|<span data-ttu-id="dfc32-147">Gültige Werte</span><span class="sxs-lookup"><span data-stu-id="dfc32-147">Valid digit values</span></span>|<span data-ttu-id="dfc32-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dfc32-148">Example</span></span>|  
|-----------------|------------|------------------------|-------------|  
|<span data-ttu-id="dfc32-149">Hexadezimalformat (Basis 16)</span><span class="sxs-lookup"><span data-stu-id="dfc32-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="dfc32-150">0-9 und A-F</span><span class="sxs-lookup"><span data-stu-id="dfc32-150">0-9 and A-F</span></span>|`&HFFFF`|  
|<span data-ttu-id="dfc32-151">Oktalformat (Basis 8)</span><span class="sxs-lookup"><span data-stu-id="dfc32-151">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="dfc32-152">0-7</span><span class="sxs-lookup"><span data-stu-id="dfc32-152">0-7</span></span>|`&O77`|  
  
 <span data-ttu-id="dfc32-153">Sie können ein vorangestellter Literal mit einem Literalzeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="dfc32-153">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="dfc32-154">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="dfc32-154">The following example shows this.</span></span>  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 <span data-ttu-id="dfc32-155">Im vorherigen Beispiel `counter` hat den Dezimalwert-32768, und `flags` hat den Dezimalwert +&32768;.</span><span class="sxs-lookup"><span data-stu-id="dfc32-155">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc32-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfc32-156">See Also</span></span>  
 <span data-ttu-id="dfc32-157">[Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-157">[Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md) </span></span>  
<span data-ttu-id="dfc32-158"> [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-158"> [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="dfc32-159"> [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-159"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="dfc32-160"> [Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-160"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="dfc32-161"> [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-161"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="dfc32-162"> [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="dfc32-162"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="dfc32-163"> [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span><span class="sxs-lookup"><span data-stu-id="dfc32-163"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)</span></span>
