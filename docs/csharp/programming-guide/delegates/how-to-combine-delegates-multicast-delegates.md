---
title: 'Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Delegaten kombinieren, um Multicastdelegaten zu erstellen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d23ea758c9da2c3399f5d98e81360cc250b428a1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302736"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="d4e66-104">Kombinieren von Delegaten (Multicastdelegaten) (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d4e66-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>
<span data-ttu-id="d4e66-105">Das folgende Beispiel veranschaulicht das Erstellen von Multicastdelegaten.</span><span class="sxs-lookup"><span data-stu-id="d4e66-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="d4e66-106">Eine nützliche Eigenschaft von [delegate](../../language-reference/builtin-types/reference-types.md)-Objekten besteht darin, dass einer Delegatinstanz mithilfe des Operators `+` mehrere Objekte zugewiesen werden können.</span><span class="sxs-lookup"><span data-stu-id="d4e66-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="d4e66-107">Der Multicastdelegat enthält eine Liste der zugewiesenen Delegaten.</span><span class="sxs-lookup"><span data-stu-id="d4e66-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="d4e66-108">Wenn der Multicastdelegat aufgerufen wird, ruft er die Delegaten in der Liste nacheinander auf.</span><span class="sxs-lookup"><span data-stu-id="d4e66-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="d4e66-109">Es können nur Delegaten desselben Typs kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="d4e66-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="d4e66-110">Mithilfe des Operators `-` kann ein Komponentendelegat aus einem Multicastdelegaten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d4e66-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4e66-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4e66-111">Example</span></span>  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d4e66-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4e66-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="d4e66-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d4e66-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d4e66-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="d4e66-114">Events</span></span>](../events/index.md)
