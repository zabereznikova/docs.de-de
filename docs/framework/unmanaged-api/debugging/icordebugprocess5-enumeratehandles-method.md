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
ms.openlocfilehash: e0e68dba1f4d9ac5fa618aa842b823dcc046e70e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129681"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="f50eb-102">ICorDebugProcess5::EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="f50eb-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="f50eb-103">Ruft einen Enumerator für Objekt Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f50eb-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f50eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f50eb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f50eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f50eb-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="f50eb-106">in Eine bitweise Kombination von [corgkreferencetype](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Werten, die den Typ der Handles angibt, die in der Auflistung enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f50eb-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="f50eb-107">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) -Enumerationsobjekts, bei dem es sich um einen Enumerator für die Objekte handelt, für die eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f50eb-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f50eb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f50eb-108">Remarks</span></span>  
 <span data-ttu-id="f50eb-109">`EnumerateHandles` ist eine Hilfsfunktion, die die Überprüfung der Handle-Tabelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f50eb-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="f50eb-110">Sie ähnelt der [ICorDebugProcess5:: enumerategkreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) -Methode, mit dem Unterschied, dass Sie keine [icordebuggkreferenceenumerationsauflistung](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) mit allen Objekten auffüllen, die für die Garbage Collection freigegeben werden sollen. Sie enthält nur Objekte, die über Handles aus verfügen. die Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f50eb-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="f50eb-111">Der `types`-Parameter gibt die Handle-Typen an, die in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f50eb-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="f50eb-112">`types` kann eines der folgenden drei Member der [corgkreferencetype](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) -Enumeration sein:</span><span class="sxs-lookup"><span data-stu-id="f50eb-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="f50eb-113">`CorHandleStrongOnly` (nur Handles zu starken verweisen).</span><span class="sxs-lookup"><span data-stu-id="f50eb-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="f50eb-114">`CorHandleWeakOnly` (nur Handles für schwache Verweise).</span><span class="sxs-lookup"><span data-stu-id="f50eb-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="f50eb-115">`CorHandleAll` (alle Handles).</span><span class="sxs-lookup"><span data-stu-id="f50eb-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f50eb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f50eb-116">Requirements</span></span>  
 <span data-ttu-id="f50eb-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f50eb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f50eb-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f50eb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f50eb-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f50eb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f50eb-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f50eb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50eb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f50eb-121">See also</span></span>

- [<span data-ttu-id="f50eb-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f50eb-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f50eb-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f50eb-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
