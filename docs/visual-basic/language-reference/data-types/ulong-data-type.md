---
title: ULong-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343882"
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="045a1-102">ULong-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="045a1-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="045a1-103">Enthält nicht signierte 64-Bit-Ganzzahlen (8 Byte) mit einem Wert von 0 bis 18446744073709551615 (mehr als 1,84 mal 10 ^ 19).</span><span class="sxs-lookup"><span data-stu-id="045a1-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>

## <a name="remarks"></a><span data-ttu-id="045a1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="045a1-104">Remarks</span></span>

<span data-ttu-id="045a1-105">Verwenden Sie den `ULong`-Datentyp, um Binärdaten zu enthalten, die für `UInteger`zu groß sind, oder die größtmöglichen ganzzahligen Werte ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="045a1-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>

<span data-ttu-id="045a1-106">Der Standardwert von `ULong` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="045a1-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="045a1-107">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="045a1-107">Literal assignments</span></span>

<span data-ttu-id="045a1-108">Sie können eine `ULong` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="045a1-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="045a1-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="045a1-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="045a1-110">Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="045a1-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> <span data-ttu-id="045a1-111">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="045a1-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="045a1-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="045a1-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="045a1-113">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="045a1-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="045a1-114">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="045a1-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="045a1-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="045a1-115">For example:</span></span>

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="045a1-116">Numerische Literale können auch das `UL` oder `ul` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `ULong` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="045a1-116">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="045a1-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="045a1-117">Programming tips</span></span>

- <span data-ttu-id="045a1-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="045a1-118">**Negative Numbers.**</span></span> <span data-ttu-id="045a1-119">Da `ULong` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="045a1-119">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="045a1-120">Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `ULong`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="045a1-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>

- <span data-ttu-id="045a1-121">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="045a1-121">**CLS Compliance.**</span></span> <span data-ttu-id="045a1-122">Der `ULong`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="045a1-122">The `ULong` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="045a1-123">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="045a1-123">**Interop Considerations.**</span></span> <span data-ttu-id="045a1-124">Wenn Sie mit Komponenten interagieren, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Typen wie `ulong` in anderen Umgebungen eine andere Daten Breite (32 Bits) aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="045a1-124">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="045a1-125">Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UInteger`, anstatt `ULong` in Ihrem verwalteten Visual Basic-Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="045a1-125">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>

  <span data-ttu-id="045a1-126">Außerdem werden in Windows 95, Windows 98, Windows Me oder Windows 2000 keine 64-Bit-Ganzzahlen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="045a1-126">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="045a1-127">Es ist nicht möglich, ein Visual Basic `ULong`-Argument an eine Automatisierungskomponente auf diesen Plattformen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="045a1-127">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>

- <span data-ttu-id="045a1-128">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="045a1-128">**Widening.**</span></span> <span data-ttu-id="045a1-129">Der `ULong`-Datentyp wird auf `Decimal`, `Single`und `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="045a1-129">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="045a1-130">Dies bedeutet, dass Sie `ULong` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="045a1-130">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="045a1-131">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="045a1-131">**Type Characters.**</span></span> <span data-ttu-id="045a1-132">Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `UL` werden, wird der Datentyp `ULong`</span><span class="sxs-lookup"><span data-stu-id="045a1-132">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="045a1-133">`ULong` hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="045a1-133">`ULong` has no identifier type character.</span></span>

- <span data-ttu-id="045a1-134">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="045a1-134">**Framework Type.**</span></span> <span data-ttu-id="045a1-135">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="045a1-135">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="045a1-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="045a1-136">See also</span></span>

- <xref:System.UInt64>
- [<span data-ttu-id="045a1-137">Datentypen</span><span class="sxs-lookup"><span data-stu-id="045a1-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="045a1-138">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="045a1-138">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="045a1-139">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="045a1-139">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="045a1-140">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="045a1-140">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="045a1-141">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="045a1-141">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
