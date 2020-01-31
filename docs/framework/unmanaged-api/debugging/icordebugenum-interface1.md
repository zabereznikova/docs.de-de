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
ms.openlocfilehash: cc5598f9cbec4b97bb75f83fb18ccf8742904272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783008"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="b509d-102">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b509d-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="b509d-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer debugginganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b509d-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b509d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b509d-104">Methods</span></span>  
  
|<span data-ttu-id="b509d-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="b509d-105">Method</span></span>|<span data-ttu-id="b509d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b509d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b509d-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="b509d-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="b509d-108">Erstellt eine Kopie dieses `ICorDebugEnum` Objekts.</span><span class="sxs-lookup"><span data-stu-id="b509d-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="b509d-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="b509d-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="b509d-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="b509d-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="b509d-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="b509d-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="b509d-112">Verschiebt den Cursor an den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b509d-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="b509d-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="b509d-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="b509d-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="b509d-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b509d-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b509d-115">Remarks</span></span>  
 <span data-ttu-id="b509d-116">Die folgenden Enumeratoren werden von `ICorDebugEnum`abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="b509d-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="b509d-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="b509d-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="b509d-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="b509d-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="b509d-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="b509d-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="b509d-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="b509d-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="b509d-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="b509d-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="b509d-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="b509d-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="b509d-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="b509d-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="b509d-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="b509d-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="b509d-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="b509d-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="b509d-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="b509d-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="b509d-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="b509d-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="b509d-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="b509d-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b509d-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b509d-139">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b509d-139">Requirements</span></span>  
 <span data-ttu-id="b509d-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b509d-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b509d-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b509d-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b509d-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b509d-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b509d-143">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b509d-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b509d-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b509d-144">See also</span></span>

- [<span data-ttu-id="b509d-145">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b509d-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
