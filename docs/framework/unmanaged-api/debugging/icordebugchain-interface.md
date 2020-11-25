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
ms.openlocfilehash: a0285970a8a42c078aa663579e1d5998d0d1c037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724454"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="a999a-102">ICorDebugChain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a999a-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="a999a-103">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="a999a-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a999a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a999a-104">Methods</span></span>  
  
|<span data-ttu-id="a999a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-105">Method</span></span>|<span data-ttu-id="a999a-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a999a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a999a-107">EnumerateFrames-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="a999a-108">Ruft einen Enumerator ab, der alle verwalteten Stapel Rahmen in der Kette enthält, beginnend mit dem letzten Frame.</span><span class="sxs-lookup"><span data-stu-id="a999a-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="a999a-109">GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="a999a-110">Ruft den aktiven Frame (d. h. den aktuellen) Frame in der Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="a999a-111">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="a999a-112">Ruft die Kette ab, die von dieser Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a999a-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="a999a-113">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="a999a-114">Ruft die Kette ab, die diese Kette aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="a999a-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="a999a-115">GetContext-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="a999a-116">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="a999a-116">Not implemented.</span></span>|  
|[<span data-ttu-id="a999a-117">GetNext-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="a999a-118">Ruft die nächste Rahmen Kette für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a999a-119">GetPrevious-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="a999a-120">Ruft die vorherige Rahmen Kette für den Thread ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="a999a-121">GetReason-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="a999a-122">Ruft den Grund für die Entstehung dieser aufrufenden Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="a999a-123">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="a999a-124">Ruft den Register Satz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="a999a-125">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="a999a-126">Ruft den Adressbereich des Stapel Segments für diese Kette ab.</span><span class="sxs-lookup"><span data-stu-id="a999a-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="a999a-127">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="a999a-128">Ruft den physischen Thread ab, zu dem diese rufkette gehört.</span><span class="sxs-lookup"><span data-stu-id="a999a-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="a999a-129">IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="a999a-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="a999a-130">Ruft einen Wert ab, der angibt, ob diese Kette verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a999a-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a999a-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a999a-131">Remarks</span></span>  

 <span data-ttu-id="a999a-132">Die Stapel Rahmen in einer Kette belegen zusammenhängenden Stapel Speicher und verwenden denselben Thread und Kontext.</span><span class="sxs-lookup"><span data-stu-id="a999a-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="a999a-133">Eine Kette kann entweder verwaltete oder nicht verwaltete Code Ketten darstellen.</span><span class="sxs-lookup"><span data-stu-id="a999a-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="a999a-134">Eine leere- `ICorDebugChain` Instanz stellt eine nicht verwaltete Code Kette dar.</span><span class="sxs-lookup"><span data-stu-id="a999a-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a999a-135">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a999a-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a999a-136">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a999a-136">Requirements</span></span>  

 <span data-ttu-id="a999a-137">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a999a-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a999a-138">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a999a-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a999a-139">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a999a-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a999a-140">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a999a-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a999a-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a999a-141">See also</span></span>

- [<span data-ttu-id="a999a-142">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a999a-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
