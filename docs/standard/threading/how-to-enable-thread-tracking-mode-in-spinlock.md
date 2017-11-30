---
title: 'Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock'
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="c7f89-102">Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock</span><span class="sxs-lookup"><span data-stu-id="c7f89-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>
<span data-ttu-id="c7f89-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType>ist eine Low-Level gegenseitigen Ausschluss-Sperre, die Sie für Szenarien verwenden können, die sehr kurze Wartezeiten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c7f89-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="c7f89-104"><xref:System.Threading.SpinLock>ist nicht wiedereintrittsfähig.</span><span class="sxs-lookup"><span data-stu-id="c7f89-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="c7f89-105">Nach ein Thread die Sperre angefordert hat, muss er die Sperre ordnungsgemäß beenden, bevor er erneut eingeben kann.</span><span class="sxs-lookup"><span data-stu-id="c7f89-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="c7f89-106">In der Regel können jeder Versuch, die Sperre erneut einen Deadlock verursachen würde, und Deadlocks sehr schwer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="c7f89-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="c7f89-107">Als Hilfe bei der Entwicklung <xref:System.Threading.SpinLock?displayProperty=nameWithType> unterstützt einen Modus zum Nachverfolgen von Threads, die bewirkt, eine Ausnahme ausgelöst werden dass, wenn ein Thread versucht, eine Sperre, die sie bereits enthält, erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="c7f89-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="c7f89-108">Dadurch können Sie, die mehrere den Punkt suchen Sie mit dem die Sperre nicht ordnungsgemäß beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c7f89-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="c7f89-109">Thread-Nachverfolgungsmodus einschalten, mithilfe der <xref:System.Threading.SpinLock> Konstruktor, der einen boolescher Wert akzeptiert Eingabeparameter, und übergeben ein Argument des `true`.</span><span class="sxs-lookup"><span data-stu-id="c7f89-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="c7f89-110">Deaktivieren Sie nach Abschluss der Entwicklung und Testphase Modus zum Nachverfolgen von Threads für eine bessere Leistung.</span><span class="sxs-lookup"><span data-stu-id="c7f89-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7f89-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7f89-111">Example</span></span>  
 <span data-ttu-id="c7f89-112">Das folgende Beispiel zeigt die Thread-Nachverfolgungsmodus.</span><span class="sxs-lookup"><span data-stu-id="c7f89-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="c7f89-113">Die Zeilen, die die Sperre ordnungsgemäß beenden sind auskommentiert, um einen Codefehler zu simulieren, die bewirkt, eines der folgenden Ergebnisse dass:</span><span class="sxs-lookup"><span data-stu-id="c7f89-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
-   <span data-ttu-id="c7f89-114">Eine Ausnahme wird ausgelöst, wenn die <xref:System.Threading.SpinLock> wurde erstellt, mit dem Argument der `true` (`True` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c7f89-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
-   <span data-ttu-id="c7f89-115">Wenn ein Deadlock auftreten der <xref:System.Threading.SpinLock> wurde erstellt, mit dem Argument der `false` (`False` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c7f89-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="c7f89-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7f89-116">See Also</span></span>  
 [<span data-ttu-id="c7f89-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="c7f89-117">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)
