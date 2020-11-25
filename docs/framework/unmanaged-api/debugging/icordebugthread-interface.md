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
ms.openlocfilehash: 5165ef081aad849c11747807d8cc76b2df0a6c74
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729316"
---
# <a name="icordebugthread-interface"></a><span data-ttu-id="967e2-102">ICorDebugThread-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="967e2-102">ICorDebugThread Interface</span></span>

<span data-ttu-id="967e2-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="967e2-103">Represents a thread in a process.</span></span> <span data-ttu-id="967e2-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="967e2-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="967e2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="967e2-105">Methods</span></span>  
  
|<span data-ttu-id="967e2-106">Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-106">Method</span></span>|<span data-ttu-id="967e2-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="967e2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="967e2-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-108">ClearCurrentException Method</span></span>](icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="967e2-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="967e2-109">This method is not implemented.</span></span> <span data-ttu-id="967e2-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="967e2-110">Do not use it.</span></span>|  
|[<span data-ttu-id="967e2-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-111">CreateEval Method</span></span>](icordebugthread-createeval-method.md)|<span data-ttu-id="967e2-112">Erstellt ein ICorDebugEval-Objekt, das auf diesem ausgeführt wird `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-113">CreateStepper Method</span></span>](icordebugthread-createstepper-method.md)|<span data-ttu-id="967e2-114">Erstellt ein ICorDebug-Stepper-Objekt, das das schrittweise durchlaufen des aktiven Frames in diesem ermöglicht `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-115">EnumerateChains Method</span></span>](icordebugthread-enumeratechains-method.md)|<span data-ttu-id="967e2-116">Ruft einen Schnittstellen Zeiger auf einen ICorDebug-chainenum-Enumerator ab, der alle Stapel Ketten in diesem enthält `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-117">GetActiveChain Method</span></span>](icordebugthread-getactivechain-method.md)|<span data-ttu-id="967e2-118">Ruft einen Schnittstellen Zeiger auf die aktive ICorDebug-Kette für dieses ab `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-119">GetActiveFrame Method</span></span>](icordebugthread-getactiveframe-method.md)|<span data-ttu-id="967e2-120">Ruft einen Schnittstellen Zeiger auf den aktiven ICorDebug-Frame für dieses ab `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-121">GetAppDomain Method</span></span>](icordebugthread-getappdomain-method.md)|<span data-ttu-id="967e2-122">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, in der diese `ICorDebugThread` gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="967e2-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="967e2-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-123">GetCurrentException Method</span></span>](icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="967e2-124">Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="967e2-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="967e2-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-125">GetDebugState Method</span></span>](icordebugthread-getdebugstate-method.md)|<span data-ttu-id="967e2-126">Ruft einen CorDebugThreadState-Wert ab, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-127">GetHandle Method</span></span>](icordebugthread-gethandle-method.md)|<span data-ttu-id="967e2-128">Ruft das aktuelle Handle für den aktiven Teil dieses ab `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-129">GetID Method</span></span>](icordebugthread-getid-method.md)|<span data-ttu-id="967e2-130">Ruft den aktuellen Betriebssystem Bezeichner des aktiven Teils dieses ab `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-131">GetObject Method</span></span>](icordebugthread-getobject-method.md)|<span data-ttu-id="967e2-132">Ruft einen Schnittstellen Zeiger auf den Common Language Runtime (CLR)-Thread ab.</span><span class="sxs-lookup"><span data-stu-id="967e2-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="967e2-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-133">GetProcess Method</span></span>](icordebugthread-getprocess-method.md)|<span data-ttu-id="967e2-134">Ruft einen Schnittstellen Zeiger auf den Prozess ab, zu dem dieses-Element `ICorDebugThread` gehört.</span><span class="sxs-lookup"><span data-stu-id="967e2-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="967e2-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-135">GetRegisterSet Method</span></span>](icordebugthread-getregisterset-method.md)|<span data-ttu-id="967e2-136">Ruft einen Schnittstellen Zeiger auf den Register Satz ab, der diesem zugeordnet ist `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-137">GetUserState Method</span></span>](icordebugthread-getuserstate-method.md)|<span data-ttu-id="967e2-138">Ruft eine bitweise Kombination von CorDebugUserState-Werten ab, die den aktuellen Zustand dieses beschreiben `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="967e2-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="967e2-139">SetDebugState Method</span></span>](icordebugthread-setdebugstate-method.md)|<span data-ttu-id="967e2-140">Legt eine bitweise Kombination von- `CorDebugThreadState` Werten fest, die den Debugzustand dieses beschreiben `ICorDebugThread` .</span><span class="sxs-lookup"><span data-stu-id="967e2-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="967e2-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="967e2-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="967e2-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="967e2-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="967e2-143">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="967e2-143">Requirements</span></span>  

 <span data-ttu-id="967e2-144">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="967e2-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="967e2-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="967e2-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="967e2-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="967e2-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="967e2-147">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="967e2-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="967e2-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="967e2-148">See also</span></span>

- [<span data-ttu-id="967e2-149">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="967e2-149">Debugging Interfaces</span></span>](debugging-interfaces.md)
