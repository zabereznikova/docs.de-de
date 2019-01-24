---
title: ICorDebugChain-Schnittstelle1
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
ms.openlocfilehash: e0bb716f1ad4087642a76dc84266ec6d3f46c1ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571203"
---
# <a name="icordebugchain-interface1"></a><span data-ttu-id="1feae-102">ICorDebugChain-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="1feae-102">ICorDebugChain Interface1</span></span>
<span data-ttu-id="1feae-103">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="1feae-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1feae-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1feae-104">Methods</span></span>  
  
|<span data-ttu-id="1feae-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-105">Method</span></span>|<span data-ttu-id="1feae-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1feae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1feae-107">EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="1feae-108">Ruft einen Enumerator, der alle verwalteten Stapelrahmen in der Kette, enthält der letzten Frame ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="1feae-109">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="1feae-110">Ruft das aktive (d. h. die letzte) Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="1feae-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="1feae-111">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="1feae-112">Ruft die Zertifikatskette, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1feae-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="1feae-113">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="1feae-114">Ruft die Zertifikatskette, die dieser Kette aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1feae-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="1feae-115">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="1feae-116">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1feae-116">Not implemented.</span></span>|  
|[<span data-ttu-id="1feae-117">GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="1feae-118">Ruft die nächste Kette von Frames für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="1feae-119">GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="1feae-120">Ruft die vorherige Kette von Frames für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="1feae-121">GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="1feae-122">Ruft den Grund für die Entstehung dieser Aufrufkette ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="1feae-123">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="1feae-124">Ruft ab, das Register, die für den aktiven Teil des dieser Kette festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1feae-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="1feae-125">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="1feae-126">Ruft den Adressbereich des Stack-Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="1feae-127">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="1feae-128">Ruft den physischen Thread, die, den diese Kette von Aufrufen ist, Teil ab.</span><span class="sxs-lookup"><span data-stu-id="1feae-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="1feae-129">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="1feae-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="1feae-130">Ruft einen Wert, der angibt, ob dieser Kette auf verwalteten Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1feae-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1feae-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1feae-131">Remarks</span></span>  
 <span data-ttu-id="1feae-132">Die Stapelrahmen in einer Kette zusammenhängenden Stapelspeicher belegt und den gleichen Thread und Kontext.</span><span class="sxs-lookup"><span data-stu-id="1feae-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="1feae-133">Eine Kette kann entweder Ketten verwaltetem oder nicht verwalteten Code darstellen.</span><span class="sxs-lookup"><span data-stu-id="1feae-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="1feae-134">Ein leeres `ICorDebugChain` Instanz darstellt, eine Kette von nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="1feae-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1feae-135">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1feae-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1feae-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1feae-136">Requirements</span></span>  
 <span data-ttu-id="1feae-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1feae-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1feae-138">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1feae-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1feae-139">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1feae-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1feae-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1feae-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1feae-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1feae-141">See also</span></span>
- [<span data-ttu-id="1feae-142">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1feae-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
