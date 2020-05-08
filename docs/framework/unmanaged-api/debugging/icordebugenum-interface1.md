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
ms.openlocfilehash: 7575be3f5074243b251c80b8dd5bdbb12e5d50fd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976325"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="ab259-102">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab259-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="ab259-103">Dient als abstrakte Basisschnittstelle für die Enumeratoren, die von einer debugginganwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab259-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab259-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ab259-104">Methods</span></span>  
  
|<span data-ttu-id="ab259-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ab259-105">Method</span></span>|<span data-ttu-id="ab259-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ab259-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab259-107">Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="ab259-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="ab259-108">Erstellt eine Kopie dieses `ICorDebugEnum`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="ab259-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="ab259-109">GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="ab259-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="ab259-110">Ruft die Anzahl der Elemente in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="ab259-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="ab259-111">Reset-Methode</span><span class="sxs-lookup"><span data-stu-id="ab259-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="ab259-112">Verschiebt den Cursor an den Anfang der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ab259-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="ab259-113">Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="ab259-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="ab259-114">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="ab259-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab259-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab259-115">Remarks</span></span>  
 <span data-ttu-id="ab259-116">Die folgenden Enumeratoren werden von `ICorDebugEnum`abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="ab259-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="ab259-117">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="ab259-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="ab259-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="ab259-120">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="ab259-121">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="ab259-122">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="ab259-123">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="ab259-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="ab259-125">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="ab259-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="ab259-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="ab259-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="ab259-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="ab259-130">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="ab259-131">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="ab259-132">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="ab259-133">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="ab259-134">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="ab259-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="ab259-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="ab259-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="ab259-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="ab259-138">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ab259-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab259-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab259-139">Requirements</span></span>  
 <span data-ttu-id="ab259-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab259-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab259-141">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab259-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab259-142">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab259-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab259-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab259-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab259-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab259-144">See also</span></span>

- [<span data-ttu-id="ab259-145">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ab259-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
