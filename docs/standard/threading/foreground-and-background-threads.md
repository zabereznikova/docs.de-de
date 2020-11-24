---
title: Vordergrund- und Hintergrundthreads
description: Bestimmen Sie mithilfe der Eigenschaft „Thread.IsBackground“ in .NET, ob es sich bei einem Thread um einen Hintergrund- oder um einen Vordergrundthread handelt, oder verwenden Sie diese Eigenschaft, um diese Einstellung zu ändern.
ms.date: 03/30/2017
helpviewer_keywords:
- threading [.NET], foreground
- threading [.NET], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 9f0ea1d53eb2f96b8a56cacc089cf90eb2f079a0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819902"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="67524-103">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="67524-103">Foreground and background threads</span></span>

<span data-ttu-id="67524-104">Ein verwalteter Thread ist entweder ein Hintergrund- oder Vordergrundthread.</span><span class="sxs-lookup"><span data-stu-id="67524-104">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="67524-105">Hintergrundthreads sind mit einer Ausnahme identisch mit Vordergrundthreads: Ein Hintergrundthread erhält nicht die Ausführung der verwalteten Ausführungsumgebung aufrecht.</span><span class="sxs-lookup"><span data-stu-id="67524-105">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="67524-106">Sobald alle Vordergrundthreads in einem verwalteten Prozess (wobei die EXE-Datei eine verwaltete Assembly ist) beendet sind, beendet das System alle Hintergrundthreads und fährt herunter.</span><span class="sxs-lookup"><span data-stu-id="67524-106">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67524-107">Wenn die Runtime einen Hintergrundthread beendet, da der Prozess heruntergefahren wird, wird keine Ausnahme im Thread ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="67524-107">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="67524-108">Wenn Threads allerdings beendet werden, da die <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>-Methode die Anwendungsdomäne entlädt, wird eine <xref:System.Threading.ThreadAbortException> sowohl im Vordergrund- als auch Hintergrundthread ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="67524-108">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="67524-109">Verwenden Sie die <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>-Eigenschaft, um zu bestimmen, ob ein Thread ein Hintergrund- oder Vordergrundthread ist, oder um seinen Status zu ändern.</span><span class="sxs-lookup"><span data-stu-id="67524-109">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="67524-110">Ein Thread kann jederzeit durch Festlegen seiner <xref:System.Threading.Thread.IsBackground%2A>-Eigenschaft auf `true` in einen Hintergrundthread geändert werden.</span><span class="sxs-lookup"><span data-stu-id="67524-110">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="67524-111">Der Vorder- oder Hintergrundstatus eines Threads wirkt sich nicht auf das Ergebnis einer nicht behandelten Ausnahme im Thread aus.</span><span class="sxs-lookup"><span data-stu-id="67524-111">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="67524-112">Ein Ausnahmefehler in Vorder- oder Hintergrundthreads führt zum Beenden der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="67524-112">An unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="67524-113">Siehe [Ausnahmen in verwalteten Threads](exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="67524-113">See [Exceptions in Managed Threads](exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="67524-114">Threads, die zum verwalteten Threadpool gehört (d.h. Threads, deren <xref:System.Threading.Thread.IsThreadPoolThread%2A>-Eigenschaft `true` ist), sind Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="67524-114">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="67524-115">Alle Threads, die aus nicht verwaltetem Code in die verwaltete Ausführungsumgebung eingehen, werden als Hintergrundthreads markiert.</span><span class="sxs-lookup"><span data-stu-id="67524-115">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="67524-116">Alle Threads, die durch Erstellen und Starten eines neuen <xref:System.Threading.Thread>-Objekts generiert werden, sind standardmäßig Vordergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="67524-116">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="67524-117">Wenn Sie einen Thread zur Überwachung einer Aktivität, z.B. einer Socketverbindung, verwenden, legen Sie seine <xref:System.Threading.Thread.IsBackground%2A>-Eigenschaft auf `true` fest, sodass der Thread nicht das Beenden Ihres Prozesses verhindert.</span><span class="sxs-lookup"><span data-stu-id="67524-117">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67524-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67524-118">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
