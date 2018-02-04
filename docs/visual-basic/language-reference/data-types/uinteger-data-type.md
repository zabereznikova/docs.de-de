---
title: UInteger-Datentyp
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea6d42a604e5a50fab62644034afc82e089792c7
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="uinteger-data-type"></a><span data-ttu-id="760ff-102">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="760ff-102">UInteger data type</span></span>

<span data-ttu-id="760ff-103">Enthält 32-Bit (4-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 4.294.967.295.</span><span class="sxs-lookup"><span data-stu-id="760ff-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="760ff-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="760ff-104">Remarks</span></span>

 <span data-ttu-id="760ff-105">Die `UInteger` -Datentyp stellt den größten Wert ohne Vorzeichen in die effizienteste Datenbreite bereit.</span><span class="sxs-lookup"><span data-stu-id="760ff-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="760ff-106">Der Standardwert von `UInteger` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="760ff-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="760ff-107">Literal Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="760ff-107">Literal assignments</span></span>

<span data-ttu-id="760ff-108">Sie können deklarieren und Initialisieren einer `UInteger` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="760ff-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="760ff-109">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="760ff-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="760ff-110">Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="760ff-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="760ff-111">Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="760ff-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="760ff-112">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="760ff-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="760ff-113">Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="760ff-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="760ff-114">Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern.</span><span class="sxs-lookup"><span data-stu-id="760ff-114">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="760ff-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="760ff-115">For example:</span></span>

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="760ff-116">Numerische Literale zählen auch die `UI` oder `ui` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `UInteger` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="760ff-116">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="760ff-117">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="760ff-117">Programming tips</span></span>

 <span data-ttu-id="760ff-118">Die `UInteger` und `Integer` Datentypen bereitstellen auf einem 32-Bit-Prozessor eine optimale Leistung, weil die kleineren ganzzahlige Typen (`UShort`, `Short`, `Byte`, und `SByte`), auch wenn sie weniger Bits verwendet mehr Zeit in Anspruch nehmen Laden, speichern und abrufen.</span><span class="sxs-lookup"><span data-stu-id="760ff-118">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="760ff-119">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="760ff-119">**Negative Numbers.**</span></span> <span data-ttu-id="760ff-120">Da `UInteger` ein Typ ohne Vorzeichen ist es nicht darstellen kann eine negative Zahl.</span><span class="sxs-lookup"><span data-stu-id="760ff-120">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="760ff-121">Bei Verwendung der unäres minus (`-`) Operator auf einen Ausdruck, der ausgewertet wird, um geben `UInteger`, konvertiert den Ausdruck, der Visual Basic `Long` erste.</span><span class="sxs-lookup"><span data-stu-id="760ff-121">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="760ff-122">**CLS-Kompatibilität.**</span><span class="sxs-lookup"><span data-stu-id="760ff-122">**CLS Compliance.**</span></span> <span data-ttu-id="760ff-123">Die `UInteger` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="760ff-123">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="760ff-124">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="760ff-124">**Interop Considerations.**</span></span> <span data-ttu-id="760ff-125">Wenn Sie Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen Datenbreite bedenken, die von wie z. B. Typen `uint` in anderen Umgebungen können eine andere Datenbreite (16 Bits) vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="760ff-125">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="760ff-126">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort` anstelle von `UInteger` im verwalteten Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="760ff-126">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="760ff-127">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="760ff-127">**Widening.**</span></span> <span data-ttu-id="760ff-128">Die `UInteger` -Datentyp zu `Long`, `ULong`, `Decimal`, `Single`, und `Double`.</span><span class="sxs-lookup"><span data-stu-id="760ff-128">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="760ff-129">Dies bedeutet, Sie können konvertieren `UInteger` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="760ff-129">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="760ff-130">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="760ff-130">**Type Characters.**</span></span> <span data-ttu-id="760ff-131">Anhängen des Literaltypzeichens `UI` an ein Literal wird der `UInteger` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="760ff-131">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="760ff-132">`UInteger`verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="760ff-132">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="760ff-133">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="760ff-133">**Framework Type.**</span></span> <span data-ttu-id="760ff-134">Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="760ff-134">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760ff-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="760ff-135">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="760ff-136">Datentypen</span><span class="sxs-lookup"><span data-stu-id="760ff-136">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="760ff-137">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="760ff-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="760ff-138">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="760ff-138">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="760ff-139">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="760ff-139">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="760ff-140">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="760ff-140">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
