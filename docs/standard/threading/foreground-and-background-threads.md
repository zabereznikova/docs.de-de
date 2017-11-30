---
title: Vordergrund- und Hintergrundthreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="53a4b-102">Vordergrund- und Hintergrundthreads</span><span class="sxs-lookup"><span data-stu-id="53a4b-102">Foreground and Background Threads</span></span>
<span data-ttu-id="53a4b-103">Ein verwalteter Thread ist ein Hintergrundthread oder ein Vordergrundthread.</span><span class="sxs-lookup"><span data-stu-id="53a4b-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="53a4b-104">Hintergrundthreads sind identisch mit Vordergrundthreads mit einer Ausnahme: ein Hintergrundthread ist nicht möglich, die verwaltete ausführungsumgebung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="53a4b-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="53a4b-105">Sobald alle Vordergrundthreads, in einem verwalteten Prozess (wobei die .exe-Datei für eine verwaltete Assembly ist) beendet wurde, wird das System beendet alle Hintergrundthreads ausgeführt und beendet wird.</span><span class="sxs-lookup"><span data-stu-id="53a4b-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53a4b-106">Wenn die Common Language Runtime einen Hintergrundthread beendet wird, da der Prozess heruntergefahren wird, wird keine Ausnahme im Thread ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="53a4b-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="53a4b-107">Allerdings der Wenn-Threads beendet werden, da die <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> Methode entladen die Anwendungsdomäne eine <xref:System.Threading.ThreadAbortException> im Vordergrund-und Hintergrundthreads ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="53a4b-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="53a4b-108">Verwenden der <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> Eigenschaft, um zu bestimmen, ob ein Thread einen Hintergrund oder ein Vordergrundthread ist, oder auf deren Status zu ändern.</span><span class="sxs-lookup"><span data-stu-id="53a4b-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="53a4b-109">Ein Thread kann geändert werden in einen Hintergrundthread jederzeit durch Festlegen seiner <xref:System.Threading.Thread.IsBackground%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="53a4b-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53a4b-110">Der Status Vorder- oder Hintergrund für einen Thread, wirkt sich nicht auf das Ergebnis einer nicht behandelten Ausnahme im Thread aus.</span><span class="sxs-lookup"><span data-stu-id="53a4b-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="53a4b-111">In .NET Framework, Version 2.0 führt eine nicht behandelte Ausnahme im Vorder- oder Hintergrund Threads bei Beendigung der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="53a4b-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="53a4b-112">Finden Sie unter [Ausnahmen in verwalteten Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="53a4b-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="53a4b-113">Threads, die auf dem verwalteten Threadpool gehört (d. h., threads, deren <xref:System.Threading.Thread.IsThreadPoolThread%2A> Eigenschaft `true`) sind Hintergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="53a4b-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="53a4b-114">Alle Threads, die die verwaltete ausführungsumgebung von nicht verwaltetem Code eingeben, werden als Hintergrundthreads markiert.</span><span class="sxs-lookup"><span data-stu-id="53a4b-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="53a4b-115">Alle Threads, die durch Erstellen und Starten eines neuen generiert <xref:System.Threading.Thread> Objekt sind standardmäßig Vordergrundthreads.</span><span class="sxs-lookup"><span data-stu-id="53a4b-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="53a4b-116">Festlegen, wenn Sie einen Thread verwenden, um eine Aktivität, z. B. eine Socketverbindung überwachen seine <xref:System.Threading.Thread.IsBackground%2A> Eigenschaft `true` so, dass der Thread verhindert nicht, den Prozess beendet wird.</span><span class="sxs-lookup"><span data-stu-id="53a4b-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53a4b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53a4b-117">See Also</span></span>  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
