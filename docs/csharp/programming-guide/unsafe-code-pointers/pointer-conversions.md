---
title: Zeigerkonvertierungen (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], conversions
ms.assetid: f0e87502-477a-4ede-a31f-7a3e262e46fb
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e415d892d979e2bdcd648256150e2a96b1772ce4
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-conversions-c-programming-guide"></a><span data-ttu-id="4fdd5-102">Zeigerkonvertierungen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4fdd5-102">Pointer Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="4fdd5-103">Die folgende Tabelle zeigt vordefinierte implizite Zeigerkonvertierungen.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-103">The following table shows the predefined implicit pointer conversions.</span></span> <span data-ttu-id="4fdd5-104">Implizite Konvertierungen können in vielen Situationen auftreten, einschließlich methodenaufrufender und Zuweisungsansweisungen.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
## <a name="implicit-pointer-conversions"></a><span data-ttu-id="4fdd5-105">Implizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="4fdd5-105">Implicit pointer conversions</span></span>  
  
|<span data-ttu-id="4fdd5-106">Von</span><span class="sxs-lookup"><span data-stu-id="4fdd5-106">From</span></span>|<span data-ttu-id="4fdd5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fdd5-107">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="4fdd5-108">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-108">Any pointer type</span></span>|<span data-ttu-id="4fdd5-109">void*</span><span class="sxs-lookup"><span data-stu-id="4fdd5-109">void*</span></span>|  
|<span data-ttu-id="4fdd5-110">NULL</span><span class="sxs-lookup"><span data-stu-id="4fdd5-110">null</span></span>|<span data-ttu-id="4fdd5-111">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-111">Any pointer type</span></span>|  
  
 <span data-ttu-id="4fdd5-112">Die explizite Zeigerkonvertierung wird verwendet, um Konvertierungen, für die keine implizite Konvertierung vorliegt, mithilfe eines CAST-Ausdrucks durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-112">Explicit pointer conversion is used to perform conversions, for which there is no implicit conversion, by using a cast expression.</span></span> <span data-ttu-id="4fdd5-113">Die folgende Tabelle zeigt diese Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-113">The following table shows these conversions.</span></span>  
  
## <a name="explicit-pointer-conversions"></a><span data-ttu-id="4fdd5-114">Explizite Zeigerkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="4fdd5-114">Explicit pointer conversions</span></span>  
  
|<span data-ttu-id="4fdd5-115">Von</span><span class="sxs-lookup"><span data-stu-id="4fdd5-115">From</span></span>|<span data-ttu-id="4fdd5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fdd5-116">To</span></span>|  
|----------|--------|  
|<span data-ttu-id="4fdd5-117">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-117">Any pointer type</span></span>|<span data-ttu-id="4fdd5-118">Ein beliebiger anderer Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-118">Any other pointer type</span></span>|  
|<span data-ttu-id="4fdd5-119">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="4fdd5-119">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|<span data-ttu-id="4fdd5-120">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-120">Any pointer type</span></span>|  
|<span data-ttu-id="4fdd5-121">Beliebiger Zeigertyp</span><span class="sxs-lookup"><span data-stu-id="4fdd5-121">Any pointer type</span></span>|<span data-ttu-id="4fdd5-122">sbyte, byte, short, ushort, int, uint, long oder ulong</span><span class="sxs-lookup"><span data-stu-id="4fdd5-122">sbyte, byte, short, ushort, int, uint, long, or ulong</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4fdd5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4fdd5-123">Example</span></span>  
 <span data-ttu-id="4fdd5-124">Im folgenden Beispiel wird ein Zeiger auf `int` in einen Zeiger auf `byte` konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-124">In the following example, a pointer to `int` is converted to a pointer to `byte`.</span></span> <span data-ttu-id="4fdd5-125">Beachten Sie, dass der Zeiger auf das Byte der Variable mit der niedrigsten Adresse zeigt.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-125">Notice that the pointer points to the lowest addressed byte of the variable.</span></span> <span data-ttu-id="4fdd5-126">Wenn Sie das Ergebnis nach und nach bis auf die Größe von `int` (4 Bytes) erhöhen, können Sie die verbleibenden Bytes der Variable anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4fdd5-126">When you successively increment the result, up to the size of `int` (4 bytes), you can display the remaining bytes of the variable.</span></span>  
  
 <span data-ttu-id="4fdd5-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4fdd5-127">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="4fdd5-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4fdd5-128">[!code-cs[csProgGuidePointers#4](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-conversions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fdd5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fdd5-129">See Also</span></span>  
 <span data-ttu-id="4fdd5-130">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4fdd5-131">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-131">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="4fdd5-132">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-132">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="4fdd5-133">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-133">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="4fdd5-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-134">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="4fdd5-135">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4fdd5-135">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="4fdd5-136">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4fdd5-136">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

