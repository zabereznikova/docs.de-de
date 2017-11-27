---
title: COR_HEAPOBJECT-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPOBJECT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPOBJECT
helpviewer_keywords: COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bcd971853707349bf0d60459cb46b0fea1e8a97b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corheapobject-structure"></a><span data-ttu-id="7da97-102">COR_HEAPOBJECT-Struktur</span><span class="sxs-lookup"><span data-stu-id="7da97-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="7da97-103">Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="7da97-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7da97-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="7da97-105">Member</span><span class="sxs-lookup"><span data-stu-id="7da97-105">Members</span></span>  
  
|<span data-ttu-id="7da97-106">Member</span><span class="sxs-lookup"><span data-stu-id="7da97-106">Member</span></span>|<span data-ttu-id="7da97-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da97-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="7da97-108">Die Adresse des Objekts im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="7da97-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="7da97-109">Die Gesamtgröße des Objekts, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7da97-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="7da97-110">Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="7da97-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da97-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7da97-111">Remarks</span></span>  
 <span data-ttu-id="7da97-112">`COR_HEAPOBJECT`Instanzen können durch aufzählen abgerufen werden ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das durch den Aufruf enthält die [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7da97-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="7da97-113">Ein `COR_HEAPOBJECT` Instanz enthält Informationen über ein aktives Objekt auf dem verwalteten Heap oder über ein Objekt, das ist keines Objekt als Stamm, aber noch nicht vom Garbage Collector erfasst.</span><span class="sxs-lookup"><span data-stu-id="7da97-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="7da97-114">Aus Leistungsgründen die `COR_HEAPOBJECT.address` Feld ist ein `CORDB_ADDRESS` Wert statt ICorDebugValue-Schnittstelle im Großteil der Debug-API verwendete Wert.</span><span class="sxs-lookup"><span data-stu-id="7da97-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="7da97-115">Um ICorDebugValue-Objekts für eine Adresse für die angegebene Objekt zu erhalten, übergeben Sie die `CORDB_ADDRESS` -Wert an die [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7da97-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="7da97-116">Aus Leistungsgründen die `COR_HEAPOBJECT.type` Feld ist ein `COR_TYPEID` Wert anstelle der ICorDebugType-Schnittstelle im Großteil der Debug-API verwendete Wert.</span><span class="sxs-lookup"><span data-stu-id="7da97-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="7da97-117">Um ein ICorDebugType für einen angegebenen Typ-ID zu erhalten, übergeben Sie die `COR_TYPEID` -Wert an die [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7da97-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="7da97-118">Die `COR_HEAPOBJECT` Struktur umfasst eine COM-Schnittstelle mit referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="7da97-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="7da97-119">Wenn Sie Abrufen einer `COR_HEAPOBJECT` Instanz aus dem Enumerator durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) -Methode, Sie müssen den Verweis anschließend freigeben.</span><span class="sxs-lookup"><span data-stu-id="7da97-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7da97-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7da97-120">Requirements</span></span>  
 <span data-ttu-id="7da97-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da97-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da97-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7da97-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7da97-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7da97-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7da97-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da97-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da97-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7da97-125">See Also</span></span>  
 [<span data-ttu-id="7da97-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="7da97-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="7da97-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7da97-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
