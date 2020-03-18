---
title: Zeigerkonvertierungen – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 517166331d2bcf73132269ce2adcf68d5f60b4fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "76745363"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="43652-102">Zeigerkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="43652-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="43652-103">Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="43652-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="43652-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="43652-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="43652-105">Implizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="43652-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="43652-106">Von</span><span class="sxs-lookup"><span data-stu-id="43652-106">From</span></span>|<span data-ttu-id="43652-107">An</span><span class="sxs-lookup"><span data-stu-id="43652-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="43652-108">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-108">Any pointer type</span></span>|<span data-ttu-id="43652-109">void\*</span><span class="sxs-lookup"><span data-stu-id="43652-109">void\*</span></span>|  
|<span data-ttu-id="43652-110">null</span><span class="sxs-lookup"><span data-stu-id="43652-110">null</span></span>|<span data-ttu-id="43652-111">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="43652-112">Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="43652-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="43652-113">Die folgende Tabelle zeigt diese Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="43652-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="43652-114">Explizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="43652-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="43652-115">Von</span><span class="sxs-lookup"><span data-stu-id="43652-115">From</span></span>|<span data-ttu-id="43652-116">An</span><span class="sxs-lookup"><span data-stu-id="43652-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="43652-117">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-117">Any pointer type</span></span>|<span data-ttu-id="43652-118">Ein beliebiger anderer Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-118">Any other pointer type</span></span>|  
|<span data-ttu-id="43652-119">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="43652-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="43652-120">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-120">Any pointer type</span></span>|  
|<span data-ttu-id="43652-121">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="43652-121">Any pointer type</span></span>|<span data-ttu-id="43652-122">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="43652-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="43652-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43652-123">Example</span></span>  
 <span data-ttu-id="43652-124">Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="43652-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="43652-125">Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt.</span><span class="sxs-lookup"><span data-stu-id="43652-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="43652-126">Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.</span><span class="sxs-lookup"><span data-stu-id="43652-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="43652-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43652-127">See also</span></span>

- [<span data-ttu-id="43652-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="43652-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43652-129">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="43652-129">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="43652-130">Reference types (Verweistypen)</span><span class="sxs-lookup"><span data-stu-id="43652-130">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="43652-131">Value types (Werttypen)</span><span class="sxs-lookup"><span data-stu-id="43652-131">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="43652-132">unsafe</span><span class="sxs-lookup"><span data-stu-id="43652-132">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="43652-133">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="43652-133">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="43652-134">stackalloc</span><span class="sxs-lookup"><span data-stu-id="43652-134">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
