---
title: SByte-Datentyp (Visual Basic)
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
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
ms.openlocfilehash: b2ef4f083cd9b6f38dc91bf8bf0eac9cd21c2618
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148083"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="2039e-102">SByte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2039e-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="2039e-103">Speichert signierte 8-Bit (1-Byte) ganze Zahlen, die im Bereich zwischen-128 und 127 liegen.</span><span class="sxs-lookup"><span data-stu-id="2039e-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2039e-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2039e-104">Remarks</span></span>

<span data-ttu-id="2039e-105">Verwenden der `SByte` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer` oder sogar die Hälfte Datenbreite des `Short`.</span><span class="sxs-lookup"><span data-stu-id="2039e-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="2039e-106">In einigen Fällen die common Language Runtime kann in der Lage, Packen Ihrer `SByte` Variablen, die eng zusammen und Arbeitsspeicher belegt.</span><span class="sxs-lookup"><span data-stu-id="2039e-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="2039e-107">Der Standardwert von `SByte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="2039e-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="2039e-108">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="2039e-108">Literal assignments</span></span>
  
<span data-ttu-id="2039e-109">Sie können deklarieren und initialisieren eine `SByte` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="2039e-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="2039e-110">Im folgenden Beispiel werden Ganzzahlen wie 102, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden zugewiesen, `SByte` Werte.</span><span class="sxs-lookup"><span data-stu-id="2039e-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="2039e-111">Dieses Beispiel erfordert, dass Sie die Kompilierung mit der `/removeintchecks` Compilerschalter.</span><span class="sxs-lookup"><span data-stu-id="2039e-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="2039e-112">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="2039e-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="2039e-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="2039e-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="2039e-114">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2039e-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="2039e-115">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="2039e-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="2039e-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2039e-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="2039e-117">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="2039e-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="2039e-118">Wenn ein Ganzzahlliteral kein Suffix besitzt eine [Ganzzahl](integer-data-type.md) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2039e-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="2039e-119">Ist das Ganzzahlliteral außerhalb des Bereichs von der `Integer` Typ eine [lange](long-data-type.md) abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2039e-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="2039e-120">Das bedeutet, dass in den vorherigen Beispielen, die die numerischen Literale `0x9A` und `0b10011010` werden als 32-Bit-Ganzzahlen mit Vorzeichen mit einem Wert von 156, überschreitet interpretiert <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2039e-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2039e-121">Um Code wie den folgenden zu kompilieren, die eine nicht-Dezimalzahlen ganze Zahl, und weist eine `SByte`, führen Sie einen der folgenden:</span><span class="sxs-lookup"><span data-stu-id="2039e-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="2039e-122">Deaktivieren Sie die Grenzen Überprüfung ganzer Zahlen durch die Kompilierung mit der `/removeintchecks` Compilerschalter.</span><span class="sxs-lookup"><span data-stu-id="2039e-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="2039e-123">Verwenden einer [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) , den literalen Wert explizit zu definieren, die Sie zuweisen möchten die `SByte`.</span><span class="sxs-lookup"><span data-stu-id="2039e-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="2039e-124">Das folgende Beispiel weist ein negatives Literal `Short` -Werts in einen `SByte`.</span><span class="sxs-lookup"><span data-stu-id="2039e-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="2039e-125">Beachten Sie, dass für negative Zahlen, das höchstwertige Bit von das höherwertige Wort des numerischen Literals muss festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2039e-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="2039e-126">Bei unserem Beispiel ist dies bit 15 des Literals `Short` Wert.</span><span class="sxs-lookup"><span data-stu-id="2039e-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="2039e-127">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="2039e-127">Programming tips</span></span>
  
-   <span data-ttu-id="2039e-128">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="2039e-128">**CLS Compliance.**</span></span> <span data-ttu-id="2039e-129">Die `SByte` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2039e-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="2039e-130">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="2039e-130">**Widening.**</span></span> <span data-ttu-id="2039e-131">Die `SByte` -Datentyp wird zu `Short`, `Integer`, `Long`, `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="2039e-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="2039e-132">Dies bedeutet, Sie können konvertieren `SByte` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="2039e-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="2039e-133">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="2039e-133">**Type Characters.**</span></span> <span data-ttu-id="2039e-134">`SByte` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="2039e-134">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="2039e-135">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="2039e-135">**Framework Type.**</span></span> <span data-ttu-id="2039e-136">Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="2039e-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2039e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2039e-137">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="2039e-138">Datentypen</span><span class="sxs-lookup"><span data-stu-id="2039e-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="2039e-139">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="2039e-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="2039e-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="2039e-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="2039e-141">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2039e-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="2039e-142">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2039e-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="2039e-143">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2039e-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="2039e-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="2039e-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
