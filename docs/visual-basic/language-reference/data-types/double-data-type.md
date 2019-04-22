---
title: Double-Datentyp (Visual Basic)
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
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824662"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="5b3d1-102">Double-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b3d1-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="5b3d1-103">Speichert signierte IEEE-64-Bit (8 Byte) mit doppelter Genauigkeit Gleitkommazahlen, die in den Wertebereich von - 1.79769313486231570E + 308 bis - liegen 4.94065645841246544E-324 für negative Werte und 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="5b3d1-104">Zahlen mit doppelter Genauigkeit speichern eine Approximation einer reellen Zahl.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b3d1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b3d1-105">Remarks</span></span>  
 <span data-ttu-id="5b3d1-106">Die `Double` -Datentyp stellt die größte und kleinsten möglichen Werte für eine Reihe.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="5b3d1-107">Der Standardwert von `Double` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5b3d1-108">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="5b3d1-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="5b3d1-109">**Mit einfacher Genauigkeit.**</span><span class="sxs-lookup"><span data-stu-id="5b3d1-109">**Precision.**</span></span> <span data-ttu-id="5b3d1-110">Beim Arbeiten mit Gleitkommazahlen, denken Sie daran, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="5b3d1-111">Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="5b3d1-112">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="5b3d1-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="5b3d1-113">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="5b3d1-113">**Trailing Zeros.**</span></span> <span data-ttu-id="5b3d1-114">Der Gleitkomma-Datentypen keine interne Darstellung für nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="5b3d1-115">Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="5b3d1-116">Folglich nachfolgende Nullen erscheinen nicht beim Anzeigen oder Drucken Gleitkommawerte.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="5b3d1-117">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="5b3d1-117">**Type Characters.**</span></span> <span data-ttu-id="5b3d1-118">Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="5b3d1-119">Wenn ein ganzzahliger Wert folgt, wird z. B. `R`, der Wert wird geändert, um eine `Double`.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="5b3d1-120">Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="5b3d1-121">Im folgenden Beispiel ist die Variable `num` typisiert ist, als eine `Double`:</span><span class="sxs-lookup"><span data-stu-id="5b3d1-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="5b3d1-122">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="5b3d1-122">**Framework Type.**</span></span> <span data-ttu-id="5b3d1-123">Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="5b3d1-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b3d1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b3d1-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="5b3d1-125">Datentypen</span><span class="sxs-lookup"><span data-stu-id="5b3d1-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5b3d1-126">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5b3d1-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="5b3d1-127">Single-Datentyp</span><span class="sxs-lookup"><span data-stu-id="5b3d1-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="5b3d1-128">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="5b3d1-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="5b3d1-129">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="5b3d1-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="5b3d1-130">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="5b3d1-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="5b3d1-131">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="5b3d1-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="5b3d1-132">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="5b3d1-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
