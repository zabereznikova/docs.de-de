---
title: Generics und Arrays – C#-Programmierhandbuch
description: Erfahren Sie mehr über Generics und Arrays in der C#-Programmierung. Hier finden Sie Codebeispiele und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 808e9ddafea9806a74ccd105c8850e7b77b563be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151453"
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="e8976-104">Generics und Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e8976-104">Generics and Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="e8976-105">In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.</span><span class="sxs-lookup"><span data-stu-id="e8976-105">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="e8976-106">So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e8976-106">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="e8976-107">Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="e8976-107">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="e8976-108">Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e8976-108">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="e8976-109">Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e8976-109">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="e8976-110">Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="e8976-110">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#35)]  
  
## <a name="see-also"></a><span data-ttu-id="e8976-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8976-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="e8976-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e8976-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e8976-113">Generics</span><span class="sxs-lookup"><span data-stu-id="e8976-113">Generics</span></span>](./index.md)
- [<span data-ttu-id="e8976-114">Arrays</span><span class="sxs-lookup"><span data-stu-id="e8976-114">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="e8976-115">Generics</span><span class="sxs-lookup"><span data-stu-id="e8976-115">Generics</span></span>](../../../standard/generics/index.md)
