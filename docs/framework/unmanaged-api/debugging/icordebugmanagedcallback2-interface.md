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
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689783"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="fb197-102">ICorDebugManagedCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb197-102">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="fb197-103">Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fb197-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="fb197-104">`ICorDebugManagedCallback2` ist eine logische Erweiterung der [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fb197-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb197-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="fb197-105">Methods</span></span>  
  
|<span data-ttu-id="fb197-106">Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-106">Method</span></span>|<span data-ttu-id="fb197-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb197-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb197-108">ChangeConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="fb197-109">Benachrichtigt den Debugger, dass sich der Satz der Tasks, die der angegebenen Verbindung zugeordnet sind, geändert hat.</span><span class="sxs-lookup"><span data-stu-id="fb197-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="fb197-110">CreateConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="fb197-111">Benachrichtigt den Debugger, dass eine neue Verbindung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb197-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="fb197-112">DestroyConnection-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="fb197-113">Benachrichtigt den Debugger, dass die angegebene Verbindung beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fb197-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="fb197-114">Exception-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="fb197-115">Benachrichtigt den Debugger, dass eine Suche nach einem Ausnahmehandler gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="fb197-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="fb197-116">ExceptionUnwind-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="fb197-117">Stellt während des Entwicklungs Vorgangs der Ausnahme eine Status Benachrichtigung bereit.</span><span class="sxs-lookup"><span data-stu-id="fb197-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="fb197-118">FunctionRemapComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="fb197-119">Benachrichtigt den Debugger, dass die Codeausführung zu einer neuen Version einer bearbeiteten Funktion gewechselt hat.</span><span class="sxs-lookup"><span data-stu-id="fb197-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="fb197-120">FunctionRemapOpportunity-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="fb197-121">Benachrichtigt den Debugger, dass die Codeausführung einen Sequenz Punkt in einer älteren Version einer bearbeiteten Funktion erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="fb197-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="fb197-122">MDANotification-Methode</span><span class="sxs-lookup"><span data-stu-id="fb197-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="fb197-123">Stellt eine Benachrichtigung bereit, dass bei der Codeausführung eine MDA-Nachricht (Managed Debug Assistant) aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fb197-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb197-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb197-124">Remarks</span></span>  

 <span data-ttu-id="fb197-125">Die- `ICorDebugManagedCallback2` Schnittstelle erweitert die- `ICorDebugManagedCallback` Schnittstelle, um neue Debugereignisse zu verarbeiten, die in der .NET Framework Version 2,0</span><span class="sxs-lookup"><span data-stu-id="fb197-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="fb197-126">Ein Debugger muss implementieren, `ICorDebugManagedCallback2` Wenn er .NET Framework 2,0-Anwendungen debuggt.</span><span class="sxs-lookup"><span data-stu-id="fb197-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="fb197-127">Eine Instanz von `ICorDebugManagedCallback` oder `ICorDebugManagedCallback2` wird als Rückruf Objekt an [ICorDebug:: SetManagedHandler](icordebug-setmanagedhandler-method.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="fb197-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb197-128">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fb197-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb197-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb197-129">Requirements</span></span>  

 <span data-ttu-id="fb197-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb197-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb197-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb197-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb197-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb197-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb197-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb197-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb197-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb197-134">See also</span></span>

- [<span data-ttu-id="fb197-135">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="fb197-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="fb197-136">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fb197-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fb197-137">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb197-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
