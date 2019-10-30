---
title: ICorDebugEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085263"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="527b0-102">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="527b0-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="527b0-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer debugginganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="527b0-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="527b0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="527b0-104">Methods</span></span>  
  
|<span data-ttu-id="527b0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="527b0-105">Method</span></span>|<span data-ttu-id="527b0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="527b0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="527b0-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="527b0-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="527b0-108">Erstellt eine Kopie dieses `ICorDebugEnum` Objekts.</span><span class="sxs-lookup"><span data-stu-id="527b0-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="527b0-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="527b0-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="527b0-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="527b0-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="527b0-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="527b0-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="527b0-112">Verschiebt den Cursor an den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="527b0-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="527b0-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="527b0-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="527b0-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="527b0-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="527b0-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="527b0-115">Remarks</span></span>  
 <span data-ttu-id="527b0-116">Die folgenden Enumeratoren werden von `ICorDebugEnum`abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="527b0-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="527b0-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="527b0-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="527b0-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="527b0-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="527b0-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="527b0-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="527b0-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="527b0-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="527b0-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="527b0-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="527b0-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="527b0-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="527b0-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="527b0-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="527b0-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="527b0-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="527b0-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="527b0-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="527b0-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="527b0-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="527b0-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="527b0-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="527b0-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="527b0-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="527b0-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="527b0-139">Requirements</span></span>  
 <span data-ttu-id="527b0-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="527b0-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="527b0-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="527b0-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="527b0-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="527b0-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="527b0-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="527b0-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="527b0-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="527b0-144">See also</span></span>

- [<span data-ttu-id="527b0-145">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="527b0-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
