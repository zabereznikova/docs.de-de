---
title: 'Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
ms.openlocfilehash: c33978226a02f65fdc495762af9286ba2daf9454
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723739"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a><span data-ttu-id="bec5c-102">Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock</span><span class="sxs-lookup"><span data-stu-id="bec5c-102">How to: Enable Thread-Tracking Mode in SpinLock</span></span>

<span data-ttu-id="bec5c-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> ist eine gegenseitige Low-Level- Ausschlusssperre, die Sie für Szenarien mit sehr kurzen Wartezeiten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="bec5c-103"><xref:System.Threading.SpinLock?displayProperty=nameWithType> is a low-level mutual exclusion lock that you can use for scenarios that have very short wait times.</span></span> <span data-ttu-id="bec5c-104"><xref:System.Threading.SpinLock> ist nicht wiedereintrittsfähig.</span><span class="sxs-lookup"><span data-stu-id="bec5c-104"><xref:System.Threading.SpinLock> is not re-entrant.</span></span> <span data-ttu-id="bec5c-105">Wenn ein Thread in die Sperre eintritt, muss er die Sperre ordnungsgemäß beenden, bevor er erneut eintreten kann.</span><span class="sxs-lookup"><span data-stu-id="bec5c-105">After a thread enters the lock, it must exit the lock correctly before it can enter again.</span></span> <span data-ttu-id="bec5c-106">In der Regel würde jeder Versuch, erneut in die Sperre einzutreten, einen Deadlock verursachen, und Deadlocks sind sehr schwer zu beheben.</span><span class="sxs-lookup"><span data-stu-id="bec5c-106">Typically, any attempt to re-enter the lock would cause deadlock, and deadlocks can be very difficult to debug.</span></span> <span data-ttu-id="bec5c-107">Als Hilfe zur Entwicklung unterstützt <xref:System.Threading.SpinLock?displayProperty=nameWithType> einen Modus zum Nachverfolgen von Threads, der bewirkt, dass eine Ausnahme ausgelöst wird, wenn ein Thread versucht, erneut in eine Sperre einzutreten, in der er sich bereits befindet.</span><span class="sxs-lookup"><span data-stu-id="bec5c-107">As an aid to development, <xref:System.Threading.SpinLock?displayProperty=nameWithType> supports a thread-tracking mode that causes an exception to be thrown when a thread attempts to re-enter a lock that it already holds.</span></span> <span data-ttu-id="bec5c-108">So können Sie leichter den Punkt lokalisieren, an dem die Sperre nicht ordnungsgemäß beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bec5c-108">This lets you more easily locate the point at which the lock was not exited correctly.</span></span> <span data-ttu-id="bec5c-109">Sie können den Modus zum Nachverfolgen von Threads mithilfe des <xref:System.Threading.SpinLock>-Konstruktors einschalten, der einen booleschen Eingabeparameter akzeptiert, und ein `true`-Argument übergeben.</span><span class="sxs-lookup"><span data-stu-id="bec5c-109">You can turn on thread-tracking mode by using the <xref:System.Threading.SpinLock> constructor that takes a Boolean input parameter, and passing in an argument of `true`.</span></span> <span data-ttu-id="bec5c-110">Deaktivieren Sie den Modus zum Nachverfolgen von Threads nach Abschluss der Entwicklungs- und Testphase im Interesse besserer Leistung.</span><span class="sxs-lookup"><span data-stu-id="bec5c-110">After you complete the development and testing phases, turn off thread-tracking mode for better performance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bec5c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bec5c-111">Example</span></span>  

 <span data-ttu-id="bec5c-112">Das folgende Beispiel veranschaulicht den Modus zum Nachverfolgen von Threads.</span><span class="sxs-lookup"><span data-stu-id="bec5c-112">The following example demonstrates thread-tracking mode.</span></span> <span data-ttu-id="bec5c-113">Die Zeilen zum ordnungsgemäßen Beenden der Sperre sind auskommentiert, um einen Codefehler zu simulieren, der eines der folgenden Ergebnisse bewirkt:</span><span class="sxs-lookup"><span data-stu-id="bec5c-113">The lines that correctly exit the lock are commented out to simulate a coding error that causes one of the following results:</span></span>  
  
- <span data-ttu-id="bec5c-114">Eine Ausnahme wird ausgelöst, wenn <xref:System.Threading.SpinLock> mit dem Argument `true` (`True` in Visual Basic) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bec5c-114">An exception is thrown if the <xref:System.Threading.SpinLock> was created by using an argument of `true` (`True` in Visual Basic).</span></span>  
  
- <span data-ttu-id="bec5c-115">Ein Deadlock wird ausgelöst, wenn <xref:System.Threading.SpinLock> mit dem Argument `false` (`False` in Visual Basic) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bec5c-115">Deadlock if the <xref:System.Threading.SpinLock> was created by using an argument of `false` (`False` in Visual Basic).</span></span>  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="bec5c-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bec5c-116">See also</span></span>

- [<span data-ttu-id="bec5c-117">SpinLock</span><span class="sxs-lookup"><span data-stu-id="bec5c-117">SpinLock</span></span>](spinlock.md)
