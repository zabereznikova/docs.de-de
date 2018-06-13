---
title: ICorDebugChain Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32889a8e8867fc42b48413463095dda423f26b85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409840"
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="6996c-102">ICorDebugChain Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="6996c-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="6996c-103">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="6996c-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6996c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6996c-104">Methods</span></span>  
  
|<span data-ttu-id="6996c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-105">Method</span></span>|<span data-ttu-id="6996c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6996c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6996c-107">EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="6996c-108">Ruft ein Enumerator, der alle verwalteten Stapelrahmen in der Kette enthält, beginnend mit den aktuellsten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="6996c-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="6996c-109">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="6996c-110">Ruft den aktiven (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="6996c-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="6996c-111">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="6996c-112">Ruft die Kette, die durch diese Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="6996c-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="6996c-113">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="6996c-114">Ruft die Kette, die diese Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6996c-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="6996c-115">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="6996c-116">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="6996c-116">Not implemented.</span></span>|  
|[<span data-ttu-id="6996c-117">GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="6996c-118">Ruft die nächste Kette von Frames für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="6996c-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="6996c-119">GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="6996c-120">Ruft die vorherige Kette von Frames für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="6996c-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="6996c-121">GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="6996c-122">Ruft den Grund für die Entstehung dieser Aufrufkette ab.</span><span class="sxs-lookup"><span data-stu-id="6996c-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="6996c-123">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="6996c-124">Ruft den Registersatz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="6996c-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="6996c-125">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="6996c-126">Ruft den Adressbereich des Stapelsegments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="6996c-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="6996c-127">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="6996c-128">Ruft den physischen Thread, den diese Aufrufkette wird Teil ab.</span><span class="sxs-lookup"><span data-stu-id="6996c-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="6996c-129">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="6996c-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="6996c-130">Ruft einen Wert, der angibt, ob diese Kette verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6996c-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6996c-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6996c-131">Remarks</span></span>  
 <span data-ttu-id="6996c-132">Stapelrahmen in einer Kette zusammenhängenden Stapelspeicherplatz belegen und Freigeben von dem gleichen Thread und Kontext.</span><span class="sxs-lookup"><span data-stu-id="6996c-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="6996c-133">Eine Kette kann entweder Codeketten verwalteten oder nicht verwalteten darstellen.</span><span class="sxs-lookup"><span data-stu-id="6996c-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="6996c-134">Ein leeres `ICorDebugChain` Instanz darstellt, eine Kette von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="6996c-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6996c-135">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6996c-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6996c-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6996c-136">Requirements</span></span>  
 <span data-ttu-id="6996c-137">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6996c-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6996c-138">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6996c-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6996c-139">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6996c-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6996c-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6996c-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6996c-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6996c-141">See Also</span></span>  
 [<span data-ttu-id="6996c-142">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6996c-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
