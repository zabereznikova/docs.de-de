---
title: SByte-Datentyp
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
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401382"
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="b2abc-102">SByte-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2abc-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="b2abc-103">Enthält signierte 8-Bit-Ganzzahlen (1 Byte), die einen Wert von -128 bis 127 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2abc-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b2abc-104">Remarks</span></span>

<span data-ttu-id="b2abc-105">Verwenden `SByte` Sie den Datentyp, um ganzzahlige Werte zu `Integer` enthalten, die nicht `Short`die volle Datenbreite oder sogar die halbe Datenbreite von erfordern.</span><span class="sxs-lookup"><span data-stu-id="b2abc-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="b2abc-106">In einigen Fällen kann die Common Language Runtime Ihre `SByte` Variablen eng zusammenpacken und den Speicherverbrauch sparen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="b2abc-107">Der Standardwert von `SByte` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="b2abc-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="b2abc-108">Literale Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="b2abc-108">Literal assignments</span></span>

<span data-ttu-id="b2abc-109">Sie können eine `SByte` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="b2abc-110">Im folgenden Beispiel werden `SByte` Ganzzahlen gleich -102, die als Dezimal-, Hexadezimal- und Binärliterale dargestellt werden, Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="b2abc-111">In diesem Beispiel müssen `/removeintchecks` Sie mit dem Compilerschalter kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b2abc-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> <span data-ttu-id="b2abc-112">Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="b2abc-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="b2abc-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="b2abc-114">Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="b2abc-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

<span data-ttu-id="b2abc-115">Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2abc-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="b2abc-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b2abc-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="b2abc-117">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="b2abc-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="b2abc-118">Wenn ein Ganzzahlliteral kein Suffix hat, wird eine [ganze Zahl](integer-data-type.md) abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b2abc-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="b2abc-119">Wenn sich das Ganzzahlliteral außerhalb `Integer` des Bereichs des Typs befindet, wird ein [Long](long-data-type.md) abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b2abc-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="b2abc-120">Dies bedeutet, dass in den vorherigen `0x9A` `0b10011010` Beispielen <xref:System.SByte.MaxValue?displayProperty=nameWithType>die numerischen Literale und als 32-Bit-ganzer Ganzzahlen mit einem Wert von 156 interpretiert werden, der überschreitet.</span><span class="sxs-lookup"><span data-stu-id="b2abc-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2abc-121">Um Code wie diesen erfolgreich zu kompilieren, der `SByte`einer eine nicht dezimale Ganzzahl zuweist, können Sie eine der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b2abc-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="b2abc-122">Deaktivieren Sie ganzzahlige Begrenzungsprüfungen, `/removeintchecks` indem Sie mit dem Compilerschalter kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b2abc-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="b2abc-123">Verwenden Sie ein [Typzeichen,](../../programming-guide/language-features/data-types/type-characters.md) um explizit den Literalwert zu definieren, den Sie dem `SByte`zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="b2abc-123">Use a [type character](../../programming-guide/language-features/data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="b2abc-124">Im folgenden Beispiel wird `Short` einem `SByte`ein negativer Literalwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="b2abc-125">Beachten Sie, dass bei negativen Zahlen das Bit hoher Ordnung des Hochrangworts des numerischen Literals festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="b2abc-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="b2abc-126">Im Falle unseres Beispiels ist dies Bit `Short` 15 des Literalwerts.</span><span class="sxs-lookup"><span data-stu-id="b2abc-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="b2abc-127">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="b2abc-127">Programming tips</span></span>

- <span data-ttu-id="b2abc-128">**CLS-Compliance.**</span><span class="sxs-lookup"><span data-stu-id="b2abc-128">**CLS Compliance.**</span></span> <span data-ttu-id="b2abc-129">Der `SByte` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2abc-129">The `SByte` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="b2abc-130">**Erweiterung.**</span><span class="sxs-lookup"><span data-stu-id="b2abc-130">**Widening.**</span></span> <span data-ttu-id="b2abc-131">Der `SByte` Datentyp wird `Short` `Integer`auf `Long` `Decimal`, `Single`, `Double`, , und erweitert.</span><span class="sxs-lookup"><span data-stu-id="b2abc-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="b2abc-132">Dies bedeutet, `SByte` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="b2abc-133">**Typ Zeichen.**</span><span class="sxs-lookup"><span data-stu-id="b2abc-133">**Type Characters.**</span></span> <span data-ttu-id="b2abc-134">`SByte`hat kein Literaltypzeichen oder Bezeichnertypzeichen.</span><span class="sxs-lookup"><span data-stu-id="b2abc-134">`SByte` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="b2abc-135">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="b2abc-135">**Framework Type.**</span></span> <span data-ttu-id="b2abc-136">Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="b2abc-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2abc-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2abc-137">See also</span></span>

- <xref:System.SByte?displayProperty=nameWithType>
- [<span data-ttu-id="b2abc-138">Datentypen</span><span class="sxs-lookup"><span data-stu-id="b2abc-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="b2abc-139">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="b2abc-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="b2abc-140">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b2abc-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="b2abc-141">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b2abc-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="b2abc-142">Ganzzahl-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b2abc-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="b2abc-143">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b2abc-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="b2abc-144">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="b2abc-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
