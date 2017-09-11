---
title: Generika und Arrays (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
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
ms.openlocfilehash: 46cea2733504e56aec5e65a4c9a8b655bc9431cf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="98dab-102">Generika und Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="98dab-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="98dab-103">In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.</span><span class="sxs-lookup"><span data-stu-id="98dab-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="98dab-104">So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="98dab-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="98dab-105">Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="98dab-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="98dab-106">Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="98dab-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="98dab-107">Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="98dab-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="98dab-108">Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="98dab-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 <span data-ttu-id="98dab-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="98dab-109">[!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dab-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98dab-110">See Also</span></span>  
 <span data-ttu-id="98dab-111"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="98dab-111"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="98dab-112">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="98dab-112">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="98dab-113">[Generika](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="98dab-113">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="98dab-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="98dab-114">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="98dab-115">Generika</span><span class="sxs-lookup"><span data-stu-id="98dab-115">Generics</span></span>](~/docs/standard/generics/index.md)

