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
ms.openlocfilehash: d156f103c3812c91da380e722a1c6c95d621df4c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860917"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="7cf51-102">CorGCReferenceType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7cf51-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="7cf51-103">Identifiziert die Quelle eines Objekts, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7cf51-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cf51-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7cf51-105">Members</span><span class="sxs-lookup"><span data-stu-id="7cf51-105">Members</span></span>  
  
|<span data-ttu-id="7cf51-106">Membername</span><span class="sxs-lookup"><span data-stu-id="7cf51-106">Member name</span></span>|<span data-ttu-id="7cf51-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7cf51-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="7cf51-108">Ein Handle für einen starken Verweis von der Objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="7cf51-109">Ein Handle für einen fixierten starken Verweis aus der Objekt Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="7cf51-110">Ein Handle für einen schwachen Verweis aus der Objekt Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="7cf51-111">Ein Handle für ein schwaches Verweis Gezähltes Objekt aus der Objekt Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="7cf51-112">Ein Handle für ein Objekt mit Verweis Zählung aus der Objekt Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="7cf51-113">Ein Handle für ein abhängiges Objekt aus der Objekt Handle-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="7cf51-114">Ein asynchrones angeheftetes Objekt von der Objekthandletabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf51-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="7cf51-115">Ein starkes Handle, das eine ungefähre Größe des kollektiven Abschlusses aller Objekte und Objektstämme zur Garbage Collection-Zeit enthält.</span><span class="sxs-lookup"><span data-stu-id="7cf51-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="7cf51-116">Ein Verweis aus dem verwalteten Stapel.</span><span class="sxs-lookup"><span data-stu-id="7cf51-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="7cf51-117">Ein Verweis aus der Finalizerwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="7cf51-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="7cf51-118">Corlenker strongonly</span><span class="sxs-lookup"><span data-stu-id="7cf51-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="7cf51-119">Gibt nur starke Verweise aus der Handle-Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="7cf51-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="7cf51-120">Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cf51-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="7cf51-121">Gibt nur schwache Verweise aus der Handle-Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="7cf51-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="7cf51-122">Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cf51-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="7cf51-123">Gibt alle Verweise aus der Handle-Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="7cf51-123">Return all references from the handle table.</span></span> <span data-ttu-id="7cf51-124">Dieser Wert wird nur von der [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cf51-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cf51-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7cf51-125">Remarks</span></span>  
 <span data-ttu-id="7cf51-126">Die `CorGCReferenceType` -Enumeration wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="7cf51-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="7cf51-127">Als Wert des- `type` Felds der [COR_GC_REFERENCE](cor-gc-reference-structure.md) Struktur wird die Quelle eines Verweises oder eines Handles angegeben.</span><span class="sxs-lookup"><span data-stu-id="7cf51-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="7cf51-128">Als `types` Argument für die [ICorDebugProcess5:: enumeratehandles](icordebugprocess5-enumeratehandles-method.md) -Methode gibt es die Typen von Handles an, die in der-Enumeration enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="7cf51-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf51-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7cf51-129">Requirements</span></span>  
 <span data-ttu-id="7cf51-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf51-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf51-131">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7cf51-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7cf51-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7cf51-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7cf51-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf51-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf51-134">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7cf51-134">See also</span></span>

- [<span data-ttu-id="7cf51-135">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="7cf51-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
