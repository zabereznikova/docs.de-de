---
title: Short-Datentyp (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="36c02-102">Short-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36c02-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="36c02-103">Speichert signierte 16-Bit (2-Byte) ganze Zahlen, die im Wert von-32.768 bis 32.767 reichen.</span><span class="sxs-lookup"><span data-stu-id="36c02-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36c02-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36c02-104">Remarks</span></span>  
 <span data-ttu-id="36c02-105">Verwenden der `Short` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer`.</span><span class="sxs-lookup"><span data-stu-id="36c02-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="36c02-106">In einigen Fällen kann die common Language Runtime pack Ihre `Short` Variablen eng zusammen, und speichern Sie den Arbeitsspeicherverbrauch.</span><span class="sxs-lookup"><span data-stu-id="36c02-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="36c02-107">Der Standardwert von `Short` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="36c02-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="36c02-108">Literal Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="36c02-108">Literal assignments</span></span>

<span data-ttu-id="36c02-109">Sie können deklarieren und Initialisieren einer `Short` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="36c02-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="36c02-110">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="36c02-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="36c02-111">Im folgenden Beispiel Ganzzahlen 1,034 ab, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale werden implizit konvertiert, aus [Ganzzahl](integer-data-type.md) zu `Short` Werte.</span><span class="sxs-lookup"><span data-stu-id="36c02-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="36c02-112">Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="36c02-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="36c02-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="36c02-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="36c02-114">Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="36c02-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="36c02-115">Numerische Literale zählen auch die `S` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `Short` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="36c02-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="36c02-116">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="36c02-116">Programming tips</span></span>

-   <span data-ttu-id="36c02-117">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="36c02-117">**Widening.**</span></span> <span data-ttu-id="36c02-118">Die `Short` -Datentyp zu `Integer`, `Long`, `Decimal`, `Single`, oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="36c02-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="36c02-119">Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="36c02-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="36c02-120">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="36c02-120">**Type Characters.**</span></span> <span data-ttu-id="36c02-121">Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="36c02-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="36c02-122">`Short`verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="36c02-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="36c02-123">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="36c02-123">**Framework Type.**</span></span> <span data-ttu-id="36c02-124">Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="36c02-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36c02-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36c02-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="36c02-126">Datentypen</span><span class="sxs-lookup"><span data-stu-id="36c02-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="36c02-127">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="36c02-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="36c02-128">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="36c02-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="36c02-129">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="36c02-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="36c02-130">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="36c02-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="36c02-131">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="36c02-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
