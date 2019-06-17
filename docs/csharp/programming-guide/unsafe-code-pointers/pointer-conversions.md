---
title: Zeigerkonvertierungen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 3cef2f2d2af2d285504daea14aa57c55b9e9a21b
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833464"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="482c5-102">Zeigerkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="482c5-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="482c5-103">Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="482c5-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="482c5-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="482c5-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="482c5-105">Implizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="482c5-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="482c5-106">Von</span><span class="sxs-lookup"><span data-stu-id="482c5-106">From</span></span>|<span data-ttu-id="482c5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="482c5-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="482c5-108">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-108">Any pointer type</span></span>|<span data-ttu-id="482c5-109">void\*</span><span class="sxs-lookup"><span data-stu-id="482c5-109">void\*</span></span>|  
|<span data-ttu-id="482c5-110">NULL</span><span class="sxs-lookup"><span data-stu-id="482c5-110">null</span></span>|<span data-ttu-id="482c5-111">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="482c5-112">Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="482c5-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="482c5-113">Die folgende Tabelle zeigt diese Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="482c5-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="482c5-114">Explizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="482c5-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="482c5-115">Von</span><span class="sxs-lookup"><span data-stu-id="482c5-115">From</span></span>|<span data-ttu-id="482c5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="482c5-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="482c5-117">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-117">Any pointer type</span></span>|<span data-ttu-id="482c5-118">Ein beliebiger anderer Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-118">Any other pointer type</span></span>|  
|<span data-ttu-id="482c5-119">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="482c5-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="482c5-120">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-120">Any pointer type</span></span>|  
|<span data-ttu-id="482c5-121">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="482c5-121">Any pointer type</span></span>|<span data-ttu-id="482c5-122">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="482c5-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="482c5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="482c5-123">Example</span></span>  
 <span data-ttu-id="482c5-124">Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="482c5-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="482c5-125">Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt.</span><span class="sxs-lookup"><span data-stu-id="482c5-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="482c5-126">Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.</span><span class="sxs-lookup"><span data-stu-id="482c5-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="482c5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="482c5-127">See also</span></span>

- [<span data-ttu-id="482c5-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="482c5-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="482c5-129">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="482c5-129">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="482c5-130">Typen</span><span class="sxs-lookup"><span data-stu-id="482c5-130">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="482c5-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="482c5-131">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="482c5-132">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="482c5-132">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="482c5-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="482c5-133">stackalloc</span></span>](../../../csharp/language-reference/operators/stackalloc.md)
