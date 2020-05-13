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
ms.openlocfilehash: 291b384d6f0c8c1404b380c653693ec65fcfc960
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213412"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="1eb09-102">ICorDebugProcess5::EnumerateHandles-Methode</span><span class="sxs-lookup"><span data-stu-id="1eb09-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="1eb09-103">Ruft einen Enumerator für Objekt Handles in einem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="1eb09-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eb09-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb09-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1eb09-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="1eb09-106">in Eine bitweise Kombination von [corgkreferencetype](corgcreferencetype-enumeration.md) -Werten, die den Typ der Handles angibt, die in der Auflistung enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1eb09-106">[in] A bitwise combination of [CorGCReferenceType](corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="1eb09-107">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebug](icordebuggcreferenceenum-interface.md) -Enumerationsobjekts, bei dem es sich um einen Enumerator für die Objekte handelt, für die eine Garbage Collection durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1eb09-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eb09-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1eb09-108">Remarks</span></span>  
 <span data-ttu-id="1eb09-109">`EnumerateHandles`ist eine Hilfsfunktion, die die Überprüfung der Handle-Tabelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1eb09-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="1eb09-110">Die Methode ähnelt der [ICorDebugProcess5:: enumerategkreferences](icordebugprocess5-enumerategcreferences-method.md) -Methode, mit der Ausnahme, dass Sie keine [icordebuggkreferenceenumerationsauflistung](icordebuggcreferenceenum-interface.md) mit allen Objekten auffüllen, die für die Garbage Collection freigegeben werden sollen. Sie enthält nur Objekte, die über Handles aus der Handle-Tabelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="1eb09-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="1eb09-111">Der- `types` Parameter gibt die Handle-Typen an, die in die Auflistung eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1eb09-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="1eb09-112">`types`kann eines der folgenden drei Member der [corgkreferencetype](corgcreferencetype-enumeration.md) -Enumeration sein:</span><span class="sxs-lookup"><span data-stu-id="1eb09-112">`types` can be any of the following three members of the [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
- <span data-ttu-id="1eb09-113">`CorHandleStrongOnly`(nur Handles zu starken verweisen).</span><span class="sxs-lookup"><span data-stu-id="1eb09-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
- <span data-ttu-id="1eb09-114">`CorHandleWeakOnly`(nur Handles für schwache Verweise).</span><span class="sxs-lookup"><span data-stu-id="1eb09-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
- <span data-ttu-id="1eb09-115">`CorHandleAll`(alle Handles).</span><span class="sxs-lookup"><span data-stu-id="1eb09-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb09-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1eb09-116">Requirements</span></span>  
 <span data-ttu-id="1eb09-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb09-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb09-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1eb09-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1eb09-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eb09-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eb09-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb09-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb09-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb09-121">See also</span></span>

- [<span data-ttu-id="1eb09-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="1eb09-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="1eb09-123">Debuggen</span><span class="sxs-lookup"><span data-stu-id="1eb09-123">Debugging</span></span>](index.md)
