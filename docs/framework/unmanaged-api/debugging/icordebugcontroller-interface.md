---
title: ICorDebugController-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: d6c923f03309da3ad8092ea6119e7d850120ee2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783801"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="87ffb-102">ICorDebugController-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87ffb-102">ICorDebugController Interface</span></span>

<span data-ttu-id="87ffb-103">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="87ffb-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87ffb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="87ffb-104">Methods</span></span>  
  
|<span data-ttu-id="87ffb-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-105">Method</span></span>|<span data-ttu-id="87ffb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87ffb-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="87ffb-107">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="87ffb-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="87ffb-108">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="87ffb-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="87ffb-109">Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-109">Continue Method</span></span>](icordebugcontroller-continue-method.md)|<span data-ttu-id="87ffb-110">Setzt die Ausführung verwalteter Threads nach einem [ICorDebugController:: Stoppvorgang](icordebugcontroller-stop-method.md)fort.</span><span class="sxs-lookup"><span data-stu-id="87ffb-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="87ffb-111">Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-111">Detach Method</span></span>](icordebugcontroller-detach-method.md)|<span data-ttu-id="87ffb-112">Trennt den Debugger vom Prozess oder der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="87ffb-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="87ffb-113">EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-113">EnumerateThreads Method</span></span>](icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="87ffb-114">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="87ffb-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="87ffb-115">HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-115">HasQueuedCallbacks Method</span></span>](icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="87ffb-116">Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.</span><span class="sxs-lookup"><span data-stu-id="87ffb-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="87ffb-117">IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-117">IsRunning Method</span></span>](icordebugcontroller-isrunning-method.md)|<span data-ttu-id="87ffb-118">Ruft einen Wert ab, der angibt, ob die Threads im Prozess momentan frei ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="87ffb-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="87ffb-119">SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-119">SetAllThreadsDebugState Method</span></span>](icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="87ffb-120">Legt den Debugstatus aller verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="87ffb-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="87ffb-121">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-121">Stop Method</span></span>](icordebugcontroller-stop-method.md)|<span data-ttu-id="87ffb-122">Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="87ffb-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="87ffb-123">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="87ffb-123">Terminate Method</span></span>](icordebugcontroller-terminate-method.md)|<span data-ttu-id="87ffb-124">Beendet den Prozess mit dem angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="87ffb-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87ffb-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87ffb-125">Remarks</span></span>  
 <span data-ttu-id="87ffb-126">Wenn `ICorDebugController` einen Prozess steuert, umfasst der Bereich alle Threads des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="87ffb-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="87ffb-127">Wenn `ICorDebugController` eine Anwendungsdomäne steuert, umfasst der Bereich nur die Threads dieser bestimmten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="87ffb-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87ffb-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="87ffb-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87ffb-129">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87ffb-129">Requirements</span></span>  
 <span data-ttu-id="87ffb-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87ffb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87ffb-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87ffb-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87ffb-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87ffb-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87ffb-133">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87ffb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87ffb-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87ffb-134">See also</span></span>

- [<span data-ttu-id="87ffb-135">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="87ffb-135">Debugging Interfaces</span></span>](debugging-interfaces.md)
