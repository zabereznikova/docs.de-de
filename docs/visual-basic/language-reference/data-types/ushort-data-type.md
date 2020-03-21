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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401310"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="cb100-102">UKurzer Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb100-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="cb100-103">Enthält nicht signierte 16-Bit-Ganzzahlen (2-Byte) im Wert von 0 bis 65.535.</span><span class="sxs-lookup"><span data-stu-id="cb100-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb100-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cb100-104">Remarks</span></span>

 <span data-ttu-id="cb100-105">Verwenden `UShort` Sie den Datentyp, um `Byte`Binärdaten zu groß für zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb100-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="cb100-106">Der Standardwert von `UShort` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="cb100-106">The default value of `UShort` is 0.</span></span>  

## <a name="literal-assignments"></a><span data-ttu-id="cb100-107">Literale Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="cb100-107">Literal assignments</span></span>

<span data-ttu-id="cb100-108">Sie können eine `UShort` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cb100-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="cb100-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="cb100-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="cb100-110">Im folgenden Beispiel werden `UShort` Ganzzahlen von 65.034, die als Dezimal-, Hexadezimal- und Binärliterale dargestellt werden, Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cb100-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="cb100-111">Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen.</span><span class="sxs-lookup"><span data-stu-id="cb100-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="cb100-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="cb100-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="cb100-113">Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="cb100-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="cb100-114">Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb100-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="cb100-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb100-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="cb100-116">Numerische Literale können `US` auch `us` das oder [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UShort` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="cb100-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="cb100-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="cb100-117">Programming tips</span></span>
  
- <span data-ttu-id="cb100-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="cb100-118">**Negative Numbers.**</span></span> <span data-ttu-id="cb100-119">Da `UShort` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen.</span><span class="sxs-lookup"><span data-stu-id="cb100-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="cb100-120">Wenn Sie den Operator`-`unary minus ( ) für `UShort`einen Ausdruck verwenden, `Integer` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.</span><span class="sxs-lookup"><span data-stu-id="cb100-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
- <span data-ttu-id="cb100-121">**CLS-Compliance.**</span><span class="sxs-lookup"><span data-stu-id="cb100-121">**CLS Compliance.**</span></span> <span data-ttu-id="cb100-122">Der `UShort` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb100-122">The `UShort` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
- <span data-ttu-id="cb100-123">**Erweiterung.**</span><span class="sxs-lookup"><span data-stu-id="cb100-123">**Widening.**</span></span> <span data-ttu-id="cb100-124">Der `UShort` Datentyp wird `Integer` `UInteger`auf `Long` `ULong`, `Decimal` `Single`, `Double`, , , und erweitert.</span><span class="sxs-lookup"><span data-stu-id="cb100-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="cb100-125">Dies bedeutet, `UShort` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.</span><span class="sxs-lookup"><span data-stu-id="cb100-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="cb100-126">**Typ Zeichen.**</span><span class="sxs-lookup"><span data-stu-id="cb100-126">**Type Characters.**</span></span> <span data-ttu-id="cb100-127">Das Anfügen der `US` Literaltypzeichen an `UShort` ein Literal erzwingt, dass es an den Datentyp gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="cb100-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="cb100-128">`UShort`hat kein Bezeichnertypzeichen.</span><span class="sxs-lookup"><span data-stu-id="cb100-128">`UShort` has no identifier type character.</span></span>  
  
- <span data-ttu-id="cb100-129">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="cb100-129">**Framework Type.**</span></span> <span data-ttu-id="cb100-130">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="cb100-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb100-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb100-131">See also</span></span>

- <xref:System.UInt16>
- [<span data-ttu-id="cb100-132">Datentypen</span><span class="sxs-lookup"><span data-stu-id="cb100-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="cb100-133">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="cb100-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="cb100-134">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="cb100-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="cb100-135">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="cb100-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="cb100-136">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="cb100-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
