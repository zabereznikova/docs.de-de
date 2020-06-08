---
title: 'Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: 2e13dfb277807eb0a9f256f74c2845f5a4d2a047
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279296"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a><span data-ttu-id="09759-102">Gewusst wie: Synchronisieren gleichzeitiger Vorgänge mit einer Barriere</span><span class="sxs-lookup"><span data-stu-id="09759-102">How to: Synchronize Concurrent Operations with a Barrier</span></span>
<span data-ttu-id="09759-103">Das folgende Beispiel zeigt das Synchronisieren gleichzeitiger Aufgaben mit einer <xref:System.Threading.Barrier>.</span><span class="sxs-lookup"><span data-stu-id="09759-103">The following example shows how to synchronize concurrent tasks with a <xref:System.Threading.Barrier>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09759-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09759-104">Example</span></span>  
 <span data-ttu-id="09759-105">Zweck des folgenden Programms ist, zu zählen, wie viele Iterationen (oder Phasen) erforderlich sind, damit zwei Threads ihre jeweilige Hälfte der Lösung mithilfe eines Zufallsalgorithmus zum erneuten Mischen der Wörter in der gleichen Phase finden.</span><span class="sxs-lookup"><span data-stu-id="09759-105">The purpose of the following program is to count how many iterations (or phases) are required for two threads to each find their half of the solution on the same phase by using a randomizing algorithm to reshuffle the words.</span></span> <span data-ttu-id="09759-106">Nachdem jeder Thread seine Wörter gemischt hat, vergleicht der Barrierennachphasen-Vorgang die beiden Ergebnisse, um festzustellen, ob der vollständige Satz in der richtigen Reihenfolge gerendert wurde.</span><span class="sxs-lookup"><span data-stu-id="09759-106">After each thread has shuffled its words, the barrier post-phase operation compares the two results to see if the complete sentence has been rendered in correct word order.</span></span>  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <span data-ttu-id="09759-107">Eine <xref:System.Threading.Barrier> ist ein Objekt, das verhindert, dass einzelne Aufgaben in einem parallelen Vorgang fortgesetzt werden, bevor alle Aufgaben die Barriere erreichen.</span><span class="sxs-lookup"><span data-stu-id="09759-107">A <xref:System.Threading.Barrier> is an object that prevents individual tasks in a parallel operation from continuing until all tasks reach the barrier.</span></span> <span data-ttu-id="09759-108">Das ist nützlich, wenn ein parallel ausgeführter Vorgang in Phasen erfolgt, und jede Phase eine Synchronisierung zwischen Aufgaben erfordert.</span><span class="sxs-lookup"><span data-stu-id="09759-108">It is useful when a parallel operation occurs in phases, and each phase requires synchronization between tasks.</span></span> <span data-ttu-id="09759-109">In diesem Beispiel besteht der Vorgang aus zwei Phasen.</span><span class="sxs-lookup"><span data-stu-id="09759-109">In this example, there are two phases to the operation.</span></span> <span data-ttu-id="09759-110">In der ersten Phase füllt jede Aufgabe ihren Abschnitt des Puffers mit Daten.</span><span class="sxs-lookup"><span data-stu-id="09759-110">In the first phase, each task fills its section of the buffer with data.</span></span> <span data-ttu-id="09759-111">Wenn eine Aufgabe ihren Abschnitt gefüllt hat, signalisiert die Aufgabe der Barriere, das sie zum Fortfahren bereit ist, und wartet.</span><span class="sxs-lookup"><span data-stu-id="09759-111">When each task finishes filling its section, the task signals the barrier that it is ready to continue, and then waits.</span></span> <span data-ttu-id="09759-112">Wenn alle Aufgaben ihr Signal an die Barriere gesendet haben, werden sie entsperrt, und die zweite Phase startet.</span><span class="sxs-lookup"><span data-stu-id="09759-112">When all tasks have signaled the barrier, they are unblocked and the second phase starts.</span></span> <span data-ttu-id="09759-113">Die Barriere ist erforderlich, da die zweite Phase voraussetzt, dass jede Aufgabe Zugriff auf alle Daten hat, die bis zu diesem Punkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="09759-113">The barrier is necessary because the second phase requires that each task have access to all the data that has been generated to this point.</span></span> <span data-ttu-id="09759-114">Ohne die Barriere könnten die Aufgaben, die zuerst ihre Abschnitte gefüllt haben, versuchen, aus Puffern zu lesen, die noch nicht von anderen Aufgaben gefüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="09759-114">Without the barrier, the first tasks to complete might try to read from buffers that have not been filled in yet by other tasks.</span></span> <span data-ttu-id="09759-115">Sie können eine beliebige Anzahl von Phasen auf diese Weise synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="09759-115">You can synchronize any number of phases in this manner.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09759-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09759-116">See also</span></span>

- [<span data-ttu-id="09759-117">Datenstrukturen für die parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="09759-117">Data Structures for Parallel Programming</span></span>](../parallel-programming/data-structures-for-parallel-programming.md)
