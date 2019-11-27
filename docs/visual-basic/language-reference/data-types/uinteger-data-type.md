---
title: UInteger-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343890"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="5dcb2-102">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5dcb2-102">UInteger data type</span></span>

<span data-ttu-id="5dcb2-103">Enthält nicht signierte 32-Bit-Ganzzahlen (4 Bytes) mit einem Wert von 0 bis 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>

## <a name="remarks"></a><span data-ttu-id="5dcb2-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dcb2-104">Remarks</span></span>

<span data-ttu-id="5dcb2-105">Der `UInteger`-Datentyp stellt den größten Wert ohne Vorzeichen in der effizientesten Daten Breite bereit.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>

<span data-ttu-id="5dcb2-106">Der Standardwert von `UInteger` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-106">The default value of `UInteger` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="5dcb2-107">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="5dcb2-107">Literal assignments</span></span>

<span data-ttu-id="5dcb2-108">Sie können eine `UInteger` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5dcb2-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5dcb2-110">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> <span data-ttu-id="5dcb2-111">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5dcb2-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5dcb2-113">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

<span data-ttu-id="5dcb2-114">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="5dcb2-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5dcb2-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="5dcb2-116">Numerische Literale können auch das `UI` oder `ui` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UInteger` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="5dcb2-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="5dcb2-117">Programming tips</span></span>

<span data-ttu-id="5dcb2-118">Die Datentypen "`UInteger`" und "`Integer`" bieten eine optimale Leistung für einen 32-Bit-Prozessor, da die kleineren ganzzahligen Typen (`UShort`, `Short`, `Byte`und `SByte`), auch wenn weniger Bits verwendet werden, mehr Zeit zum Laden, speichern und Abrufen benötigen.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>

- <span data-ttu-id="5dcb2-119">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-119">**Negative Numbers.**</span></span> <span data-ttu-id="5dcb2-120">Da `UInteger` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5dcb2-121">Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `UInteger`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Long`.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>

- <span data-ttu-id="5dcb2-122">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-122">**CLS Compliance.**</span></span> <span data-ttu-id="5dcb2-123">Der `UInteger`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

- <span data-ttu-id="5dcb2-124">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-124">**Interop Considerations.**</span></span> <span data-ttu-id="5dcb2-125">Wenn Sie mit Komponenten interagieren, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Typen wie `uint` in anderen Umgebungen eine andere Daten Breite (16 Bits) aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="5dcb2-126">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort`, anstatt `UInteger` in Ihrem verwalteten Visual Basic-Code zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>

- <span data-ttu-id="5dcb2-127">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-127">**Widening.**</span></span> <span data-ttu-id="5dcb2-128">Der `UInteger`-Datentyp wird auf `Long`, `ULong`, `Decimal`, `Single`und `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5dcb2-129">Dies bedeutet, dass Sie `UInteger` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

- <span data-ttu-id="5dcb2-130">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-130">**Type Characters.**</span></span> <span data-ttu-id="5dcb2-131">Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `UI` werden, wird der Datentyp `UInteger`</span><span class="sxs-lookup"><span data-stu-id="5dcb2-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="5dcb2-132">`UInteger` hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-132">`UInteger` has no identifier type character.</span></span>

- <span data-ttu-id="5dcb2-133">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="5dcb2-133">**Framework Type.**</span></span> <span data-ttu-id="5dcb2-134">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="5dcb2-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="5dcb2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dcb2-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="5dcb2-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="5dcb2-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5dcb2-137">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="5dcb2-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5dcb2-138">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="5dcb2-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5dcb2-139">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="5dcb2-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="5dcb2-140">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="5dcb2-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
