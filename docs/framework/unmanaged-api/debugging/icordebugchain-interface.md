---
title: ICorDebugChain Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain
helpviewer_keywords: ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f964b5390e601b518acad44dd6fd170399ff0af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="5bf15-102">ICorDebugChain Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="5bf15-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="5bf15-103">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="5bf15-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bf15-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5bf15-104">Methods</span></span>  
  
|<span data-ttu-id="5bf15-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-105">Method</span></span>|<span data-ttu-id="5bf15-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5bf15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bf15-107">EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="5bf15-108">Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="5bf15-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="5bf15-109">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="5bf15-110">Ruft den aktiven (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="5bf15-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="5bf15-111">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="5bf15-112">Ruft die Kette, die durch diese Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="5bf15-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="5bf15-113">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="5bf15-114">Ruft die Kette, die diese Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5bf15-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="5bf15-115">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="5bf15-116">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="5bf15-116">Not implemented.</span></span>|  
|[<span data-ttu-id="5bf15-117">GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="5bf15-118">Ruft die nächste Kette von Frames für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="5bf15-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="5bf15-119">GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="5bf15-120">Ruft die vorherige Kette von Frames für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="5bf15-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="5bf15-121">GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="5bf15-122">Ruft den Grund für die Entstehung dieser Aufrufkette ab.</span><span class="sxs-lookup"><span data-stu-id="5bf15-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="5bf15-123">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="5bf15-124">Ruft den Registersatz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="5bf15-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="5bf15-125">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="5bf15-126">Ruft den Adressbereich des Stapelsegments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="5bf15-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="5bf15-127">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="5bf15-128">Ruft den physischen Thread, den diese Aufrufkette wird Teil ab.</span><span class="sxs-lookup"><span data-stu-id="5bf15-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="5bf15-129">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="5bf15-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="5bf15-130">Ruft einen Wert, der angibt, ob diese Kette verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5bf15-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bf15-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bf15-131">Remarks</span></span>  
 <span data-ttu-id="5bf15-132">Stapelrahmen in einer Kette zusammenhängenden Stapelspeicherplatz belegen und Freigeben von dem gleichen Thread und Kontext.</span><span class="sxs-lookup"><span data-stu-id="5bf15-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="5bf15-133">Eine Kette kann entweder Codeketten verwalteten oder nicht verwalteten darstellen.</span><span class="sxs-lookup"><span data-stu-id="5bf15-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="5bf15-134">Ein leeres `ICorDebugChain` Instanz darstellt, eine Kette von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="5bf15-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bf15-135">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5bf15-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf15-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bf15-136">Requirements</span></span>  
 <span data-ttu-id="5bf15-137">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bf15-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf15-138">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bf15-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bf15-139">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bf15-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bf15-140">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf15-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf15-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bf15-141">See Also</span></span>  
 [<span data-ttu-id="5bf15-142">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5bf15-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
