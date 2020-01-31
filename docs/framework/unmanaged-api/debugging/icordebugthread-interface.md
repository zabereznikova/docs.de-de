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
ms.openlocfilehash: b227b374021136e78f7f061d235eb18eca5b9515
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791472"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="8d0a8-102">ICorDebugThread-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d0a8-102">ICorDebugThread Interface</span></span>
<span data-ttu-id="8d0a8-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-103">Represents a thread in a process.</span></span> <span data-ttu-id="8d0a8-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d0a8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8d0a8-105">Methods</span></span>  
  
|<span data-ttu-id="8d0a8-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-106">Method</span></span>|<span data-ttu-id="8d0a8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d0a8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d0a8-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="8d0a8-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-109">This method is not implemented.</span></span> <span data-ttu-id="8d0a8-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-110">Do not use it.</span></span>|  
|[<span data-ttu-id="8d0a8-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="8d0a8-112">Erstellt ein ICorDebugEval-Objekt, das mit diesem `ICorDebugThread`arbeitet.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="8d0a8-114">Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem `ICorDebugThread`ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="8d0a8-116">Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem `ICorDebugThread`enthält.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="8d0a8-118">Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette in diesem `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="8d0a8-120">Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame auf diesem `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="8d0a8-122">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der dieser `ICorDebugThread` derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="8d0a8-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="8d0a8-124">Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="8d0a8-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="8d0a8-126">Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses `ICorDebugThread`beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="8d0a8-128">Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="8d0a8-130">Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses `ICorDebugThread`ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="8d0a8-132">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="8d0a8-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="8d0a8-134">Ruft einen Schnittstellen Zeiger auf den Prozess ab, dessen-`ICorDebugThread` ein Teil bildet.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="8d0a8-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="8d0a8-136">Ruft einen Schnittstellen Zeiger auf den diesem `ICorDebugThread`zugeordneten Register Satz ab.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="8d0a8-138">Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses `ICorDebugThread`beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="8d0a8-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="8d0a8-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="8d0a8-140">Legt eine bitweise Kombination von `CorDebugThreadState`-Werten fest, die den Debugzustand dieses `ICorDebugThread`beschreiben.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d0a8-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d0a8-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d0a8-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8d0a8-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d0a8-143">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d0a8-143">Requirements</span></span>  
 <span data-ttu-id="8d0a8-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d0a8-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d0a8-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d0a8-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d0a8-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d0a8-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d0a8-147">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d0a8-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0a8-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d0a8-148">See also</span></span>

- [<span data-ttu-id="8d0a8-149">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d0a8-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
