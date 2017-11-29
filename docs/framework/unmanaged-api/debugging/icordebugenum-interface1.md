---
title: ICorDebugEnum Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum
helpviewer_keywords: ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f6596918819294f0ab68735cec12f9eab8bf83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="5ee7d-102">ICorDebugEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="5ee7d-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="5ee7d-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer Debuganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5ee7d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5ee7d-104">Methods</span></span>  
  
|<span data-ttu-id="5ee7d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5ee7d-105">Method</span></span>|<span data-ttu-id="5ee7d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ee7d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ee7d-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee7d-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="5ee7d-108">Erstellt eine Kopie dieser `ICorDebugEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="5ee7d-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee7d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="5ee7d-110">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="5ee7d-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee7d-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="5ee7d-112">Verschiebt den Cursor auf den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="5ee7d-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee7d-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="5ee7d-114">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ee7d-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ee7d-115">Remarks</span></span>  
 <span data-ttu-id="5ee7d-116">Die folgenden Enumeratoren leiten sich von `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="5ee7d-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="5ee7d-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="5ee7d-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="5ee7d-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="5ee7d-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="5ee7d-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="5ee7d-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="5ee7d-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="5ee7d-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="5ee7d-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="5ee7d-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="5ee7d-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="5ee7d-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="5ee7d-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="5ee7d-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="5ee7d-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5ee7d-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee7d-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ee7d-139">Requirements</span></span>  
 <span data-ttu-id="5ee7d-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee7d-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee7d-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ee7d-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ee7d-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ee7d-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ee7d-143">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee7d-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee7d-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ee7d-144">See Also</span></span>  
 [<span data-ttu-id="5ee7d-145">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ee7d-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
