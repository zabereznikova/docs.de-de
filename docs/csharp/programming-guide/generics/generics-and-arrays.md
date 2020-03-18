---
title: Generics und Arrays – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: a8fad38fac07b9e8d51529d3ab7070328a333dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75703012"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="01af6-102">Generics und Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="01af6-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="01af6-103">In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.</span><span class="sxs-lookup"><span data-stu-id="01af6-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="01af6-104">So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="01af6-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="01af6-105">Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="01af6-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="01af6-106">Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="01af6-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="01af6-107">Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="01af6-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="01af6-108">Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="01af6-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="01af6-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01af6-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="01af6-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="01af6-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="01af6-111">Generics</span><span class="sxs-lookup"><span data-stu-id="01af6-111">Generics</span></span>](./index.md)
- [<span data-ttu-id="01af6-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="01af6-112">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="01af6-113">Generics</span><span class="sxs-lookup"><span data-stu-id="01af6-113">Generics</span></span>](../../../standard/generics/index.md)
