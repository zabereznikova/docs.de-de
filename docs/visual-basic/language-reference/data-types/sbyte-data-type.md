---
title: SByte-Datentyp (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bcd00665ec5b8651089811a61212bfa302fe95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="075f5-102">SByte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="075f5-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="075f5-103">Speichert signierte (1-Byte) 8-Bit-Ganzzahlen, die zwischen-128 bis 127 liegen.</span><span class="sxs-lookup"><span data-stu-id="075f5-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="075f5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="075f5-104">Remarks</span></span>

<span data-ttu-id="075f5-105">Verwenden der `SByte` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer` oder sogar die halbe Breite der `Short`.</span><span class="sxs-lookup"><span data-stu-id="075f5-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="075f5-106">In einigen Fällen die common Language Runtime möglicherweise pack Ihre `SByte` Variablen eng zusammen, und speichern Sie den Arbeitsspeicherverbrauch.</span><span class="sxs-lookup"><span data-stu-id="075f5-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="075f5-107">Der Standardwert von `SByte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="075f5-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="075f5-108">Literal Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="075f5-108">Literal assignments</span></span>
  
<span data-ttu-id="075f5-109">Sie können deklarieren und Initialisieren einer `SByte` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="075f5-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="075f5-110">Im folgenden Beispiel Ganzzahlen-102, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale zugewiesen sind `SByte` Werte.</span><span class="sxs-lookup"><span data-stu-id="075f5-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="075f5-111">Dieses Beispiel benötigen Sie, dass beim Kompilieren mit der `/removeintchecks` Compilerschalter.</span><span class="sxs-lookup"><span data-stu-id="075f5-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="075f5-112">Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="075f5-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="075f5-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="075f5-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="075f5-114">Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="075f5-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="075f5-115">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="075f5-115">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="075f5-116">Wenn ein Ganzzahlliteral ohne Suffix hat eine [Ganzzahl](integer-data-type.md) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="075f5-116">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="075f5-117">Integer-literal ist außerhalb des Bereichs der der `Integer` Typ, eine [lange](long-data-type.md) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="075f5-117">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="075f5-118">Dies bedeutet, dass in den vorherigen Beispielen, die numerische Literale `0x9A` und `0b10011010` werden als 32-Bit, die mit einem Wert von 156, wodurch überschritten Ganzzahlen mit Vorzeichen interpretiert <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="075f5-118">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="075f5-119">Um Code wie folgt zu kompilieren, die zu eine nicht-Dezimalzahlen Ganzzahl weist eine `SByte`, führen Sie eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="075f5-119">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="075f5-120">Grenzen Überprüfungen deaktiviert, durch die Kompilierung mit der `/removeintchecks` Compilerschalter.</span><span class="sxs-lookup"><span data-stu-id="075f5-120">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="075f5-121">Verwenden einer [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) den literalen Wert explizit zu definieren, die Sie zuweisen möchten die `SByte`.</span><span class="sxs-lookup"><span data-stu-id="075f5-121">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="075f5-122">Im folgende Beispiel weist ein negatives Literal `Short` -Wert an ein `SByte`.</span><span class="sxs-lookup"><span data-stu-id="075f5-122">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="075f5-123">Beachten Sie, dass für negative Zahlen das höchstwertige Bit von das höherwertige Wort numerisches Literal festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="075f5-123">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="075f5-124">Bei unserem Beispiel ist dies bit 15 des Literals `Short` Wert.</span><span class="sxs-lookup"><span data-stu-id="075f5-124">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="075f5-125">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="075f5-125">Programming tips</span></span>
  
-   <span data-ttu-id="075f5-126">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="075f5-126">**CLS Compliance.**</span></span> <span data-ttu-id="075f5-127">Die `SByte` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="075f5-127">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="075f5-128">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="075f5-128">**Widening.**</span></span> <span data-ttu-id="075f5-129">Die `SByte` -Datentyp zu `Short`, `Integer`, `Long`, `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="075f5-129">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="075f5-130">Dies bedeutet, Sie können konvertieren `SByte` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="075f5-130">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="075f5-131">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="075f5-131">**Type Characters.**</span></span> <span data-ttu-id="075f5-132">`SByte`hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="075f5-132">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="075f5-133">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="075f5-133">**Framework Type.**</span></span> <span data-ttu-id="075f5-134">Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="075f5-134">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="075f5-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="075f5-135">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="075f5-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="075f5-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="075f5-137">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="075f5-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="075f5-138">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="075f5-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="075f5-139">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="075f5-139">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="075f5-140">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="075f5-140">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="075f5-141">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="075f5-141">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="075f5-142">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="075f5-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
