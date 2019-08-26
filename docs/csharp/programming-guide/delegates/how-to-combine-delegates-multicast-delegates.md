---
title: 'Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d9430021e6a9b438822f1a6dc201f64adf4fdb0f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590664"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="df88e-102">Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="df88e-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="df88e-103">Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten.</span><span class="sxs-lookup"><span data-stu-id="df88e-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="df88e-104">Eine nützliche Eigenschaft von [delegate](../../language-reference/keywords/delegate.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="df88e-104">A useful property of [delegate](../../language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="df88e-105">Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="df88e-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="df88e-106">Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf.</span><span class="sxs-lookup"><span data-stu-id="df88e-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="df88e-107">Es können nur Delegaten desselben Typs kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="df88e-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="df88e-108">Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="df88e-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df88e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df88e-109">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="df88e-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df88e-110">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="df88e-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="df88e-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="df88e-112">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="df88e-112">Events</span></span>](../events/index.md)
