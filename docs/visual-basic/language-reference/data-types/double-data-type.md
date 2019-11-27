---
title: Double-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 347b5c7b7af4c4aafec0f91aca46a8cf640236b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344013"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="abd86-102">Double-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abd86-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="abd86-103">Enthält signierte IEEE 64-Bit (8-Byte)-Gleit Komma Zahlen mit doppelter Genauigkeit, die den Wert from-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 für negative Werte und von 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="abd86-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="abd86-104">Zahlen mit doppelter Genauigkeit speichern eine Näherung einer reellen Zahl.</span><span class="sxs-lookup"><span data-stu-id="abd86-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="abd86-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abd86-105">Remarks</span></span>

<span data-ttu-id="abd86-106">Der `Double`-Datentyp bietet die größte und kleinste mögliche Vergrößerung für eine Zahl.</span><span class="sxs-lookup"><span data-stu-id="abd86-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="abd86-107">Der Standardwert von `Double` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="abd86-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="abd86-108">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="abd86-108">Programming Tips</span></span>

- <span data-ttu-id="abd86-109">**Präziser.**</span><span class="sxs-lookup"><span data-stu-id="abd86-109">**Precision.**</span></span> <span data-ttu-id="abd86-110">Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="abd86-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="abd86-111">Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der `Mod`-Operator.</span><span class="sxs-lookup"><span data-stu-id="abd86-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="abd86-112">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="abd86-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="abd86-113">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="abd86-113">**Trailing Zeros.**</span></span> <span data-ttu-id="abd86-114">Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="abd86-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="abd86-115">Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2.</span><span class="sxs-lookup"><span data-stu-id="abd86-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="abd86-116">Folglich werden nachfolgende NULL-Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.</span><span class="sxs-lookup"><span data-stu-id="abd86-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="abd86-117">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="abd86-117">**Type Characters.**</span></span> <span data-ttu-id="abd86-118">Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="abd86-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="abd86-119">Wenn z. b. auf einen ganzzahligen Wert `R`folgt, wird der Wert in einen `Double`geändert.</span><span class="sxs-lookup"><span data-stu-id="abd86-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="abd86-120">Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="abd86-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="abd86-121">Im folgenden Beispiel wird die Variable `num` als `Double`typisiert:</span><span class="sxs-lookup"><span data-stu-id="abd86-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="abd86-122">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="abd86-122">**Framework Type.**</span></span> <span data-ttu-id="abd86-123">Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="abd86-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="abd86-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abd86-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="abd86-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="abd86-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="abd86-126">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="abd86-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="abd86-127">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="abd86-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="abd86-128">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="abd86-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="abd86-129">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="abd86-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="abd86-130">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="abd86-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="abd86-131">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="abd86-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="abd86-132">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="abd86-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
