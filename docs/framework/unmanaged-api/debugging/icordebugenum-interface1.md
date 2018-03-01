---
title: ICorDebugEnum Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 751cca87962473501ef29a4deb99d9d24be33396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="5e85b-102">ICorDebugEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="5e85b-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="5e85b-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer Debuganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e85b-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e85b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5e85b-104">Methods</span></span>  
  
|<span data-ttu-id="5e85b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5e85b-105">Method</span></span>|<span data-ttu-id="5e85b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e85b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e85b-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="5e85b-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="5e85b-108">Erstellt eine Kopie dieser `ICorDebugEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5e85b-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="5e85b-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5e85b-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="5e85b-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5e85b-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="5e85b-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="5e85b-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="5e85b-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5e85b-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="5e85b-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="5e85b-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="5e85b-114">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="5e85b-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e85b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e85b-115">Remarks</span></span>  
 <span data-ttu-id="5e85b-116">Die folgenden Enumeratoren leiten sich von `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="5e85b-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="5e85b-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="5e85b-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="5e85b-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="5e85b-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="5e85b-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="5e85b-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="5e85b-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="5e85b-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="5e85b-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="5e85b-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="5e85b-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="5e85b-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="5e85b-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="5e85b-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="5e85b-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5e85b-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e85b-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e85b-139">Requirements</span></span>  
 <span data-ttu-id="5e85b-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e85b-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e85b-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e85b-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e85b-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e85b-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e85b-143">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e85b-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e85b-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e85b-144">See Also</span></span>  
 [<span data-ttu-id="5e85b-145">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5e85b-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
