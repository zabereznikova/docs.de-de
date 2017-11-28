---
title: "Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0304f04233151d35c8ee18fe09feac91fbd0879b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="2d0ad-102">Gewusst wie: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2d0ad-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="2d0ad-103">Sie können `accessor-declarations` dazu verwenden, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld hinzufügen zu müssen, indem Sie stattdessen ein Wörterbuch verwenden, um die Ereignisinstanzen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="2d0ad-104">Dies ist jedoch nur nützlich, wenn Sie viele Ereignisse haben, Sie aber davon ausgehen, dass viele der Ereignisse nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="2d0ad-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d0ad-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2d0ad-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2d0ad-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d0ad-106">See Also</span></span>  
 [<span data-ttu-id="2d0ad-107">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2d0ad-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2d0ad-108">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="2d0ad-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="2d0ad-109">Delegaten</span><span class="sxs-lookup"><span data-stu-id="2d0ad-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
