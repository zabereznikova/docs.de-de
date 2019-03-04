---
title: Generika und Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 145203d259b943bea1f43a9e49db2c7889bf914a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978911"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="57a72-102">Generika und Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="57a72-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="57a72-103">In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.</span><span class="sxs-lookup"><span data-stu-id="57a72-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="57a72-104">So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="57a72-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="57a72-105">Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="57a72-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="57a72-106">Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="57a72-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="57a72-107">Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57a72-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="57a72-108">Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="57a72-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="57a72-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57a72-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="57a72-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="57a72-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="57a72-111">Generics</span><span class="sxs-lookup"><span data-stu-id="57a72-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="57a72-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="57a72-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)
- [<span data-ttu-id="57a72-113">Generics</span><span class="sxs-lookup"><span data-stu-id="57a72-113">Generics</span></span>](~/docs/standard/generics/index.md)
