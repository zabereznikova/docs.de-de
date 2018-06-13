---
title: ICorDebugProcess5::EnumerateHandles-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f2177702c6c5999033d0852a932e52c0725fb8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422658"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="60bd3-102">ICorDebugProcess5::EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="60bd3-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="60bd3-103">Ruft einen Enumerator für die Objekt-Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="60bd3-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60bd3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60bd3-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60bd3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60bd3-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="60bd3-106">[in] Eine bitweise Kombination von [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Werte, der angibt, den Typ des Handles in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60bd3-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="60bd3-107">[out] Ein Zeiger auf die Adresse des ein [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) also einen Enumerator für die Objekte, die Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="60bd3-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60bd3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60bd3-108">Remarks</span></span>  
 <span data-ttu-id="60bd3-109">`EnumerateHandles` ist eine Hilfsfunktion, die Überprüfung der Handletabelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="60bd3-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="60bd3-110">Ähnelt der [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode, außer dass anstatt Auffüllen einer [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) Auflistung mit allen Objekten, die Garbage Collection übergeben, werden sie enthält nur Objekte, die Handles aus der Handletabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="60bd3-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="60bd3-111">Die `types` Parameter gibt die Handletypen in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="60bd3-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="60bd3-112">`types` kann eine der folgenden drei Elemente von der [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) Enumeration:</span><span class="sxs-lookup"><span data-stu-id="60bd3-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="60bd3-113">`CorHandleStrongOnly` (Handles zum starken Verweise nur).</span><span class="sxs-lookup"><span data-stu-id="60bd3-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="60bd3-114">`CorHandleWeakOnly` (um nur schwache Verweise Handles).</span><span class="sxs-lookup"><span data-stu-id="60bd3-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="60bd3-115">`CorHandleAll` (alle Handles).</span><span class="sxs-lookup"><span data-stu-id="60bd3-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60bd3-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60bd3-116">Requirements</span></span>  
 <span data-ttu-id="60bd3-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60bd3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60bd3-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60bd3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60bd3-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60bd3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60bd3-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60bd3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60bd3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60bd3-121">See Also</span></span>  
 [<span data-ttu-id="60bd3-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="60bd3-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="60bd3-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="60bd3-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
