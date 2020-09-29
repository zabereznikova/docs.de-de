---
title: Zeigerkonvertierungen – C#-Programmierhandbuch
description: Erfahren Sie mehr über Zeigerkonvertierungen. Hier finden Sie Tabellen mit impliziten und expliziten Zeigerkonvertierungen, Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
ms.openlocfilehash: 7a37c4e9f6333c00c7842df0fdaf353df516974d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205073"
---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="3c71a-104">Zeigerkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3c71a-104">Pointer Conversions (C# Programming Guide)</span></span>

<span data-ttu-id="3c71a-105">Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="3c71a-105">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="3c71a-106">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="3c71a-106">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="3c71a-107">Implizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="3c71a-107">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="3c71a-108">Von</span><span class="sxs-lookup"><span data-stu-id="3c71a-108">From</span></span>|<span data-ttu-id="3c71a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c71a-109">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="3c71a-110">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-110">Any pointer type</span></span>|<span data-ttu-id="3c71a-111">void\*</span><span class="sxs-lookup"><span data-stu-id="3c71a-111">void\*</span></span>|  
|<span data-ttu-id="3c71a-112">NULL</span><span class="sxs-lookup"><span data-stu-id="3c71a-112">null</span></span>|<span data-ttu-id="3c71a-113">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-113">Any pointer type</span></span>|  
  
 <span data-ttu-id="3c71a-114">Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3c71a-114">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="3c71a-115">Die folgende Tabelle zeigt diese Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="3c71a-115">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="3c71a-116">Explizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="3c71a-116">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="3c71a-117">Von</span><span class="sxs-lookup"><span data-stu-id="3c71a-117">From</span></span>|<span data-ttu-id="3c71a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c71a-118">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="3c71a-119">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-119">Any pointer type</span></span>|<span data-ttu-id="3c71a-120">Ein beliebiger anderer Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-120">Any other pointer type</span></span>|  
|<span data-ttu-id="3c71a-121">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="3c71a-121">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="3c71a-122">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-122">Any pointer type</span></span>|  
|<span data-ttu-id="3c71a-123">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="3c71a-123">Any pointer type</span></span>|<span data-ttu-id="3c71a-124">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="3c71a-124">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3c71a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c71a-125">Example</span></span>  

 <span data-ttu-id="3c71a-126">Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3c71a-126">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="3c71a-127">Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt.</span><span class="sxs-lookup"><span data-stu-id="3c71a-127">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="3c71a-128">Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c71a-128">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="3c71a-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c71a-129">See also</span></span>

- [<span data-ttu-id="3c71a-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3c71a-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="3c71a-131">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="3c71a-131">Pointer types</span></span>](pointer-types.md)
- [<span data-ttu-id="3c71a-132">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3c71a-132">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="3c71a-133">Werttypen</span><span class="sxs-lookup"><span data-stu-id="3c71a-133">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
- [<span data-ttu-id="3c71a-134">unsafe</span><span class="sxs-lookup"><span data-stu-id="3c71a-134">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
- [<span data-ttu-id="3c71a-135">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3c71a-135">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="3c71a-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3c71a-136">stackalloc</span></span>](../../language-reference/operators/stackalloc.md)
