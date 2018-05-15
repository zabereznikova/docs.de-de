---
title: Generika und Arrays (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], arrays
- arrays [C#], generics
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
ms.openlocfilehash: 2e7ab9ff0dc4a73500c1a452df16af17c720d528
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generics-and-arrays-c-programming-guide"></a><span data-ttu-id="7fb35-102">Generika und Arrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7fb35-102">Generics and Arrays (C# Programming Guide)</span></span>
<span data-ttu-id="7fb35-103">In C# 2.0 oder höher implementieren eindimensionale Arrays, die als untere Grenze 0 (null) aufweisen, <xref:System.Collections.Generic.IList%601> automatisch.</span><span class="sxs-lookup"><span data-stu-id="7fb35-103">In C# 2.0 and later, single-dimensional arrays that have a lower bound of zero automatically implement <xref:System.Collections.Generic.IList%601>.</span></span> <span data-ttu-id="7fb35-104">So können Sie generische Methoden erstellen, die zum Durchlaufen von Arrays und anderen Auflistungstypen den gleichen Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="7fb35-104">This enables you to create generic methods that can use the same code to iterate through arrays and other collection types.</span></span> <span data-ttu-id="7fb35-105">Diese Technik ist vor allem zum Lesen der Daten in Auflistungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="7fb35-105">This technique is primarily useful for reading data in collections.</span></span> <span data-ttu-id="7fb35-106">Die Schnittstelle <xref:System.Collections.Generic.IList%601> kann nicht verwendet werden, um Elemente einem Array hinzuzufügen oder daraus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7fb35-106">The <xref:System.Collections.Generic.IList%601> interface cannot be used to add or remove elements from an array.</span></span> <span data-ttu-id="7fb35-107">Bei dem Versuch, eine <xref:System.Collections.Generic.IList%601>-Methode wie <xref:System.Collections.Generic.IList%601.RemoveAt%2A> für ein Array in diesem Kontext aufzurufen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7fb35-107">An exception will be thrown if you try to call an <xref:System.Collections.Generic.IList%601> method such as <xref:System.Collections.Generic.IList%601.RemoveAt%2A> on an array in this context.</span></span>  
  
 <span data-ttu-id="7fb35-108">Das folgende Codebeispiel veranschaulicht, wie eine einzelne generische Methode, die einen <xref:System.Collections.Generic.IList%601>-Eingabeparameter verwendet, sowohl eine Liste als auch ein Array (in diesem Fall ein Array mit ganzen Zahlen) durchlaufen kann.</span><span class="sxs-lookup"><span data-stu-id="7fb35-108">The following code example demonstrates how a single generic method that takes an <xref:System.Collections.Generic.IList%601> input parameter can iterate through both a list and an array, in this case an array of integers.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-arrays_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7fb35-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fb35-109">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="7fb35-110">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7fb35-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7fb35-111">Generika</span><span class="sxs-lookup"><span data-stu-id="7fb35-111">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
 [<span data-ttu-id="7fb35-112">Arrays</span><span class="sxs-lookup"><span data-stu-id="7fb35-112">Arrays</span></span>](../../../csharp/programming-guide/arrays/index.md)  
 [<span data-ttu-id="7fb35-113">Generika</span><span class="sxs-lookup"><span data-stu-id="7fb35-113">Generics</span></span>](~/docs/standard/generics/index.md)
