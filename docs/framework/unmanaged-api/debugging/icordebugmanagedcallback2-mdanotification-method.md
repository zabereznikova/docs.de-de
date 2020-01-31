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
ms.openlocfilehash: bf9ea40cc81be37499e6729006e7177a8000c000
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793299"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="238c7-102">ICorDebugManagedCallback2::MDANotification-Methode</span><span class="sxs-lookup"><span data-stu-id="238c7-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="238c7-103">Stellt eine Benachrichtigung bereit, dass die Codeausführung in der zu debuggenden Anwendung einen Assistenten für verwaltetes Debuggen (MDA) gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="238c7-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="238c7-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="238c7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="238c7-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="238c7-106">[in] Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess verfügbar macht oder die Anwendungsdomäne, in der der MDA aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="238c7-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="238c7-107">Ein Debugger sollte keine Annahmen darüber treffen, ob der Controller ein Prozess oder eine Anwendungsdomäne ist, obwohl er die Schnittstelle jederzeit Abfragen kann, um eine Entscheidung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="238c7-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="238c7-108">[in] Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, auf dem das Debug-Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="238c7-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="238c7-109">Wenn der MDA in einem nicht verwalteten Thread aufgetreten ist, wird der Wert `pThread` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="238c7-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="238c7-110">Sie müssen die Thread-ID des Betriebssystems (OS) aus dem MDA-Objekt selbst erhalten.</span><span class="sxs-lookup"><span data-stu-id="238c7-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="238c7-111">in Ein Zeiger auf eine [ICorDebugMDA](icordebugmda-interface.md) -Schnittstelle, die die MDA-Informationen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="238c7-111">[in] A pointer to an [ICorDebugMDA](icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="238c7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="238c7-112">Remarks</span></span>  
 <span data-ttu-id="238c7-113">Ein MDA ist eine heuristische Warnung und erfordert keine explizite Debuggeraktion außer dem Aufruf von [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) , um die Ausführung der Anwendung fortzusetzen, die gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="238c7-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="238c7-114">Der Common Language Runtime (CLR) kann bestimmen, welche MDAs ausgelöst werden und welche Daten an einem beliebigen Punkt in einem beliebigen MDA vorliegen.</span><span class="sxs-lookup"><span data-stu-id="238c7-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="238c7-115">Daher sollten Debugger keine Funktionen erstellen, die bestimmte MDA-Muster erfordern.</span><span class="sxs-lookup"><span data-stu-id="238c7-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="238c7-116">MDAs kann in der Warteschlange eingereiht und unmittelbar nach dem Auftreten des MDA ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="238c7-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="238c7-117">Dies kann der Fall sein, wenn die Laufzeit gewartet werden muss, bis Sie einen sicheren Punkt zum Auslösen des MDA erreicht, anstatt den MDA bei Auftreten des MDA auszulösen.</span><span class="sxs-lookup"><span data-stu-id="238c7-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="238c7-118">Dies bedeutet auch, dass die Laufzeit möglicherweise eine Reihe von MDAs in einem einzelnen Satz von Rückrufe in der Warteschlange auslöst (ähnlich wie bei einem Vorgang zum Anfügen eines Ereignisses).</span><span class="sxs-lookup"><span data-stu-id="238c7-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="238c7-119">Ein Debugger sollte den Verweis auf eine `ICorDebugMDA` Instanz sofort nach der Rückgabe des `MDANotification` Rückrufs freigeben, damit die CLR den von einem MDA genutzten Arbeitsspeicher wieder verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="238c7-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="238c7-120">Das Freigeben der Instanz kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="238c7-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238c7-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="238c7-121">Requirements</span></span>  
 <span data-ttu-id="238c7-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238c7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238c7-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="238c7-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="238c7-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238c7-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238c7-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238c7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238c7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="238c7-126">See also</span></span>

- [<span data-ttu-id="238c7-127">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="238c7-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="238c7-128">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="238c7-128">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="238c7-129">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="238c7-129">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
