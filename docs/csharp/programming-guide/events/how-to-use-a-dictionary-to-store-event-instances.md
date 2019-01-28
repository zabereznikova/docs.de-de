---
title: 'Vorgehensweise: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 8f0284c5637890f35642346880d035619bc0e1e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560060"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a><span data-ttu-id="489a8-102">Vorgehensweise: Verwenden eines Wörterbuchs zum Speichern von Ereignisinstanzen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="489a8-102">How to: Use a Dictionary to Store Event Instances (C# Programming Guide)</span></span>
<span data-ttu-id="489a8-103">Sie können `accessor-declarations` dazu verwenden, viele Ereignisse verfügbar zu machen, ohne jedem Ereignis ein Feld hinzufügen zu müssen, indem Sie stattdessen ein Wörterbuch verwenden, um die Ereignisinstanzen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="489a8-103">One use for `accessor-declarations` is to expose many events without allocating a field for each event, but instead using a Dictionary to store the event instances.</span></span> <span data-ttu-id="489a8-104">Dies ist jedoch nur nützlich, wenn Sie viele Ereignisse haben, Sie aber davon ausgehen, dass viele der Ereignisse nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="489a8-104">This is only useful if you have many events, but you expect most of the events will not be implemented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="489a8-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="489a8-105">Example</span></span>  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="489a8-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="489a8-106">See also</span></span>

- [<span data-ttu-id="489a8-107">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="489a8-107">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="489a8-108">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="489a8-108">Events</span></span>](../../../csharp/programming-guide/events/index.md)
- [<span data-ttu-id="489a8-109">Delegaten</span><span class="sxs-lookup"><span data-stu-id="489a8-109">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
