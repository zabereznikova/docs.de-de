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
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694918"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="7e9c0-102">ICorDebugProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e9c0-102">ICorDebugProcess Interface</span></span>

<span data-ttu-id="7e9c0-103">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="7e9c0-104">Bei dieser Schnittstelle handelt es sich um eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e9c0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7e9c0-105">Methods</span></span>  
  
|<span data-ttu-id="7e9c0-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-106">Method</span></span>|<span data-ttu-id="7e9c0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7e9c0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e9c0-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-108">ClearCurrentException Method</span></span>](icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="7e9c0-109">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="7e9c0-110">EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-110">EnableLogMessages Method</span></span>](icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="7e9c0-111">Aktiviert und deaktiviert das Senden von Protokollmeldungen an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="7e9c0-112">EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-112">EnumerateAppDomains Method</span></span>](icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="7e9c0-113">Listet alle Anwendungs Domänen im Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="7e9c0-114">EnumerateObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-114">EnumerateObjects Method</span></span>](icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="7e9c0-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-115">Not implemented.</span></span>|  
|[<span data-ttu-id="7e9c0-116">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-116">GetHandle Method</span></span>](icordebugprocess-gethandle-method.md)|<span data-ttu-id="7e9c0-117">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="7e9c0-118">GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-118">GetHelperThreadID Method</span></span>](icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="7e9c0-119">Ruft die Betriebssystem-Thread-ID für den internen Hilfsthread des Debuggers ab.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="7e9c0-120">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-120">GetID Method</span></span>](icordebugprocess-getid-method.md)|<span data-ttu-id="7e9c0-121">Ruft die Betriebssystem-ID des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="7e9c0-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-122">GetObject Method</span></span>](icordebugprocess-getobject-method.md)|<span data-ttu-id="7e9c0-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-123">Not implemented.</span></span>|  
|[<span data-ttu-id="7e9c0-124">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-124">GetThread Method</span></span>](icordebugprocess-getthread-method.md)|<span data-ttu-id="7e9c0-125">Ruft die ICorDebugThread-Instanz ab, die über die angegebene Betriebssystem Thread-ID verfügt.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="7e9c0-126">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-126">GetThreadContext Method</span></span>](icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="7e9c0-127">Ruft den Kontext für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="7e9c0-128">IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-128">IsOSSuspended Method</span></span>](icordebugprocess-isossuspended-method.md)|<span data-ttu-id="7e9c0-129">Bestimmt, ob der Thread angehalten wurde, weil der Debugger den Prozess beendet hat.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="7e9c0-130">IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-130">IsTransitionStub Method</span></span>](icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="7e9c0-131">Bestimmt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="7e9c0-132">ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-132">ModifyLogSwitch Method</span></span>](icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="7e9c0-133">Legt den Schweregrad des angegebenen Protokoll Schalters fest.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="7e9c0-134">ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-134">ReadMemory Method</span></span>](icordebugprocess-readmemory-method.md)|<span data-ttu-id="7e9c0-135">Liest Arbeitsspeicher aus dem Prozess.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="7e9c0-136">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-136">SetThreadContext Method</span></span>](icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="7e9c0-137">Legt den Kontext für den angegebenen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="7e9c0-138">ThreadForFiberCookie-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-138">ThreadForFiberCookie Method</span></span>](icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="7e9c0-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-139">Deprecated.</span></span>|  
|[<span data-ttu-id="7e9c0-140">WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="7e9c0-140">WriteMemory Method</span></span>](icordebugprocess-writememory-method.md)|<span data-ttu-id="7e9c0-141">Schreibt Daten in einen Arbeitsspeicher Bereich des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e9c0-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e9c0-142">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e9c0-143">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7e9c0-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e9c0-144">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7e9c0-144">Requirements</span></span>  

 <span data-ttu-id="7e9c0-145">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e9c0-145">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e9c0-146">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e9c0-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e9c0-147">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e9c0-147">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e9c0-148">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e9c0-148">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9c0-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e9c0-149">See also</span></span>

- [<span data-ttu-id="7e9c0-150">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e9c0-150">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="7e9c0-151">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7e9c0-151">Debugging Interfaces</span></span>](debugging-interfaces.md)
