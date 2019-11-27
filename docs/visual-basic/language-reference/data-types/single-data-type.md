---
title: Single-Datentyp
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
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343917"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="40597-102">Single-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40597-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="40597-103">Enthält signierte IEEE 32-Bit (4-Byte)-Gleit Komma Zahlen mit einfacher Genauigkeit, die den Wert from-3.4028235 e + 38 bis- -1 401298E e-45 für negative Werte und von -1 401298E e-45 bis 3.4028235 e + 38 für positive Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="40597-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="40597-104">Zahlen mit einfacher Genauigkeit speichern eine Näherung einer reellen Zahl.</span><span class="sxs-lookup"><span data-stu-id="40597-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40597-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40597-105">Remarks</span></span>  

 <span data-ttu-id="40597-106">Verwenden Sie den `Single`-Datentyp, um Gleit Komma Werte zu enthalten, die nicht die vollständige Daten Breite von `Double`erfordern.</span><span class="sxs-lookup"><span data-stu-id="40597-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="40597-107">In einigen Fällen können die Common Language Runtime ihre `Single` Variablen eng zusammenpacken und den Speicherverbrauch sparen.</span><span class="sxs-lookup"><span data-stu-id="40597-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="40597-108">Der Standardwert von `Single` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="40597-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="40597-109">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="40597-109">Programming Tips</span></span>  
  
- <span data-ttu-id="40597-110">**Präziser.**</span><span class="sxs-lookup"><span data-stu-id="40597-110">**Precision.**</span></span> <span data-ttu-id="40597-111">Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="40597-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="40597-112">Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der `Mod`-Operator.</span><span class="sxs-lookup"><span data-stu-id="40597-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="40597-113">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="40597-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="40597-114">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="40597-114">**Widening.**</span></span> <span data-ttu-id="40597-115">Der `Single`-Datentyp wird zu `Double`erweitert.</span><span class="sxs-lookup"><span data-stu-id="40597-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="40597-116">Dies bedeutet, dass Sie `Single` in `Double` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="40597-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="40597-117">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="40597-117">**Trailing Zeros.**</span></span> <span data-ttu-id="40597-118">Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden 0 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="40597-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="40597-119">Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2.</span><span class="sxs-lookup"><span data-stu-id="40597-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="40597-120">Folglich werden nachfolgende 0 Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.</span><span class="sxs-lookup"><span data-stu-id="40597-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="40597-121">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="40597-121">**Type Characters.**</span></span> <span data-ttu-id="40597-122">Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="40597-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="40597-123">Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="40597-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="40597-124">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="40597-124">**Framework Type.**</span></span> <span data-ttu-id="40597-125">Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="40597-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40597-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40597-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="40597-127">Datentypen</span><span class="sxs-lookup"><span data-stu-id="40597-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="40597-128">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="40597-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="40597-129">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="40597-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="40597-130">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="40597-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="40597-131">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="40597-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="40597-132">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="40597-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="40597-133">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="40597-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
