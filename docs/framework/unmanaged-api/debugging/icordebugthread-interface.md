---
title: ICorDebugThread-Schnittstelle1
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
ms.openlocfilehash: be30e91e017390befd26ada37daa0fc902bdaee2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617498"
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="90f24-102">ICorDebugThread-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="90f24-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="90f24-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="90f24-103">Represents a thread in a process.</span></span> <span data-ttu-id="90f24-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="90f24-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90f24-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="90f24-105">Methods</span></span>  
  
|<span data-ttu-id="90f24-106">Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-106">Method</span></span>|<span data-ttu-id="90f24-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90f24-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90f24-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="90f24-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="90f24-109">This method is not implemented.</span></span> <span data-ttu-id="90f24-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="90f24-110">Do not use it.</span></span>|  
|[<span data-ttu-id="90f24-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="90f24-112">Erstellt ein ICorDebugEval-Objekt, das funktioniert auf diesem `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="90f24-114">Erstellt ein ICorDebugStepper-Objekt, das des aktiven Frames in dieser schrittweise ermöglicht `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="90f24-116">Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem enthält `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="90f24-118">Ruft einen Schnittstellenzeiger auf die aktive ICorDebugChain dazu `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="90f24-120">Ruft einen Schnittstellenzeiger auf den aktiven ICorDebugFrame dazu `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="90f24-122">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in dem diese `ICorDebugThread` wird gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="90f24-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="90f24-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="90f24-124">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das eine derzeit von verwaltetem Code ausgelöste Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="90f24-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="90f24-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="90f24-126">Ruft einen CorDebugThreadState-Wert, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="90f24-128">Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="90f24-130">Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="90f24-132">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="90f24-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="90f24-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="90f24-134">Ruft einen Schnittstellenzeiger an den Prozess ab, der diese `ICorDebugThread` bildet einen Teil.</span><span class="sxs-lookup"><span data-stu-id="90f24-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="90f24-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="90f24-136">Ruft einen Schnittstellenzeiger auf den zugeordneten Registersatz `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="90f24-138">Ruft eine bitweise Kombination von CorDebugUserState-Werte, die den aktuellen Zustand dieses beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="90f24-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="90f24-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="90f24-140">Legt eine bitweise Kombination von `CorDebugThreadState` Werte, die den Debugzustand dieses beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="90f24-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90f24-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90f24-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90f24-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="90f24-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90f24-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90f24-143">Requirements</span></span>  
 <span data-ttu-id="90f24-144">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90f24-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90f24-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90f24-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90f24-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90f24-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90f24-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90f24-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90f24-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90f24-148">See also</span></span>
- [<span data-ttu-id="90f24-149">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="90f24-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
