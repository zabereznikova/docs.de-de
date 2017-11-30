---
title: "Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="8712c-102">Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere</span><span class="sxs-lookup"><span data-stu-id="8712c-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="8712c-103">Das folgende Beispiel zeigt die Vorgehensweise beim Synchronisieren gleichzeitiger Vorgänge mit einer <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="8712c-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8712c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8712c-104">Example</span></span>  
 <span data-ttu-id="8712c-105">Das folgende Programm dient gezählt, wie viele Iterationen (oder Phasen) sind für zwei Threads finden ihre Hälfte der Projektmappe auf der gleichen Phase erforderlich mithilfe einer Zufallsalgorithmus zu die Wörtern Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="8712c-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="8712c-106">Nach jeder Thread seine Wörter gemischt hat, vergleicht der Barriere Nachphasenaktion Vorgang die beiden Ergebnisse, um festzustellen, ob der vollständige Satz in der richtigen Reihenfolge gerendert wurde.</span><span class="sxs-lookup"><span data-stu-id="8712c-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="8712c-107">Ein <xref:System.Threading.Barrier> ist ein Objekt, das verhindert, einzelne Aufgaben in einem parallelen Vorgang dass fortgesetzt, bis alle Aufgaben die Barriere nicht erreicht.</span><span class="sxs-lookup"><span data-stu-id="8712c-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="8712c-108">Das ist nützlich, wenn Sie ein parallel ausgeführten Vorgang erfolgt in Phasen und jede Phase eine Synchronisierung zwischen Aufgaben erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8712c-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="8712c-109">In diesem Beispiel wird in zwei Phasen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="8712c-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="8712c-110">In der ersten Phase füllt jede Aufgabe aus seinem Abschnitt, der den Puffer mit Daten.</span><span class="sxs-lookup"><span data-stu-id="8712c-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="8712c-111">Beim Abschließen jeder Aufgabe Füllen von einem Abschnitt signalisiert die Aufgabe, die Grenze, die sie zum Fortfahren ist, und klicken Sie dann wartet.</span><span class="sxs-lookup"><span data-stu-id="8712c-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="8712c-112">Wenn alle Aufgaben die Barriere signalisiert haben, sind entsperrt, und die zweite Phase gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="8712c-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="8712c-113">Die Barriere ist erforderlich, da die zweite Phase erfordert, dass jede Aufgabe den Zugriff auf alle Daten verfügen, die zum angegebenen Zeitpunkt generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="8712c-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="8712c-114">Ohne die Grenze der ersten Aufgaben abgeschlossen versucht möglicherweise, zu aus dem Puffer zu lesen, die nicht noch von anderen Aufgaben ausgefüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="8712c-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="8712c-115">Sie können eine beliebige Anzahl von Phasen auf diese Weise synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="8712c-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8712c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8712c-116">See Also</span></span>  
 [<span data-ttu-id="8712c-117">Datenstrukturen für die parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="8712c-117">Data Structures for Parallel Programming</span></span>](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
