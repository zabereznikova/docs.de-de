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
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131459"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="de34a-102">ICorDebugManagedCallback2::MDANotification-Methode</span><span class="sxs-lookup"><span data-stu-id="de34a-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="de34a-103">Stellt eine Benachrichtigung bereit, dass die Codeausführung in der zu debuggenden Anwendung einen Assistenten für verwaltetes Debuggen (MDA) gefunden hat.</span><span class="sxs-lookup"><span data-stu-id="de34a-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de34a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de34a-104">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de34a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de34a-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="de34a-106">in Ein Zeiger auf eine ICorDebugController-Schnittstelle, die den Prozess oder die Anwendungsdomäne verfügbar macht, in der der MDA aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="de34a-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="de34a-107">Ein Debugger sollte keine Annahmen darüber treffen, ob der Controller ein Prozess oder eine Anwendungsdomäne ist, obwohl er die Schnittstelle jederzeit Abfragen kann, um eine Entscheidung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="de34a-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="de34a-108">in Ein Zeiger auf eine ICorDebugThread-Schnittstelle, die den verwalteten Thread verfügbar macht, für den das Debugereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="de34a-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="de34a-109">Wenn der MDA in einem nicht verwalteten Thread aufgetreten ist, wird der Wert `pThread` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="de34a-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="de34a-110">Sie müssen die Thread-ID des Betriebssystems (OS) aus dem MDA-Objekt selbst erhalten.</span><span class="sxs-lookup"><span data-stu-id="de34a-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="de34a-111">in Ein Zeiger auf eine [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) -Schnittstelle, die die MDA-Informationen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="de34a-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de34a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de34a-112">Remarks</span></span>  
 <span data-ttu-id="de34a-113">Ein MDA ist eine heuristische Warnung und erfordert keine explizite Debuggeraktion außer dem Aufruf von [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , um die Ausführung der Anwendung fortzusetzen, die gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="de34a-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="de34a-114">Der Common Language Runtime (CLR) kann bestimmen, welche MDAs ausgelöst werden und welche Daten an einem beliebigen Punkt in einem beliebigen MDA vorliegen.</span><span class="sxs-lookup"><span data-stu-id="de34a-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="de34a-115">Daher sollten Debugger keine Funktionen erstellen, die bestimmte MDA-Muster erfordern.</span><span class="sxs-lookup"><span data-stu-id="de34a-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="de34a-116">MDAs kann in der Warteschlange eingereiht und unmittelbar nach dem Auftreten des MDA ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="de34a-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="de34a-117">Dies kann der Fall sein, wenn die Laufzeit gewartet werden muss, bis Sie einen sicheren Punkt zum Auslösen des MDA erreicht, anstatt den MDA bei Auftreten des MDA auszulösen.</span><span class="sxs-lookup"><span data-stu-id="de34a-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="de34a-118">Dies bedeutet auch, dass die Laufzeit möglicherweise eine Reihe von MDAs in einem einzelnen Satz von Rückrufe in der Warteschlange auslöst (ähnlich wie bei einem Vorgang zum Anfügen eines Ereignisses).</span><span class="sxs-lookup"><span data-stu-id="de34a-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="de34a-119">Ein Debugger sollte den Verweis auf eine `ICorDebugMDA` Instanz sofort nach der Rückgabe des `MDANotification` Rückrufs freigeben, damit die CLR den von einem MDA genutzten Arbeitsspeicher wieder verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="de34a-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="de34a-120">Das Freigeben der Instanz kann die Leistung verbessern, wenn viele MDAs ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="de34a-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de34a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de34a-121">Requirements</span></span>  
 <span data-ttu-id="de34a-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de34a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de34a-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de34a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de34a-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de34a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de34a-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de34a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de34a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de34a-126">See also</span></span>

- [<span data-ttu-id="de34a-127">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="de34a-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="de34a-128">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de34a-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="de34a-129">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de34a-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
