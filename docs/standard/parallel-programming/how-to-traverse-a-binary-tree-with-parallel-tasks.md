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
ms.openlocfilehash: b79337e6ee8057506ff87c696cecd6b038eeebfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141640"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="1b0cd-102">Gewusst wie: Durchlaufen einer Binärstruktur mit parallelen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="1b0cd-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="1b0cd-103">Das folgende Beispiel zeigt zwei Möglichkeiten, wie parallele Aufgaben verwendet werden können, um eine Datenstruktur zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="1b0cd-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="1b0cd-104">Die Erstellung der Struktur selbst dient als Übung.</span><span class="sxs-lookup"><span data-stu-id="1b0cd-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b0cd-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b0cd-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="1b0cd-106">Die beiden gezeigten Methoden sind funktional äquivalent.</span><span class="sxs-lookup"><span data-stu-id="1b0cd-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="1b0cd-107">Wenn Sie die <xref:System.Threading.Tasks.TaskFactory.StartNew%2A>-Methode zum Erstellen und Ausführen der Aufgaben verwenden, geben die Aufgaben ein Handle zurück, das zum Warten auf die Aufgaben und Behandeln von Ausnahmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b0cd-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0cd-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b0cd-108">See also</span></span>

- [<span data-ttu-id="1b0cd-109">Task Parallel Library (TPL)</span><span class="sxs-lookup"><span data-stu-id="1b0cd-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
