---
title: UInteger-Datentyp (Visual Basic)
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
ms.openlocfilehash: 4d93b1e40371b00f9d1ff69ec31ad0983beb493f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821490"
---
# <a name="uinteger-data-type"></a><span data-ttu-id="6e174-102">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="6e174-102">UInteger data type</span></span>

<span data-ttu-id="6e174-103">Enthält 32-Bit (4-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="6e174-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e174-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e174-104">Remarks</span></span>

 <span data-ttu-id="6e174-105">Die `UInteger` -Datentyp bietet den größten Wert ohne Vorzeichen in die Breite der effizienteste.</span><span class="sxs-lookup"><span data-stu-id="6e174-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="6e174-106">Der Standardwert von `UInteger` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="6e174-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="6e174-107">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="6e174-107">Literal assignments</span></span>

<span data-ttu-id="6e174-108">Sie können deklarieren und initialisieren eine `UInteger` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="6e174-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="6e174-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="6e174-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="6e174-110">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6e174-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="6e174-111">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="6e174-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="6e174-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="6e174-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="6e174-113">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e174-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="6e174-114">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="6e174-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6e174-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6e174-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="6e174-116">Numerische Literale können auch einschließen, die `UI` oder `ui` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `UInteger` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e174-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="6e174-117">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="6e174-117">Programming tips</span></span>

 <span data-ttu-id="6e174-118">Die `UInteger` und `Integer` Datentypen auf einem 32-Bit-Prozessor, eine optimale Leistung bereit, da die kleineren ganzzahlige Typen (`UShort`, `Short`, `Byte`, und `SByte`), auch wenn sie weniger Bits verwendet mehr Zeit in Anspruch Laden, speichern und abrufen.</span><span class="sxs-lookup"><span data-stu-id="6e174-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="6e174-119">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="6e174-119">**Negative Numbers.**</span></span> <span data-ttu-id="6e174-120">Da `UInteger` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen.</span><span class="sxs-lookup"><span data-stu-id="6e174-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="6e174-121">Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `UInteger`, konvertiert den Ausdruck, der Visual Basic `Long` erste.</span><span class="sxs-lookup"><span data-stu-id="6e174-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="6e174-122">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="6e174-122">**CLS Compliance.**</span></span> <span data-ttu-id="6e174-123">Die `UInteger` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e174-123">The `UInteger` data type is not part of the [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="6e174-124">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="6e174-124">**Interop Considerations.**</span></span> <span data-ttu-id="6e174-125">Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, die Typen wie `uint` haben eine andere Datenbreite (16 Bits) in anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="6e174-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="6e174-126">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="6e174-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="6e174-127">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="6e174-127">**Widening.**</span></span> <span data-ttu-id="6e174-128">Die `UInteger` -Datentyp wird zu `Long`, `ULong`, `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="6e174-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="6e174-129">Dies bedeutet, Sie können konvertieren `UInteger` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="6e174-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="6e174-130">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="6e174-130">**Type Characters.**</span></span> <span data-ttu-id="6e174-131">Durch Anhängen des Literaltypzeichens `UI` an ein Literal wird der `UInteger` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="6e174-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="6e174-132">`UInteger` verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="6e174-132">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="6e174-133">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="6e174-133">**Framework Type.**</span></span> <span data-ttu-id="6e174-134">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="6e174-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e174-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e174-135">See also</span></span>

- <xref:System.UInt32>
- [<span data-ttu-id="6e174-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="6e174-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="6e174-137">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="6e174-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="6e174-138">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="6e174-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="6e174-139">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="6e174-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="6e174-140">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="6e174-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
