---
title: ICorDebugThread Schnittstelle1
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
ms.openlocfilehash: 404f1bdf5865733648084e34a558b7b20a59b3ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423077"
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="e2d4f-102">ICorDebugThread Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="e2d4f-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="e2d4f-103">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-103">Represents a thread in a process.</span></span> <span data-ttu-id="e2d4f-104">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2d4f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e2d4f-105">Methods</span></span>  
  
|<span data-ttu-id="e2d4f-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-106">Method</span></span>|<span data-ttu-id="e2d4f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2d4f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2d4f-108">ClearCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="e2d4f-109">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-109">This method is not implemented.</span></span> <span data-ttu-id="e2d4f-110">Verwenden Sie sie nicht.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-110">Do not use it.</span></span>|  
|[<span data-ttu-id="e2d4f-111">CreateEval-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="e2d4f-112">Erstellt ein ICorDebugEval-Objekt, das ausgeführt wird, für dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-113">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="e2d4f-114">Erstellt ein ICorDebugStepper-Objekt, die schrittweise Ausführung des aktiven Frames in diesem ermöglicht `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-115">EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="e2d4f-116">Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem enthält `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-117">GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="e2d4f-118">Ruft einen Schnittstellenzeiger auf die aktive ICorDebugChain für dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-119">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="e2d4f-120">Ruft einen Schnittstellenzeiger auf den aktiven ICorDebugFrame für dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-121">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="e2d4f-122">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in der diese `ICorDebugThread` wird gerade ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="e2d4f-123">GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="e2d4f-124">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das derzeit von verwaltetem Code ausgelöste eine Ausnahme darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="e2d4f-125">GetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="e2d4f-126">Ruft einen CorDebugThreadState-Wert, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-127">GetHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="e2d4f-128">Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-129">GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="e2d4f-130">Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils dieses `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-131">GetObject-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="e2d4f-132">Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="e2d4f-133">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="e2d4f-134">Ruft einen Schnittstellenzeiger an den Prozess ab, der diese `ICorDebugThread` bildet einen Teil.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="e2d4f-135">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="e2d4f-136">Ruft einen Schnittstellenzeiger auf den Registersatz zugeordnete `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-137">GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="e2d4f-138">Ruft eine bitweise Kombination von CorDebugUserState-Werte, die den aktuellen Zustand dieses beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="e2d4f-139">SetDebugState-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d4f-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="e2d4f-140">Legt eine bitweise Kombination von `CorDebugThreadState` Werte, die den Debugzustand beschreiben `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2d4f-141">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2d4f-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2d4f-142">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e2d4f-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d4f-143">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2d4f-143">Requirements</span></span>  
 <span data-ttu-id="e2d4f-144">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d4f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d4f-145">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2d4f-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2d4f-146">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d4f-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d4f-147">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d4f-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d4f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2d4f-148">See Also</span></span>  
 [<span data-ttu-id="e2d4f-149">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2d4f-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
