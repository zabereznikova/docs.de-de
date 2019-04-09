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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216794"
---
# <a name="icordebugprocess-interface"></a><span data-ttu-id="f8434-102">ICorDebugProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8434-102">ICorDebugProcess Interface</span></span>
<span data-ttu-id="f8434-103">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="f8434-103">Represents a process that is executing managed code.</span></span> <span data-ttu-id="f8434-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugController.</span><span class="sxs-lookup"><span data-stu-id="f8434-104">This interface is a subclass of ICorDebugController.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8434-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8434-105">Methods</span></span>  
  
|<span data-ttu-id="f8434-106">Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-106">Method</span></span>|<span data-ttu-id="f8434-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8434-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8434-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|<span data-ttu-id="f8434-109">Löscht die aktuelle nicht verwaltete Ausnahme für den angegebenen Thread.</span><span class="sxs-lookup"><span data-stu-id="f8434-109">Clears the current unmanaged exception on the given thread.</span></span>|  
|[<span data-ttu-id="f8434-110">EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-110">EnableLogMessages Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|<span data-ttu-id="f8434-111">Aktiviert und deaktiviert das Senden von Meldungen an dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="f8434-111">Enables and disables the sending of log messages to the debugger.</span></span>|  
|[<span data-ttu-id="f8434-112">EnumerateAppDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-112">EnumerateAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|<span data-ttu-id="f8434-113">Listet alle Anwendungsdomänen im Prozess.</span><span class="sxs-lookup"><span data-stu-id="f8434-113">Enumerates all of the application domains in the process.</span></span>|  
|[<span data-ttu-id="f8434-114">EnumerateObjects-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-114">EnumerateObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|<span data-ttu-id="f8434-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8434-115">Not implemented.</span></span>|  
|[<span data-ttu-id="f8434-116">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-116">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|<span data-ttu-id="f8434-117">Ruft ein Handle für den Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f8434-117">Gets a handle to the process.</span></span>|  
|[<span data-ttu-id="f8434-118">GetHelperThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-118">GetHelperThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|<span data-ttu-id="f8434-119">Ruft das Betriebssystem (OS)-Thread-ID für interne Hilfsthreads des Debuggers ab.</span><span class="sxs-lookup"><span data-stu-id="f8434-119">Gets the operating system (OS) thread ID for the debugger's internal helper thread.</span></span>|  
|[<span data-ttu-id="f8434-120">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-120">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|<span data-ttu-id="f8434-121">Ruft das Betriebssystem (OS)-ID des Prozesses ab.</span><span class="sxs-lookup"><span data-stu-id="f8434-121">Gets the operating system (OS) ID of the process.</span></span>|  
|[<span data-ttu-id="f8434-122">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-122">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|<span data-ttu-id="f8434-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="f8434-123">Not implemented.</span></span>|  
|[<span data-ttu-id="f8434-124">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-124">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|<span data-ttu-id="f8434-125">Ruft die ICorDebugThread-Instanz, die den angegebene BS-Thread-ID.</span><span class="sxs-lookup"><span data-stu-id="f8434-125">Gets the ICorDebugThread instance that has the specified OS thread ID.</span></span>|  
|[<span data-ttu-id="f8434-126">GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-126">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|<span data-ttu-id="f8434-127">Ruft den Kontext für den angegebenen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="f8434-127">Gets the context for the given thread.</span></span>|  
|[<span data-ttu-id="f8434-128">IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-128">IsOSSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|<span data-ttu-id="f8434-129">Bestimmt, ob der Thread durch den Debugger Beenden des Prozesses angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="f8434-129">Determines whether the thread has been suspended as a result of the debugger stopping the process.</span></span>|  
|[<span data-ttu-id="f8434-130">IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-130">IsTransitionStub Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|<span data-ttu-id="f8434-131">Bestimmt, ob eine Adresse in einen Stub, der einen Übergang in verwalteten Code bewirkt.</span><span class="sxs-lookup"><span data-stu-id="f8434-131">Determines whether an address is inside a stub that will cause a transition to managed code.</span></span>|  
|[<span data-ttu-id="f8434-132">ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-132">ModifyLogSwitch Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|<span data-ttu-id="f8434-133">Legt den Schweregrad der angegebenen Log-Schalter fest.</span><span class="sxs-lookup"><span data-stu-id="f8434-133">Sets the severity level of the specified log switch.</span></span>|  
|[<span data-ttu-id="f8434-134">ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-134">ReadMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|<span data-ttu-id="f8434-135">Liest Arbeitsspeicher vom Prozess an.</span><span class="sxs-lookup"><span data-stu-id="f8434-135">Reads memory from the process.</span></span>|  
|[<span data-ttu-id="f8434-136">SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-136">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|<span data-ttu-id="f8434-137">Legt den Kontext für den angegebenen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="f8434-137">Sets the context for the given thread.</span></span>|  
|[<span data-ttu-id="f8434-138">ThreadForFiberCookie-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-138">ThreadForFiberCookie Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|<span data-ttu-id="f8434-139">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="f8434-139">Deprecated.</span></span>|  
|[<span data-ttu-id="f8434-140">WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f8434-140">WriteMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|<span data-ttu-id="f8434-141">Schreibt Daten in einem Bereich des Arbeitsspeichers im Prozess.</span><span class="sxs-lookup"><span data-stu-id="f8434-141">Writes data to an area of memory in the process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8434-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8434-142">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8434-143">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f8434-143">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8434-144">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8434-144">Requirements</span></span>  
 <span data-ttu-id="f8434-145">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8434-145">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8434-146">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8434-146">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8434-147">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8434-147">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f8434-148">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f8434-148">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f8434-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8434-149">See also</span></span>

- [<span data-ttu-id="f8434-150">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8434-150">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="f8434-151">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8434-151">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
