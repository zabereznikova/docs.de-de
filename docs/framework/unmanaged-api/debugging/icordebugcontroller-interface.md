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
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107548"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="ca546-102">ICorDebugController-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca546-102">ICorDebugController Interface</span></span>

<span data-ttu-id="ca546-103">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ca546-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca546-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca546-104">Methods</span></span>  
  
|<span data-ttu-id="ca546-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-105">Method</span></span>|<span data-ttu-id="ca546-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca546-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="ca546-107">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="ca546-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="ca546-108">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="ca546-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="ca546-109">Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="ca546-110">Setzt die Ausführung von verwalteten Threads nach einem Aufruf von [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca546-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="ca546-111">Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="ca546-112">Trennt den Debugger aus der Domäne Prozess- oder Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ca546-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="ca546-113">EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="ca546-114">Ruft einen Enumerator für die aktiv verwalteten Threads im Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="ca546-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="ca546-115">HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="ca546-116">Ruft einen Wert, der angibt, ob die verwalteten Rückrufe derzeit für den angegebenen Thread in der Warteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="ca546-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="ca546-117">IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="ca546-118">Ruft einen Wert, der angibt, ob die Threads im Prozess frei derzeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca546-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="ca546-119">SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="ca546-120">Legt den Debugzustand des alle verwalteten Threads im Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="ca546-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="ca546-121">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="ca546-122">Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ca546-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="ca546-123">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="ca546-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="ca546-124">Beendet den Prozess mit den angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="ca546-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca546-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca546-125">Remarks</span></span>  
 <span data-ttu-id="ca546-126">Wenn `ICorDebugController` ist einen Prozess steuert, der Bereich enthält alle Threads des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ca546-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="ca546-127">Wenn `ICorDebugController` ist steuern eine Anwendungsdomäne, enthält der Bereich nur die Threads von dieser bestimmten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="ca546-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca546-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ca546-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca546-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca546-129">Requirements</span></span>  
 <span data-ttu-id="ca546-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca546-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca546-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca546-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca546-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca546-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ca546-133">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ca546-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ca546-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca546-134">See also</span></span>

- [<span data-ttu-id="ca546-135">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca546-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
