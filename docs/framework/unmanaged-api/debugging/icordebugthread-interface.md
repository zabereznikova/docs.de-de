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
ms.openlocfilehash: c7333f4210d0a2ec4ff71a0fac0ea00068fecc57
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133494"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="dbe18-102">ICorDebugThread-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbe18-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="dbe18-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="dbe18-103">Represents a thread in a process.</span></span> <span data-ttu-id="dbe18-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="dbe18-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbe18-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dbe18-105">Methods</span></span>  
  
|<span data-ttu-id="dbe18-106">Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-106">Method</span></span>|<span data-ttu-id="dbe18-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbe18-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbe18-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="dbe18-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="dbe18-109">This method is not implemented.</span></span> <span data-ttu-id="dbe18-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="dbe18-110">Do not use it.</span></span>|  
|[<span data-ttu-id="dbe18-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="dbe18-112">Erstellt ein ICorDebugEval-Objekt, das mit diesem `ICorDebugThread`arbeitet.</span><span class="sxs-lookup"><span data-stu-id="dbe18-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="dbe18-114">Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem `ICorDebugThread`ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="dbe18-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="dbe18-116">Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem `ICorDebugThread`enthält.</span><span class="sxs-lookup"><span data-stu-id="dbe18-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="dbe18-118">Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette in diesem `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="dbe18-120">Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame auf diesem `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="dbe18-122">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der dieser `ICorDebugThread` derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dbe18-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="dbe18-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="dbe18-124">Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="dbe18-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="dbe18-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="dbe18-126">Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses `ICorDebugThread`beschreibt.</span><span class="sxs-lookup"><span data-stu-id="dbe18-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="dbe18-128">Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="dbe18-130">Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="dbe18-132">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="dbe18-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="dbe18-134">Ruft einen Schnittstellen Zeiger auf den Prozess ab, dessen-`ICorDebugThread` ein Teil bildet.</span><span class="sxs-lookup"><span data-stu-id="dbe18-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="dbe18-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="dbe18-136">Ruft einen Schnittstellen Zeiger auf den diesem `ICorDebugThread`zugeordneten Register Satz ab.</span><span class="sxs-lookup"><span data-stu-id="dbe18-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="dbe18-138">Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses `ICorDebugThread`beschreiben.</span><span class="sxs-lookup"><span data-stu-id="dbe18-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="dbe18-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="dbe18-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="dbe18-140">Legt eine bitweise Kombination von `CorDebugThreadState`-Werten fest, die den Debugzustand dieses `ICorDebugThread`beschreiben.</span><span class="sxs-lookup"><span data-stu-id="dbe18-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe18-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbe18-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dbe18-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dbe18-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe18-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbe18-143">Requirements</span></span>  
 <span data-ttu-id="dbe18-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe18-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe18-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbe18-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbe18-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe18-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe18-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe18-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe18-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbe18-148">See also</span></span>

- [<span data-ttu-id="dbe18-149">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dbe18-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
