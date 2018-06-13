---
title: ICorDebugController Schnittstelle1
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
ms.openlocfilehash: 230488201b637c5a53f41dd4c3f204b37e8984fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411469"
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="a87ef-102">ICorDebugController Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="a87ef-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="a87ef-103">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="a87ef-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a87ef-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a87ef-104">Methods</span></span>  
  
|<span data-ttu-id="a87ef-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-105">Method</span></span>|<span data-ttu-id="a87ef-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a87ef-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="a87ef-107">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="a87ef-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="a87ef-108">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="a87ef-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="a87ef-109">Continue-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="a87ef-110">Setzt die Ausführung des verwalteten Threads nach einem Aufruf von [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="a87ef-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="a87ef-111">Detach-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="a87ef-112">Trennt den Debugger aus der Domäne verarbeiten oder in der Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a87ef-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="a87ef-113">EnumerateThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="a87ef-114">Ruft einen Enumerator für die aktiven verwalteten Threads im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="a87ef-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="a87ef-115">HasQueuedCallbacks-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="a87ef-116">Ruft einen Wert, der angibt, ob die verwalteten Rückrufe zurzeit für den angegebenen Thread in der Warteschlange befinden.</span><span class="sxs-lookup"><span data-stu-id="a87ef-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="a87ef-117">IsRunning-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="a87ef-118">Ruft einen Wert, der angibt, ob die Threads im Prozess zurzeit frei ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87ef-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="a87ef-119">SetAllThreadsDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="a87ef-120">Legt den Debugzustand aller verwalteten Threads im Prozess an.</span><span class="sxs-lookup"><span data-stu-id="a87ef-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="a87ef-121">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="a87ef-122">Beendet alle Threads, die verwalteten Code im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a87ef-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="a87ef-123">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="a87ef-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="a87ef-124">Beendet den Prozess mit dem angegebenen Exitcode.</span><span class="sxs-lookup"><span data-stu-id="a87ef-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a87ef-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a87ef-125">Remarks</span></span>  
 <span data-ttu-id="a87ef-126">Wenn `ICorDebugController` wird zum Steuern eines Prozesses, enthält der Bereich alle Threads des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a87ef-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="a87ef-127">Wenn `ICorDebugController` wird zum Steuern einer Anwendungsdomäne, enthält den Bereich nur die Threads dieses bestimmten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="a87ef-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a87ef-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a87ef-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a87ef-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a87ef-129">Requirements</span></span>  
 <span data-ttu-id="a87ef-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a87ef-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a87ef-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a87ef-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a87ef-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a87ef-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a87ef-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a87ef-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a87ef-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a87ef-134">See Also</span></span>  
 [<span data-ttu-id="a87ef-135">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a87ef-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
