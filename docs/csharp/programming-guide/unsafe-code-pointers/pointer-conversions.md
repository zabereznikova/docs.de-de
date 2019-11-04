---
title: Zeigerkonvertierungen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: b0a517eacc505376c9502e9d095c7aac0cd54555
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417532"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="ea132-102">Zeigerkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ea132-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="ea132-103">Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="ea132-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="ea132-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="ea132-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="ea132-105">Implizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ea132-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="ea132-106">Von</span><span class="sxs-lookup"><span data-stu-id="ea132-106">From</span></span>|<span data-ttu-id="ea132-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea132-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="ea132-108">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-108">Any pointer type</span></span>|<span data-ttu-id="ea132-109">void\*</span><span class="sxs-lookup"><span data-stu-id="ea132-109">void\*</span></span>|  
|<span data-ttu-id="ea132-110">NULL</span><span class="sxs-lookup"><span data-stu-id="ea132-110">null</span></span>|<span data-ttu-id="ea132-111">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="ea132-112">Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ea132-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="ea132-113">Die folgende Tabelle zeigt diese Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="ea132-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="ea132-114">Explizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="ea132-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="ea132-115">Von</span><span class="sxs-lookup"><span data-stu-id="ea132-115">From</span></span>|<span data-ttu-id="ea132-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea132-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="ea132-117">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-117">Any pointer type</span></span>|<span data-ttu-id="ea132-118">Ein beliebiger anderer Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-118">Any other pointer type</span></span>|  
|<span data-ttu-id="ea132-119">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="ea132-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="ea132-120">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-120">Any pointer type</span></span>|  
|<span data-ttu-id="ea132-121">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="ea132-121">Any pointer type</span></span>|<span data-ttu-id="ea132-122">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="ea132-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ea132-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea132-123">Example</span></span>  
 <span data-ttu-id="ea132-124">Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ea132-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="ea132-125">Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt.</span><span class="sxs-lookup"><span data-stu-id="ea132-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="ea132-126">Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea132-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="ea132-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea132-127">See also</span></span>

- [<span data-ttu-id="ea132-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ea132-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ea132-129">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="ea132-129">Pointer types</span></span>](./pointer-types.md)
- [<span data-ttu-id="ea132-130">Typen</span><span class="sxs-lookup"><span data-stu-id="ea132-130">Types</span></span>](/dotnet/csharp/language-reference/keywords)
- [<span data-ttu-id="ea132-131">unsafe</span><span class="sxs-lookup"><span data-stu-id="ea132-131">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="ea132-132">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ea132-132">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="ea132-133">stackalloc</span><span class="sxs-lookup"><span data-stu-id="ea132-133">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
