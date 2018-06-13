---
title: ICorDebugProcess Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e4e3854a850c9639e93c8db2ec8ccd567b242b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423168"
---
# <a name="icordebugprocess-interface1"></a><span data-ttu-id="77c52-102">ICorDebugProcess Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="77c52-102">ICorDebugProcess Interface1</span></span>
<span data-ttu-id="77c52-103">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="77c52-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="77c52-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="77c52-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="77c52-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="77c52-105">Methods</span></span>  
  
|<span data-ttu-id="77c52-106">Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-106">Method</span></span>|<span data-ttu-id="77c52-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77c52-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="77c52-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="77c52-109">Löscht die aktuellen nicht verwalteten Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="77c52-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="77c52-110">EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="77c52-111">Aktiviert und deaktiviert das Senden von Meldungen an dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="77c52-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="77c52-112">EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="77c52-113">Listet alle Anwendungsdomänen im Prozess.</span><span class="sxs-lookup"><span data-stu-id="77c52-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="77c52-114">EnumerateObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="77c52-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="77c52-115">Not implemented.</span></span>|  
|[<span data-ttu-id="77c52-116">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="77c52-117">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="77c52-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="77c52-118">GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="77c52-119">Ruft die Thread-ID (BS) für interne Hilfsthreads des Debuggers an.</span><span class="sxs-lookup"><span data-stu-id="77c52-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="77c52-120">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="77c52-121">Ruft die ID (BS) des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="77c52-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="77c52-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="77c52-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="77c52-123">Not implemented.</span></span>|  
|[<span data-ttu-id="77c52-124">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="77c52-125">Ruft ICorDebugThread-Instanz, die den angegebenen OS-Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="77c52-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="77c52-126">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="77c52-127">Ruft den Kontext für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="77c52-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="77c52-128">IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="77c52-129">Bestimmt, ob der Thread als Ergebnis der Debugger, beenden den Prozess angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="77c52-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="77c52-130">IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="77c52-131">Bestimmt, ob eine Adresse innerhalb eines Stubs, das einen Übergang zu verwaltetem Code bewirkt.</span><span class="sxs-lookup"><span data-stu-id="77c52-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="77c52-132">ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="77c52-133">Legt den Schweregrad der angegebenen Log-Schalter.</span><span class="sxs-lookup"><span data-stu-id="77c52-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="77c52-134">ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="77c52-135">Liest Arbeitsspeicher aus dem Prozess.</span><span class="sxs-lookup"><span data-stu-id="77c52-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="77c52-136">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="77c52-137">Legt den Kontext für den angegebenen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="77c52-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="77c52-138">ThreadForFiberCookie-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="77c52-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="77c52-139">Deprecated.</span></span>|  
|[<span data-ttu-id="77c52-140">WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="77c52-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="77c52-141">Schreibt Daten in einem Bereich des Arbeitsspeichers im Prozess.</span><span class="sxs-lookup"><span data-stu-id="77c52-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77c52-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="77c52-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77c52-143">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="77c52-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77c52-144">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="77c52-144">Requirements</span></span>  
 <span data-ttu-id="77c52-145">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77c52-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77c52-146">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77c52-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77c52-147">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77c52-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77c52-148">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77c52-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c52-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77c52-149">See Also</span></span>  
 [<span data-ttu-id="77c52-150">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77c52-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="77c52-151">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="77c52-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
