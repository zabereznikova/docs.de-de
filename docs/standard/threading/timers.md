---
title: Timer
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 478484651bf839f842148f0b4164c9387db3b98a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="timers"></a><span data-ttu-id="232c1-102">Timer</span><span class="sxs-lookup"><span data-stu-id="232c1-102">Timers</span></span>
<span data-ttu-id="232c1-103">Timer sind kompakte Objekte, mit denen angegeben werden kann, dass ein Delegat zu einem bestimmten Zeitpunkt aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="232c1-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="232c1-104">Der Wartevorgang wird von einem Thread im Threadpool ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="232c1-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="232c1-105">Die Verwendung der <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse ist einfach.</span><span class="sxs-lookup"><span data-stu-id="232c1-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="232c1-106">Sie erstellen einen **Timer**, der einen <xref:System.Threading.TimerCallback>-Delegaten an die Rückrufmethode übergibt, ein Objekt, das den an den Rückruf zu übergebenden Zustand darstellt, einen Zeitpunkt für den ersten Aufruf und eine Zeitspanne, die das Intervall zwischen den Aufrufen des Rückrufs darstellt.</span><span class="sxs-lookup"><span data-stu-id="232c1-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="232c1-107">Um einen anstehenden Timer zu löschen, rufen Sie die **Timer.Dispose**-Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="232c1-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="232c1-108">Es gibt zwei weitere Timerklassen.</span><span class="sxs-lookup"><span data-stu-id="232c1-108">There are two other timer classes.</span></span> <span data-ttu-id="232c1-109">Die <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>-Klasse ist ein Steuerelement, dass mit visuellen Designern arbeitet und für die Verwendung im Benutzeroberflächenkontext vorgesehen ist. Es löst Ereignisse für den Benutzeroberflächenthread aus.</span><span class="sxs-lookup"><span data-stu-id="232c1-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="232c1-110">Die <xref:System.Timers.Timer?displayProperty=nameWithType>-Klasse ist von <xref:System.ComponentModel.Component> abgeleitet und kann daher mit visuellen Designern verwendet werden. Sie löst ebenfalls Ereignisse aus, jedoch für einen <xref:System.Threading.ThreadPool>-Thread.</span><span class="sxs-lookup"><span data-stu-id="232c1-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="232c1-111">Die <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse nimmt Rückrufe für einen <xref:System.Threading.ThreadPool>-Thread vor und verwendet das Ereignismodell nicht.</span><span class="sxs-lookup"><span data-stu-id="232c1-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="232c1-112">Im Gegensatz zu anderen Zeitgebern stellt sie der Rückrufmethode auch ein Zustandsobjekt bereit.</span><span class="sxs-lookup"><span data-stu-id="232c1-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="232c1-113">Dies ist eine sehr einfache Klasse.</span><span class="sxs-lookup"><span data-stu-id="232c1-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="232c1-114">Im folgenden Codebeispiel wird ein Timer gestartet, der nach einer Sekunde (1.000 Millisekunden) startet und jede Sekunde hochzählt, bis die **Enter**-Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="232c1-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="232c1-115">Bei der Variablen mit dem Verweis auf den Timer handelt es sich um ein Feld auf Klassenebene, um zu verhindern, dass der Timer während der Ausführung von der Garbage Collection erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="232c1-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="232c1-116">Weitere Informationen über die aggressive Garbage Collection finden Sie unter <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="232c1-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="232c1-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="232c1-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="232c1-118">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="232c1-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
