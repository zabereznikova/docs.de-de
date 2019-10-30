---
title: ICorDebugProcess-Schnittstelle
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
ms.openlocfilehash: 393ac8c119f111b645e7ccdb6ea94efee7207fa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128792"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="932d4-102">ICorDebugProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="932d4-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="932d4-103">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="932d4-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="932d4-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="932d4-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="932d4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="932d4-105">Methods</span></span>  
  
|<span data-ttu-id="932d4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-106">Method</span></span>|<span data-ttu-id="932d4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="932d4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="932d4-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="932d4-109">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="932d4-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="932d4-110">EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="932d4-111">Aktiviert und deaktiviert das Senden von Protokollmeldungen an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="932d4-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="932d4-112">EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="932d4-113">Listet alle Anwendungs Domänen im Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="932d4-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="932d4-114">EnumerateObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="932d4-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="932d4-115">Not implemented.</span></span>|  
|[<span data-ttu-id="932d4-116">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="932d4-117">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="932d4-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="932d4-118">GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="932d4-119">Ruft die Betriebssystem-Thread-ID für den internen Hilfsthread des Debuggers ab.</span><span class="sxs-lookup"><span data-stu-id="932d4-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="932d4-120">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="932d4-121">Ruft die Betriebssystem-ID des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="932d4-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="932d4-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="932d4-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="932d4-123">Not implemented.</span></span>|  
|[<span data-ttu-id="932d4-124">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="932d4-125">Ruft die ICorDebugThread-Instanz ab, die über die angegebene Betriebssystem Thread-ID verfügt.</span><span class="sxs-lookup"><span data-stu-id="932d4-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="932d4-126">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="932d4-127">Ruft den Kontext für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="932d4-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="932d4-128">IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="932d4-129">Bestimmt, ob der Thread angehalten wurde, weil der Debugger den Prozess beendet hat.</span><span class="sxs-lookup"><span data-stu-id="932d4-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="932d4-130">IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="932d4-131">Bestimmt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="932d4-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="932d4-132">ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="932d4-133">Legt den Schweregrad des angegebenen Protokoll Schalters fest.</span><span class="sxs-lookup"><span data-stu-id="932d4-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="932d4-134">ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="932d4-135">Liest Arbeitsspeicher aus dem Prozess.</span><span class="sxs-lookup"><span data-stu-id="932d4-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="932d4-136">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="932d4-137">Legt den Kontext für den angegebenen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="932d4-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="932d4-138">ThreadForFiberCookie-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="932d4-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="932d4-139">Deprecated.</span></span>|  
|[<span data-ttu-id="932d4-140">WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="932d4-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="932d4-141">Schreibt Daten in einen Arbeitsspeicher Bereich des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="932d4-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="932d4-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="932d4-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="932d4-143">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="932d4-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="932d4-144">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="932d4-144">Requirements</span></span>  
 <span data-ttu-id="932d4-145">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="932d4-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="932d4-146">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="932d4-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="932d4-147">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="932d4-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="932d4-148">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="932d4-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932d4-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="932d4-149">See also</span></span>

- [<span data-ttu-id="932d4-150">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="932d4-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="932d4-151">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="932d4-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
