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
ms.openlocfilehash: b2429052173a187297b67c756213e5d27a79298b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792591"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="f76ef-102">ICorDebugProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f76ef-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="f76ef-103">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="f76ef-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="f76ef-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="f76ef-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f76ef-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f76ef-105">Methods</span></span>  
  
|<span data-ttu-id="f76ef-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-106">Method</span></span>|<span data-ttu-id="f76ef-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f76ef-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f76ef-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="f76ef-109">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="f76ef-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="f76ef-110">EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="f76ef-111">Aktiviert und deaktiviert das Senden von Protokollmeldungen an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="f76ef-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="f76ef-112">EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="f76ef-113">Listet alle Anwendungs Domänen im Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="f76ef-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="f76ef-114">EnumerateObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="f76ef-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f76ef-115">Not implemented.</span></span>|  
|[<span data-ttu-id="f76ef-116">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="f76ef-117">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f76ef-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="f76ef-118">GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="f76ef-119">Ruft die Betriebssystem-Thread-ID für den internen Hilfsthread des Debuggers ab.</span><span class="sxs-lookup"><span data-stu-id="f76ef-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="f76ef-120">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="f76ef-121">Ruft die Betriebssystem-ID des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="f76ef-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="f76ef-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="f76ef-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f76ef-123">Not implemented.</span></span>|  
|[<span data-ttu-id="f76ef-124">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="f76ef-125">Ruft die ICorDebugThread-Instanz ab, die über die angegebene Betriebssystem Thread-ID verfügt.</span><span class="sxs-lookup"><span data-stu-id="f76ef-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="f76ef-126">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="f76ef-127">Ruft den Kontext für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="f76ef-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="f76ef-128">IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="f76ef-129">Bestimmt, ob der Thread angehalten wurde, weil der Debugger den Prozess beendet hat.</span><span class="sxs-lookup"><span data-stu-id="f76ef-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="f76ef-130">IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="f76ef-131">Bestimmt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="f76ef-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="f76ef-132">ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="f76ef-133">Legt den Schweregrad des angegebenen Protokoll Schalters fest.</span><span class="sxs-lookup"><span data-stu-id="f76ef-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="f76ef-134">ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="f76ef-135">Liest Arbeitsspeicher aus dem Prozess.</span><span class="sxs-lookup"><span data-stu-id="f76ef-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="f76ef-136">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="f76ef-137">Legt den Kontext für den angegebenen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="f76ef-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="f76ef-138">ThreadForFiberCookie-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="f76ef-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f76ef-139">Deprecated.</span></span>|  
|[<span data-ttu-id="f76ef-140">WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f76ef-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="f76ef-141">Schreibt Daten in einen Arbeitsspeicher Bereich des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f76ef-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f76ef-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f76ef-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f76ef-143">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f76ef-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f76ef-144">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f76ef-144">Requirements</span></span>  
 <span data-ttu-id="f76ef-145">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f76ef-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f76ef-146">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f76ef-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f76ef-147">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f76ef-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f76ef-148">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f76ef-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f76ef-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f76ef-149">See also</span></span>

- [<span data-ttu-id="f76ef-150">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f76ef-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="f76ef-151">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f76ef-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
