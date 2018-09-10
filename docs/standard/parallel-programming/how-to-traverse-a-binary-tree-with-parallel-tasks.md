---
title: 'Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd937d6ce2edf0c47fce78d48a90ec1aa409eef
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44196646"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="2b27a-102">Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2b27a-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="2b27a-103">Das folgende Beispiel zeigt zwei Möglichkeiten, wie parallele Aufgaben verwendet werden können, um eine Datenstruktur zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="2b27a-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="2b27a-104">Die Erstellung der Struktur selbst dient als Übung.</span><span class="sxs-lookup"><span data-stu-id="2b27a-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b27a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b27a-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="2b27a-106">Die beiden gezeigten Methoden sind funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="2b27a-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="2b27a-107">Wenn Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode zum Erstellen und Ausführen der Aufgaben verwenden, geben die Aufgaben ein Handle zurück, das zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b27a-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b27a-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b27a-108">See also</span></span>

- [<span data-ttu-id="2b27a-109">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="2b27a-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
