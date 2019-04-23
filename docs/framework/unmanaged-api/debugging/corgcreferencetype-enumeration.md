---
title: CorGCReferenceType-Enumeration
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a673c98b11fbca5f66e9e1ae61f224448c20797
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207148"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="ded34-102">CorGCReferenceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ded34-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="ded34-103">Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ded34-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ded34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ded34-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="ded34-105">Member</span><span class="sxs-lookup"><span data-stu-id="ded34-105">Members</span></span>  
  
|<span data-ttu-id="ded34-106">Membername</span><span class="sxs-lookup"><span data-stu-id="ded34-106">Member name</span></span>|<span data-ttu-id="ded34-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ded34-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="ded34-108">Ein Handle für einen starken Verweis von der Objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="ded34-109">Ein Handle auf ein angehefteter starker Verweis von der objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="ded34-110">Ein Handle zu einem schwachen Verweis von der objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="ded34-111">Ein Handle zu einem schwachen Verweis gezähltes Objekt von der objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="ded34-112">Ein Handle auf ein Objekt mit verweiszählung von der objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="ded34-113">Ein Handle auf ein abhängiges Objekt von der objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="ded34-114">Ein asynchrones angeheftetes Objekt von der Objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="ded34-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="ded34-115">Ein starkes Handle, das eine ungefähre Größe des kollektiven Abschlusses aller Objekte und Objektstämme zur Garbage Collection-Zeit enthält.</span><span class="sxs-lookup"><span data-stu-id="ded34-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="ded34-116">Ein Verweis von den verwalteten Stapel.</span><span class="sxs-lookup"><span data-stu-id="ded34-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="ded34-117">Ein Verweis von der Finalizer-Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="ded34-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="ded34-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="ded34-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="ded34-119">Nur zuverlässige Verweise aus der Handletabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="ded34-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="ded34-120">Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.</span><span class="sxs-lookup"><span data-stu-id="ded34-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="ded34-121">Nur schwache Verweise aus der Handletabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="ded34-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="ded34-122">Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.</span><span class="sxs-lookup"><span data-stu-id="ded34-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="ded34-123">Alle Verweise aus der Handletabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="ded34-123">Return all references from the handle table.</span></span> <span data-ttu-id="ded34-124">Dieser Wert wird verwendet, durch die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) nur Methode.</span><span class="sxs-lookup"><span data-stu-id="ded34-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ded34-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ded34-125">Remarks</span></span>  
 <span data-ttu-id="ded34-126">Die `CorGCReferenceType` Enumeration wird folgendermaßen verwendet:</span><span class="sxs-lookup"><span data-stu-id="ded34-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="ded34-127">Als Wert für die `type` Feld der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Struktur gibt die Quelle der einen Verweis oder einen Handle an.</span><span class="sxs-lookup"><span data-stu-id="ded34-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="ded34-128">Als die `types` Argument für die [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) -Methode, die die Arten von Handles in der Enumeration eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ded34-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ded34-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ded34-129">Requirements</span></span>  
 <span data-ttu-id="ded34-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ded34-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ded34-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ded34-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ded34-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ded34-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ded34-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ded34-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ded34-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ded34-134">See also</span></span>

- [<span data-ttu-id="ded34-135">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ded34-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
