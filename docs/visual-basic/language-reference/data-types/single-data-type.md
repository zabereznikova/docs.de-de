---
title: Single-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 98433c0f1d1008664bb994f3b43fe48a753a432c
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705179"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="31da1-102">Single-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31da1-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="31da1-103">Speichert signierte IEEE-32-Bit (4-Byte) mit einfacher Genauigkeit Gleitkommazahlen im Bereich von - 3,4028235E + 38 bis - 1.401298E-45 für negative Werte und 1.401298E-45 bis 3,4028235E + 38 für positive Werte.</span><span class="sxs-lookup"><span data-stu-id="31da1-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="31da1-104">Zahlen mit einfacher Genauigkeit speichern eine Approximation einer reellen Zahl.</span><span class="sxs-lookup"><span data-stu-id="31da1-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31da1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31da1-105">Remarks</span></span>  
 <span data-ttu-id="31da1-106">Verwenden der `Single` Datentyp in Gleitkommazahlen-Punktwerte enthalten, die nicht die gesamten Datenbreite des erfordern `Double`.</span><span class="sxs-lookup"><span data-stu-id="31da1-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="31da1-107">In einigen Fällen die common Language Runtime kann in der Lage, Packen Ihrer `Single` Variablen, die eng zusammen und Arbeitsspeicher belegt.</span><span class="sxs-lookup"><span data-stu-id="31da1-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="31da1-108">Der Standardwert von `Single` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="31da1-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="31da1-109">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="31da1-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="31da1-110">**Mit einfacher Genauigkeit.**</span><span class="sxs-lookup"><span data-stu-id="31da1-110">**Precision.**</span></span> <span data-ttu-id="31da1-111">Beim Arbeiten mit Gleitkommazahlen, Bedenken Sie, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="31da1-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="31da1-112">Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator.</span><span class="sxs-lookup"><span data-stu-id="31da1-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="31da1-113">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="31da1-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="31da1-114">**Erweiternde.**</span><span class="sxs-lookup"><span data-stu-id="31da1-114">**Widening.**</span></span> <span data-ttu-id="31da1-115">Die `Single` -Datentyp wird zu `Double`.</span><span class="sxs-lookup"><span data-stu-id="31da1-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="31da1-116">Dies bedeutet, Sie können konvertieren `Single` zu `Double` unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.</span><span class="sxs-lookup"><span data-stu-id="31da1-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="31da1-117">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="31da1-117">**Trailing Zeros.**</span></span> <span data-ttu-id="31da1-118">Der Gleitkomma-Datentypen keine interne Darstellung für nachfolgende 0 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="31da1-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="31da1-119">Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2.</span><span class="sxs-lookup"><span data-stu-id="31da1-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="31da1-120">Nachfolgende 0 Zeichen werden daher nicht angezeigt, wenn Sie anzeigen oder Drucken von Gleitkommazahlen-Punktwerte.</span><span class="sxs-lookup"><span data-stu-id="31da1-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="31da1-121">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="31da1-121">**Type Characters.**</span></span> <span data-ttu-id="31da1-122">Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="31da1-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="31da1-123">Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="31da1-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="31da1-124">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="31da1-124">**Framework Type.**</span></span> <span data-ttu-id="31da1-125">Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="31da1-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31da1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31da1-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="31da1-127">Datentypen</span><span class="sxs-lookup"><span data-stu-id="31da1-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="31da1-128">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="31da1-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="31da1-129">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="31da1-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="31da1-130">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="31da1-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="31da1-131">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="31da1-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="31da1-132">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="31da1-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="31da1-133">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="31da1-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
