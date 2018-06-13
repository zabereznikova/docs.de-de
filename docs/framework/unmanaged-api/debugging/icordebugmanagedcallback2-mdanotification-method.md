---
title: ICorDebugManagedCallback2::MDANotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b09c173e2f66d4c650083cc12f8a0ac2c92007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417227"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="5d265-102">ICorDebugManagedCallback2::MDANotification-Methode</span><span class="sxs-lookup"><span data-stu-id="5d265-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="5d265-103">Stellt die Benachrichtigung, dass die Ausführung von Code ein Assistent für verwaltetes Debuggen (MDA) in der Anwendung gefunden hat, die gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="5d265-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d265-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d265-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d265-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d265-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="5d265-106">[in] Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess verfügbar macht oder die Anwendungsdomäne, in der der MDA aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5d265-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="5d265-107">Ein Debugger sollten keine Annahmen darüber, ob der Controller ein Prozess oder eine Anwendungsdomäne ist zwar die Schnittstelle, um eine Entscheidung zu treffen immer abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d265-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5d265-108">[in] Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, auf dem das Debug-Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5d265-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="5d265-109">Wenn der MDA aufgetreten ist, auf eine nicht verwaltete thread, den Wert des `pThread` wird null sein.</span><span class="sxs-lookup"><span data-stu-id="5d265-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="5d265-110">Sie müssen die Thread-ID (BS) aus dem MDA-Objekt selbst abrufen.</span><span class="sxs-lookup"><span data-stu-id="5d265-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="5d265-111">[in] Ein Zeiger auf ein [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) Schnittstelle, die MDA-Informationen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="5d265-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d265-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d265-112">Remarks</span></span>  
 <span data-ttu-id="5d265-113">Ein MDA ist eine heuristische Warnung und erfordert kein Eingreifen explizite Debugger außer Aufrufen [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) zum Fortsetzen der Ausführung der Anwendung, die gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="5d265-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="5d265-114">Die common Language Runtime (CLR) kann ermitteln, welcher MDAs werden ausgelöst, welche Daten befinden sich in jeder angegebenen MDA zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="5d265-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="5d265-115">Aus diesem Grund sollte Debugger nicht erstellt werden solche Funktionen verwendet werden, erfordern bestimmte MDA-Muster.</span><span class="sxs-lookup"><span data-stu-id="5d265-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="5d265-116">MDAs möglicherweise in die Warteschlange gestellt und ausgelöst, kurz nachdem der MDA festgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5d265-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="5d265-117">Dies kann passieren, wenn die Laufzeit muss warten, bis auf einem sicheren Zeitpunkt zum Auslösen des MDA, statt den MDA ausgelöst wird, wenn es gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="5d265-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="5d265-118">Dies bedeutet auch, dass die Common Language Runtime eine Anzahl von MDAs in einem einzelnen Satz von in der Warteschlange Rückrufe (ähnlich wie ein "Anfügen" Ereignis-Vorgang) ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="5d265-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="5d265-119">Ein Debugger sollte aufheben den Verweis auf ein `ICorDebugMDA` Instanz sofort nach der Rückgabe aus der `MDANotification` Rückruf, um die CLR beim wiederverwenden des Speicherplatzes, der von einem MDA zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5d265-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="5d265-120">Das Freigeben der Instanz kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="5d265-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d265-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d265-121">Requirements</span></span>  
 <span data-ttu-id="5d265-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d265-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d265-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d265-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d265-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d265-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d265-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d265-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d265-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d265-126">See Also</span></span>  
 [<span data-ttu-id="5d265-127">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="5d265-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="5d265-128">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d265-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="5d265-129">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d265-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
