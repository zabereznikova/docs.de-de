---
title: ICorDebugEnum Schnittstelle1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4659bbc9c2e3c71a6cf85e51a06bee4f789356b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422304"
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="a62e3-102">ICorDebugEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="a62e3-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="a62e3-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer Debuganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a62e3-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a62e3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a62e3-104">Methods</span></span>  
  
|<span data-ttu-id="a62e3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a62e3-105">Method</span></span>|<span data-ttu-id="a62e3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a62e3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a62e3-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="a62e3-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="a62e3-108">Erstellt eine Kopie dieser `ICorDebugEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a62e3-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="a62e3-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a62e3-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="a62e3-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a62e3-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="a62e3-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="a62e3-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="a62e3-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a62e3-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="a62e3-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="a62e3-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="a62e3-114">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="a62e3-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62e3-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a62e3-115">Remarks</span></span>  
 <span data-ttu-id="a62e3-116">Die folgenden Enumeratoren leiten sich von `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="a62e3-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="a62e3-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="a62e3-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="a62e3-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="a62e3-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="a62e3-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="a62e3-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="a62e3-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="a62e3-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="a62e3-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="a62e3-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="a62e3-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="a62e3-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="a62e3-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="a62e3-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="a62e3-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a62e3-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a62e3-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a62e3-139">Requirements</span></span>  
 <span data-ttu-id="a62e3-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a62e3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a62e3-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a62e3-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a62e3-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a62e3-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a62e3-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a62e3-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62e3-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a62e3-144">See Also</span></span>  
 [<span data-ttu-id="a62e3-145">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a62e3-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
