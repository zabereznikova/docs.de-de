---
title: ICorDebugManagedCallback2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1ecfea208f87f53f15fcc4cdafb58341c293e43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096087"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="37876-102">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37876-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="37876-103">Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="37876-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="37876-104">`ICorDebugManagedCallback2` ist eine logische Erweiterung von der [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="37876-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37876-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="37876-105">Methods</span></span>  
  
|<span data-ttu-id="37876-106">Methode</span><span class="sxs-lookup"><span data-stu-id="37876-106">Method</span></span>|<span data-ttu-id="37876-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37876-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37876-108">ChangeConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="37876-109">Benachrichtigt den Debugger an, dass der Satz von Aufgaben im Zusammenhang mit der angegebenen Verbindung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="37876-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="37876-110">CreateConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="37876-111">Benachrichtigt den Debugger an, dass eine neue Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37876-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="37876-112">DestroyConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="37876-113">Benachrichtigt den Debugger an, dass die angegebene Verbindung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="37876-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="37876-114">Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="37876-115">Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="37876-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="37876-116">ExceptionUnwind-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="37876-117">Stellt eine Benachrichtigung zum Status während des endladungsprozesses Ausnahme bereit.</span><span class="sxs-lookup"><span data-stu-id="37876-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="37876-118">FunctionRemapComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="37876-119">Benachrichtigt den Debugger, dass die Ausführung von Code auf eine neue Version einer bearbeiteten Funktion gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="37876-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="37876-120">FunctionRemapOpportunity-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="37876-121">Benachrichtigt den Debugger, dass die codeausführung einen Sequenzpunkt in einer früheren Version einer bearbeiteten Funktion erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="37876-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="37876-122">MDANotification-Methode</span><span class="sxs-lookup"><span data-stu-id="37876-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="37876-123">Stellt die Benachrichtigung, dass die Ausführung von Code mit eine verwalteten debugging Assistant, Assistent für (verwaltetes Debuggen MDA) Nachricht aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="37876-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37876-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37876-124">Remarks</span></span>  
 <span data-ttu-id="37876-125">Die `ICorDebugManagedCallback2` Schnittstelle erweitert die `ICorDebugManagedCallback` -Schnittstelle neue Debug-Ereignisse, die in .NET Framework, Version 2.0 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="37876-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="37876-126">Ein Debugger muss implementieren `ICorDebugManagedCallback2` , wenn sie .NET Framework 2.0-Anwendungen Debuggen ist.</span><span class="sxs-lookup"><span data-stu-id="37876-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="37876-127">Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als das Rückrufobjekt zu übergeben, [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="37876-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37876-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="37876-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37876-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37876-129">Requirements</span></span>  
 <span data-ttu-id="37876-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37876-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37876-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37876-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37876-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37876-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37876-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37876-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37876-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37876-134">See also</span></span>

- [<span data-ttu-id="37876-135">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="37876-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="37876-136">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="37876-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="37876-137">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="37876-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
