---
title: Short-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Short
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
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343933"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="82053-102">Short-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82053-102">Short data type (Visual Basic)</span></span>

<span data-ttu-id="82053-103">Enthält ganze 16-Bit-Zahlen (2 Bytes) mit Vorzeichen, die den Wert von-32.768 bis 32.767 über liegen.</span><span class="sxs-lookup"><span data-stu-id="82053-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82053-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82053-104">Remarks</span></span>  

 <span data-ttu-id="82053-105">Verwenden Sie den `Short`-Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von `Integer`erfordern.</span><span class="sxs-lookup"><span data-stu-id="82053-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="82053-106">In einigen Fällen können die Common Language Runtime ihre `Short` Variablen eng zusammenpacken und den Speicherverbrauch sparen.</span><span class="sxs-lookup"><span data-stu-id="82053-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="82053-107">Der Standardwert von `Short` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="82053-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="82053-108">Literalzuweisungen</span><span class="sxs-lookup"><span data-stu-id="82053-108">Literal assignments</span></span>

<span data-ttu-id="82053-109">Sie können eine `Short` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="82053-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="82053-110">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="82053-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="82053-111">Im folgenden Beispiel werden ganze Zahlen, die gleich 1.034 sind und als Dezimal-, hexadezimale und binäre Literale dargestellt werden, implizit von einer [Ganzzahl](integer-data-type.md) in `Short` Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="82053-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="82053-112">Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben.</span><span class="sxs-lookup"><span data-stu-id="82053-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="82053-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="82053-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="82053-114">Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82053-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="82053-115">Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden.</span><span class="sxs-lookup"><span data-stu-id="82053-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="82053-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="82053-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="82053-117">Numerische Literale können auch das `S` [Type-Zeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Short` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="82053-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="82053-118">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="82053-118">Programming tips</span></span>

- <span data-ttu-id="82053-119">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="82053-119">**Widening.**</span></span> <span data-ttu-id="82053-120">Der `Short`-Datentyp wird auf `Integer`, `Long`, `Decimal`, `Single`oder `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="82053-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="82053-121">Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="82053-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="82053-122">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="82053-122">**Type Characters.**</span></span> <span data-ttu-id="82053-123">Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="82053-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="82053-124">`Short` hat kein Bezeichnertyp Zeichen.</span><span class="sxs-lookup"><span data-stu-id="82053-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="82053-125">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="82053-125">**Framework Type.**</span></span> <span data-ttu-id="82053-126">Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="82053-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82053-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82053-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="82053-128">Datentypen</span><span class="sxs-lookup"><span data-stu-id="82053-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="82053-129">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="82053-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="82053-130">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="82053-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="82053-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="82053-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="82053-132">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="82053-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="82053-133">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="82053-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
