---
title: Long-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343975"
---
# <a name="long-data-type-visual-basic"></a><span data-ttu-id="00e28-102">Long-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00e28-102">Long data type (Visual Basic)</span></span>

<span data-ttu-id="00e28-103">Enthält signierte 64-Bit-Ganzzahlen (8 Byte) mit einem Wert von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 (9.2... E + 18).</span><span class="sxs-lookup"><span data-stu-id="00e28-103">Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).</span></span>

## <a name="remarks"></a><span data-ttu-id="00e28-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00e28-104">Remarks</span></span>

<span data-ttu-id="00e28-105">Verwenden Sie den `Long`-Datentyp, um ganzzahlige Zahlen zu enthalten, die zu groß für den `Integer` Datentyp sind.</span><span class="sxs-lookup"><span data-stu-id="00e28-105">Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.</span></span>

<span data-ttu-id="00e28-106">Der Standardwert von `Long` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="00e28-106">The default value of `Long` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="00e28-107">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="00e28-107">Literal assignments</span></span>

<span data-ttu-id="00e28-108">Sie können eine `Long` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="00e28-108">You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="00e28-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Long` befindet – sprich, wenn es kleiner als <xref:System.Int64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="00e28-109">If the integer literal is outside the range of `Long` (that is, if it is less than <xref:System.Int64.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="00e28-110">Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Long`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="00e28-110">In the following example, integers equal to 4,294,967,296 that are represented as decimal, hexadecimal, and binary literals are assigned to `Long` values.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> <span data-ttu-id="00e28-111">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="00e28-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="00e28-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="00e28-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="00e28-113">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00e28-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="00e28-114">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="00e28-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="00e28-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="00e28-115">For example:</span></span>

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="00e28-116">Numerische Literale können auch das `L` [Type-Zeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Long` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00e28-116">Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a><span data-ttu-id="00e28-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="00e28-117">Programming tips</span></span>

- <span data-ttu-id="00e28-118">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="00e28-118">**Interop Considerations.**</span></span> <span data-ttu-id="00e28-119">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), denken Sie daran, dass `Long` in anderen Umgebungen eine andere Daten Breite (32 Bits) aufweist.</span><span class="sxs-lookup"><span data-stu-id="00e28-119">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="00e28-120">Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Integer`, anstatt `Long` im neuen Visual Basic Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="00e28-120">If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.</span></span>

- <span data-ttu-id="00e28-121">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="00e28-121">**Widening.**</span></span> <span data-ttu-id="00e28-122">Der `Long`-Datentyp wird zu `Decimal`, `Single`oder `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="00e28-122">The `Long` data type widens to `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="00e28-123">Dies bedeutet, dass Sie `Long` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="00e28-123">This means you can convert `Long` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="00e28-124">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="00e28-124">**Type Characters.**</span></span> <span data-ttu-id="00e28-125">Durch Anhängen des Literaltypzeichens `L` an ein Literal wird der `Long`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="00e28-125">Appending the literal type character `L` to a literal forces it to the `Long` data type.</span></span> <span data-ttu-id="00e28-126">Durch Anhängen des Typkennzeichens `&` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Long`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="00e28-126">Appending the identifier type character `&` to any identifier forces it to `Long`.</span></span>

- <span data-ttu-id="00e28-127">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="00e28-127">**Framework Type.**</span></span> <span data-ttu-id="00e28-128">Der entsprechende Typ in .NET Framework ist die <xref:System.Int64?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="00e28-128">The corresponding type in the .NET Framework is the <xref:System.Int64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="00e28-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00e28-129">See also</span></span>

- <xref:System.Int64>
- [<span data-ttu-id="00e28-130">Datentypen</span><span class="sxs-lookup"><span data-stu-id="00e28-130">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="00e28-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="00e28-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="00e28-132">Short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="00e28-132">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [<span data-ttu-id="00e28-133">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="00e28-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="00e28-134">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="00e28-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="00e28-135">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="00e28-135">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
