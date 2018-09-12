---
title: UShort-Datentyp (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 038aad2c41f655d0699dab33df276132a70e3ede
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44511879"
---
# <a name="ushort-data-type-visual-basic"></a><span data-ttu-id="8afc5-102">UShort-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8afc5-102">UShort data type (Visual Basic)</span></span>

<span data-ttu-id="8afc5-103">Enthält 16-Bit (2-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 65.535.</span><span class="sxs-lookup"><span data-stu-id="8afc5-103">Holds unsigned 16-bit (2-byte) integers ranging in value from 0 through 65,535.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8afc5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8afc5-104">Remarks</span></span>

 <span data-ttu-id="8afc5-105">Verwenden der `UShort` Datentyp zu groß für die Binärdaten enthält `Byte`.</span><span class="sxs-lookup"><span data-stu-id="8afc5-105">Use the `UShort` data type to contain binary data too large for `Byte`.</span></span>  
  
 <span data-ttu-id="8afc5-106">Der Standardwert von `UShort` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="8afc5-106">The default value of `UShort` is 0.</span></span>  

# <a name="literal-assignments"></a><span data-ttu-id="8afc5-107">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="8afc5-107">Literal assignments</span></span>

<span data-ttu-id="8afc5-108">Sie können deklarieren und initialisieren eine `UShort` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="8afc5-108">You can declare and initialize a `UShort` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8afc5-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="8afc5-109">If the integer literal is outside the range of `UShort` (that is, if it is less than <xref:System.UInt16.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8afc5-110">Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden zugewiesen, `UShort` Werte.</span><span class="sxs-lookup"><span data-stu-id="8afc5-110">In the following example, integers equal to 65,034 that are represented as decimal, hexadecimal, and binary literals are assigned to `UShort` values.</span></span>
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> <span data-ttu-id="8afc5-111">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="8afc5-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8afc5-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="8afc5-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8afc5-113">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8afc5-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

<span data-ttu-id="8afc5-114">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="8afc5-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="8afc5-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8afc5-115">For example:</span></span>

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="8afc5-116">Numerische Literale können auch einschließen, die `US` oder `us` [Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `UShort` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="8afc5-116">Numeric literals can also include the `US` or `us` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UShort` data type, as the following example shows.</span></span>

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a><span data-ttu-id="8afc5-117">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="8afc5-117">Programming tips</span></span>
  
-   <span data-ttu-id="8afc5-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="8afc5-118">**Negative Numbers.**</span></span> <span data-ttu-id="8afc5-119">Da `UShort` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen.</span><span class="sxs-lookup"><span data-stu-id="8afc5-119">Because `UShort` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="8afc5-120">Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `UShort`, konvertiert den Ausdruck, der Visual Basic `Integer` erste.</span><span class="sxs-lookup"><span data-stu-id="8afc5-120">If you use the unary minus (`-`) operator on an expression that evaluates to type `UShort`, Visual Basic converts the expression to `Integer` first.</span></span>  
  
-   <span data-ttu-id="8afc5-121">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="8afc5-121">**CLS Compliance.**</span></span> <span data-ttu-id="8afc5-122">Die `UShort` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8afc5-122">The `UShort` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="8afc5-123">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="8afc5-123">**Widening.**</span></span> <span data-ttu-id="8afc5-124">Die `UShort` -Datentyp wird zu `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="8afc5-124">The `UShort` data type widens to `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="8afc5-125">Dies bedeutet, Sie können konvertieren `UShort` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="8afc5-125">This means you can convert `UShort` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="8afc5-126">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="8afc5-126">**Type Characters.**</span></span> <span data-ttu-id="8afc5-127">Durch Anhängen des Literaltypzeichens `US` an ein Literal wird der `UShort` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="8afc5-127">Appending the literal type characters `US` to a literal forces it to the `UShort` data type.</span></span> <span data-ttu-id="8afc5-128">`UShort` verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="8afc5-128">`UShort` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="8afc5-129">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="8afc5-129">**Framework Type.**</span></span> <span data-ttu-id="8afc5-130">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="8afc5-130">The corresponding type in the .NET Framework is the <xref:System.UInt16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8afc5-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8afc5-131">See Also</span></span>  
 <xref:System.UInt16>  
 [<span data-ttu-id="8afc5-132">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8afc5-132">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="8afc5-133">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="8afc5-133">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="8afc5-134">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8afc5-134">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="8afc5-135">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="8afc5-135">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="8afc5-136">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="8afc5-136">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
