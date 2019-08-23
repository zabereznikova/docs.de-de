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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2a083f46f24d6f3f24c63dd2415b85f975cfa29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912851"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="62ad4-102">ICorDebugController-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62ad4-102">ICorDebugController Interface</span></span>

<span data-ttu-id="62ad4-103">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="62ad4-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62ad4-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="62ad4-104">Methods</span></span>  
  
|<span data-ttu-id="62ad4-105">Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-105">Method</span></span>|<span data-ttu-id="62ad4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62ad4-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="62ad4-107">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="62ad4-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="62ad4-108">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="62ad4-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="62ad4-109">Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="62ad4-110">Setzt die Ausführung verwalteter Threads nach einem [ICorDebugController:: Stoppvorgang](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)fort.</span><span class="sxs-lookup"><span data-stu-id="62ad4-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="62ad4-111">Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="62ad4-112">Trennt den Debugger vom Prozess oder der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="62ad4-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="62ad4-113">EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="62ad4-114">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="62ad4-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="62ad4-115">HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="62ad4-116">Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.</span><span class="sxs-lookup"><span data-stu-id="62ad4-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="62ad4-117">IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="62ad4-118">Ruft einen Wert ab, der angibt, ob die Threads im Prozess momentan frei ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62ad4-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="62ad4-119">SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="62ad4-120">Legt den Debugstatus aller verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="62ad4-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="62ad4-121">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="62ad4-122">Führt einen kooperativen Haltepunkt für alle Threads aus, die verwalteten Code im Prozess ausführen.</span><span class="sxs-lookup"><span data-stu-id="62ad4-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="62ad4-123">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="62ad4-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="62ad4-124">Beendet den Prozess mit dem angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="62ad4-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62ad4-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62ad4-125">Remarks</span></span>  
 <span data-ttu-id="62ad4-126">Wenn `ICorDebugController` einen Prozess steuert, schließt der Bereich alle Threads des Prozesses ein.</span><span class="sxs-lookup"><span data-stu-id="62ad4-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="62ad4-127">Wenn `ICorDebugController` eine Anwendungsdomäne steuert, umfasst der Bereich nur die Threads dieser bestimmten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="62ad4-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62ad4-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="62ad4-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62ad4-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62ad4-129">Requirements</span></span>  
 <span data-ttu-id="62ad4-130">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62ad4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62ad4-131">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="62ad4-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62ad4-132">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62ad4-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62ad4-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62ad4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ad4-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62ad4-134">See also</span></span>

- [<span data-ttu-id="62ad4-135">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="62ad4-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
