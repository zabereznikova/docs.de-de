---
title: UShort-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343855"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="1b6ac-102">Ushort-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b6ac-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="1b6ac-103">Enthält ganze 16-Bit-Ganzzahlen (2 Bytes) ohne Vorzeichen, die einen Wert von 0 bis 65.535 enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b6ac-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b6ac-104">Remarks</span></span>

 <span data-ttu-id="1b6ac-105">Verwenden Sie den Datentyp `UShort`, um Binärdaten zu enthalten, die für `Byte`zu groß sind.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="1b6ac-106">Der Standardwert von `UShort` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="1b6ac-107">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="1b6ac-107">Literal assignments</span></span>

<span data-ttu-id="1b6ac-108">Sie können eine `UShort` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="1b6ac-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="1b6ac-110">Im folgenden Beispiel werden ganze Zahlen gleich 65.034, die als Dezimal-, hexadezimale und binäre Literale dargestellt werden, `UShort` Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="1b6ac-111">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="1b6ac-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="1b6ac-113">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="1b6ac-114">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="1b6ac-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1b6ac-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="1b6ac-116">Numerische Literale können auch das `US` oder `us` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UShort` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="1b6ac-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="1b6ac-117">Programming tips</span></span>
  
- <span data-ttu-id="1b6ac-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="1b6ac-118">**Negative Numbers.**</span></span> <span data-ttu-id="1b6ac-119">Da `UShort` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="1b6ac-120">Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `UShort`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="1b6ac-121">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="1b6ac-121">**CLS Compliance.**</span></span> <span data-ttu-id="1b6ac-122">Der `UShort`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="1b6ac-123">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="1b6ac-123">**Widening.**</span></span> <span data-ttu-id="1b6ac-124">Der `UShort`-Datentyp wird auf `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`und `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="1b6ac-125">Dies bedeutet, dass Sie `UShort` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="1b6ac-126">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="1b6ac-126">**Type Characters.**</span></span> <span data-ttu-id="1b6ac-127">Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `US` werden, wird der Datentyp `UShort`</span><span class="sxs-lookup"><span data-stu-id="1b6ac-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="1b6ac-128">`UShort` hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="1b6ac-129">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="1b6ac-129">**Framework Type.**</span></span> <span data-ttu-id="1b6ac-130">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="1b6ac-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6ac-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b6ac-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="1b6ac-132">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1b6ac-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="1b6ac-133">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="1b6ac-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1b6ac-134">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="1b6ac-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="1b6ac-135">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="1b6ac-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="1b6ac-136">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="1b6ac-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
