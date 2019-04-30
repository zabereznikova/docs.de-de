---
title: Short-Datentyp (Visual Basic)
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
ms.openlocfilehash: d4dab1a72d1e240bc428b2c6b83a722584e35ecc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971794"
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="825f1-102">Short-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="825f1-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="825f1-103">Speichert signierte ganze Zahlen 16-Bit-(2-Byte), die im Wert von-32.768 bis 32.767 reichen.</span><span class="sxs-lookup"><span data-stu-id="825f1-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="825f1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="825f1-104">Remarks</span></span>  
 <span data-ttu-id="825f1-105">Verwenden der `Short` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer`.</span><span class="sxs-lookup"><span data-stu-id="825f1-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="825f1-106">In einigen Fällen die common Language Runtime pack kann Ihre `Short` Variablen, die eng zusammen und Arbeitsspeicher belegt.</span><span class="sxs-lookup"><span data-stu-id="825f1-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="825f1-107">Der Standardwert von `Short` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="825f1-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="825f1-108">Zuweisung von literalen</span><span class="sxs-lookup"><span data-stu-id="825f1-108">Literal assignments</span></span>

<span data-ttu-id="825f1-109">Sie können deklarieren und initialisieren eine `Short` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.</span><span class="sxs-lookup"><span data-stu-id="825f1-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="825f1-110">Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.</span><span class="sxs-lookup"><span data-stu-id="825f1-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="825f1-111">Im folgenden Beispiel werden Ganzzahlen wie 1.034, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden implizit konvertiert, von [Ganzzahl](integer-data-type.md) zu `Short` Werte.</span><span class="sxs-lookup"><span data-stu-id="825f1-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="825f1-112">Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="825f1-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="825f1-113">Dezimale Literale haben kein Präfix.</span><span class="sxs-lookup"><span data-stu-id="825f1-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="825f1-114">Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="825f1-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="825f1-115">Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern.</span><span class="sxs-lookup"><span data-stu-id="825f1-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="825f1-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="825f1-116">For example:</span></span>

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="825f1-117">Numerische Literale können auch einschließen, die `S` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `Short` -Datentyp, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="825f1-117">Numeric literals can also include the `S` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a><span data-ttu-id="825f1-118">Tipps für die Programmierung</span><span class="sxs-lookup"><span data-stu-id="825f1-118">Programming tips</span></span>

- <span data-ttu-id="825f1-119">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="825f1-119">**Widening.**</span></span> <span data-ttu-id="825f1-120">Die `Short` -Datentyp wird zu `Integer`, `Long`, `Decimal`, `Single`, oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="825f1-120">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="825f1-121">Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="825f1-121">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="825f1-122">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="825f1-122">**Type Characters.**</span></span> <span data-ttu-id="825f1-123">Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="825f1-123">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="825f1-124">`Short` verfügt über keine Typkennzeichen aus.</span><span class="sxs-lookup"><span data-stu-id="825f1-124">`Short` has no identifier type character.</span></span>  
  
- <span data-ttu-id="825f1-125">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="825f1-125">**Framework Type.**</span></span> <span data-ttu-id="825f1-126">Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="825f1-126">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825f1-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="825f1-127">See also</span></span>

- <xref:System.Int16?displayProperty=nameWithType>
- [<span data-ttu-id="825f1-128">Datentypen</span><span class="sxs-lookup"><span data-stu-id="825f1-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="825f1-129">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="825f1-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="825f1-130">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="825f1-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="825f1-131">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="825f1-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="825f1-132">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="825f1-132">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [<span data-ttu-id="825f1-133">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="825f1-133">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
