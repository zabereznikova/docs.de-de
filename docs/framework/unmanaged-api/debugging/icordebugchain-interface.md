---
title: ICorDebugChain-Schnittstelle
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
ms.openlocfilehash: 93ada40bd88e53cd06f5e8d8136b2d527d7741e6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969306"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="a8546-102">ICorDebugChain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a8546-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="a8546-103">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="a8546-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8546-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a8546-104">Methods</span></span>  
  
|<span data-ttu-id="a8546-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-105">Method</span></span>|<span data-ttu-id="a8546-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8546-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8546-107">EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="a8546-108">Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.</span><span class="sxs-lookup"><span data-stu-id="a8546-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="a8546-109">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="a8546-110">Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="a8546-111">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="a8546-112">Ruft die Kette ab, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a8546-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="a8546-113">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="a8546-114">Ruft die Kette ab, die diese Kette aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="a8546-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="a8546-115">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="a8546-116">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a8546-116">Not implemented.</span></span>|  
|[<span data-ttu-id="a8546-117">GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="a8546-118">Ruft die nächste Rahmen Kette für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a8546-119">GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="a8546-120">Ruft die vorherige Rahmen Kette für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a8546-121">GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="a8546-122">Ruft den Grund für die Entstehung dieser aufrufenden Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="a8546-123">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="a8546-124">Ruft den Register Satz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="a8546-125">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="a8546-126">Ruft den Adressbereich des Stapel Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a8546-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="a8546-127">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="a8546-128">Ruft den physischen Thread ab, zu dem diese rufkette gehört.</span><span class="sxs-lookup"><span data-stu-id="a8546-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="a8546-129">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="a8546-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="a8546-130">Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a8546-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8546-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8546-131">Remarks</span></span>  
 <span data-ttu-id="a8546-132">Die Stapel Rahmen in einer Kette belegen zusammenhängenden Stapel Speicher und verwenden denselben Thread und Kontext.</span><span class="sxs-lookup"><span data-stu-id="a8546-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="a8546-133">Eine Kette kann entweder verwaltete oder nicht verwaltete Code Ketten darstellen.</span><span class="sxs-lookup"><span data-stu-id="a8546-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="a8546-134">Eine leere `ICorDebugChain` -Instanz stellt eine nicht verwaltete Code Kette dar.</span><span class="sxs-lookup"><span data-stu-id="a8546-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8546-135">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a8546-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8546-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8546-136">Requirements</span></span>  
 <span data-ttu-id="a8546-137">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8546-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8546-138">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="a8546-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8546-139">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8546-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8546-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8546-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8546-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8546-141">See also</span></span>

- [<span data-ttu-id="a8546-142">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a8546-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
