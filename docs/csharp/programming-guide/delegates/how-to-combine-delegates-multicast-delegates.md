---
title: 'Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
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
ms.openlocfilehash: 617af10d3fb5f9371d5893b87a91a48639d44a53
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a><span data-ttu-id="7d859-102">Gewusst wie: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="7d859-102">How to: Combine Delegates (Multicast Delegates)(C# Programming Guide)</span></span>
<span data-ttu-id="7d859-103">Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten.</span><span class="sxs-lookup"><span data-stu-id="7d859-103">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="7d859-104">Eine nützliche Eigenschaft von [delegate](../../../csharp/language-reference/keywords/delegate.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="7d859-104">A useful property of [delegate](../../../csharp/language-reference/keywords/delegate.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="7d859-105">Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="7d859-105">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="7d859-106">Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf.</span><span class="sxs-lookup"><span data-stu-id="7d859-106">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="7d859-107">Es können nur Delegaten desselben Typs kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="7d859-107">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="7d859-108">Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7d859-108">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d859-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d859-109">Example</span></span>  
 <span data-ttu-id="7d859-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7d859-110">[!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d859-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d859-111">See Also</span></span>  
 <span data-ttu-id="7d859-112"><xref:System.MulticastDelegate></span><span class="sxs-lookup"><span data-stu-id="7d859-112"><xref:System.MulticastDelegate></span></span>   
 <span data-ttu-id="7d859-113">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d859-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="7d859-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="7d859-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)

