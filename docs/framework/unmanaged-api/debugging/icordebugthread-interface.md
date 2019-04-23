---
title: ICorDebugThread-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread
helpviewer_keywords:
- ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db322bbdc7293410968542d0d22c572edb87795a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184703"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="7d5c9-102">ICorDebugThread-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7d5c9-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="7d5c9-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-103">Represents a thread in a process.</span></span> <span data-ttu-id="7d5c9-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d5c9-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7d5c9-105">Methods</span></span>  
  
|<span data-ttu-id="7d5c9-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-106">Method</span></span>|<span data-ttu-id="7d5c9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d5c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d5c9-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="7d5c9-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-109">This method is not implemented.</span></span> <span data-ttu-id="7d5c9-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-110">Do not use it.</span></span>|  
|[<span data-ttu-id="7d5c9-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="7d5c9-112">Erstellt ein ICorDebugEval-Objekt, das funktioniert auf diesem `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="7d5c9-114">Erstellt ein ICorDebugStepper-Objekt, das des aktiven Frames in dieser schrittweise ermöglicht `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="7d5c9-116">Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem enthält `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="7d5c9-118">Ruft einen Schnittstellenzeiger auf die aktive ICorDebugChain dazu `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="7d5c9-120">Ruft einen Schnittstellenzeiger auf den aktiven ICorDebugFrame dazu `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="7d5c9-122">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in dem diese `ICorDebugThread` wird gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="7d5c9-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="7d5c9-124">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das eine derzeit von verwaltetem Code ausgelöste Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="7d5c9-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="7d5c9-126">Ruft einen CorDebugThreadState-Wert, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="7d5c9-128">Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="7d5c9-130">Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="7d5c9-132">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="7d5c9-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="7d5c9-134">Ruft einen Schnittstellenzeiger an den Prozess ab, der diese `ICorDebugThread` bildet einen Teil.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="7d5c9-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="7d5c9-136">Ruft einen Schnittstellenzeiger auf den zugeordneten Registersatz `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="7d5c9-138">Ruft eine bitweise Kombination von CorDebugUserState-Werte, die den aktuellen Zustand dieses beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="7d5c9-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="7d5c9-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="7d5c9-140">Legt eine bitweise Kombination von `CorDebugThreadState` Werte, die den Debugzustand dieses beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d5c9-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d5c9-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d5c9-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7d5c9-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d5c9-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7d5c9-143">Requirements</span></span>  
 <span data-ttu-id="7d5c9-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d5c9-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d5c9-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d5c9-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d5c9-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d5c9-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d5c9-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d5c9-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d5c9-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d5c9-148">See also</span></span>

- [<span data-ttu-id="7d5c9-149">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7d5c9-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
