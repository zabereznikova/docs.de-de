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
ms.openlocfilehash: ecb0f5f6416a2dd4ddd6888cb80ed3ac11ee58df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415530"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="605b3-102">Single-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="605b3-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="605b3-103">Enthält signierte IEEE 32-Bit (4-Byte)-Gleit Komma Zahlen mit einfacher Genauigkeit, die den Wert from-3.4028235 e + 38 bis- -1 401298E e-45 für negative Werte und von -1 401298E e-45 bis 3.4028235 e + 38 für positive Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="605b3-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="605b3-104">Zahlen mit einfacher Genauigkeit speichern eine Näherung einer reellen Zahl.</span><span class="sxs-lookup"><span data-stu-id="605b3-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="605b3-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="605b3-105">Remarks</span></span>  

 <span data-ttu-id="605b3-106">Verwenden Sie den- `Single` Datentyp, um Gleit Komma Werte zu enthalten, die nicht die vollständige Daten Breite von erfordern `Double` .</span><span class="sxs-lookup"><span data-stu-id="605b3-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="605b3-107">In einigen Fällen können die Common Language Runtime Ihre `Single` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.</span><span class="sxs-lookup"><span data-stu-id="605b3-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="605b3-108">Der Standardwert von `Single` lautet 0.</span><span class="sxs-lookup"><span data-stu-id="605b3-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="605b3-109">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="605b3-109">Programming Tips</span></span>  
  
- <span data-ttu-id="605b3-110">**Präziser.**</span><span class="sxs-lookup"><span data-stu-id="605b3-110">**Precision.**</span></span> <span data-ttu-id="605b3-111">Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen.</span><span class="sxs-lookup"><span data-stu-id="605b3-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="605b3-112">Dies kann zu unerwarteten Ergebnissen bei bestimmten Vorgängen führen, wie z. b. Werte Vergleich und `Mod` Operator.</span><span class="sxs-lookup"><span data-stu-id="605b3-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="605b3-113">Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="605b3-113">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="605b3-114">**Tet.**</span><span class="sxs-lookup"><span data-stu-id="605b3-114">**Widening.**</span></span> <span data-ttu-id="605b3-115">Der- `Single` Datentyp wird zu erweitert `Double` .</span><span class="sxs-lookup"><span data-stu-id="605b3-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="605b3-116">Dies bedeutet, dass Sie `Single` in konvertieren können, `Double` ohne dass ein Fehler auftritt <xref:System.OverflowException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="605b3-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="605b3-117">**Nachfolgende Nullen.**</span><span class="sxs-lookup"><span data-stu-id="605b3-117">**Trailing Zeros.**</span></span> <span data-ttu-id="605b3-118">Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden 0 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="605b3-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="605b3-119">Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2.</span><span class="sxs-lookup"><span data-stu-id="605b3-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="605b3-120">Folglich werden nachfolgende 0 Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.</span><span class="sxs-lookup"><span data-stu-id="605b3-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="605b3-121">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="605b3-121">**Type Characters.**</span></span> <span data-ttu-id="605b3-122">Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="605b3-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="605b3-123">Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="605b3-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="605b3-124">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="605b3-124">**Framework Type.**</span></span> <span data-ttu-id="605b3-125">Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="605b3-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605b3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="605b3-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="605b3-127">Datentypen</span><span class="sxs-lookup"><span data-stu-id="605b3-127">Data Types</span></span>](index.md)
- [<span data-ttu-id="605b3-128">Decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="605b3-128">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="605b3-129">Double-Datentyp</span><span class="sxs-lookup"><span data-stu-id="605b3-129">Double Data Type</span></span>](double-data-type.md)
- [<span data-ttu-id="605b3-130">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="605b3-130">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="605b3-131">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="605b3-131">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="605b3-132">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="605b3-132">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="605b3-133">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="605b3-133">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
