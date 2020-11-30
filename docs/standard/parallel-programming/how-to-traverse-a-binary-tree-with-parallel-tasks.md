---
title: 'Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: 6c8708f2879671573ab870bf7d9df520a6118c7a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722379"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="412bf-102">Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="412bf-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>

<span data-ttu-id="412bf-103">Das folgende Beispiel zeigt zwei Möglichkeiten, wie parallele Aufgaben verwendet werden können, um eine Datenstruktur zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="412bf-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="412bf-104">Die Erstellung der Struktur selbst dient als Übung.</span><span class="sxs-lookup"><span data-stu-id="412bf-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="412bf-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="412bf-105">Example</span></span>  

 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="412bf-106">Die beiden gezeigten Methoden sind funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="412bf-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="412bf-107">Wenn Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode zum Erstellen und Ausführen der Aufgaben verwenden, geben die Aufgaben ein Handle zurück, das zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="412bf-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="412bf-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="412bf-108">See also</span></span>

- [<span data-ttu-id="412bf-109">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="412bf-109">Task Parallel Library (TPL)</span></span>](task-parallel-library-tpl.md)
