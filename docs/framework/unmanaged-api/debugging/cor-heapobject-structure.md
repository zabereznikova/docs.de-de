---
title: COR_HEAPOBJECT-Struktur
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f179b58ff8eb51e2843780d3212cf38ed7d13216
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168830"
---
# <a name="corheapobject-structure"></a><span data-ttu-id="9fe01-102">COR_HEAPOBJECT-Struktur</span><span class="sxs-lookup"><span data-stu-id="9fe01-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="9fe01-103">Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="9fe01-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fe01-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="9fe01-105">Member</span><span class="sxs-lookup"><span data-stu-id="9fe01-105">Members</span></span>  
  
|<span data-ttu-id="9fe01-106">Member</span><span class="sxs-lookup"><span data-stu-id="9fe01-106">Member</span></span>|<span data-ttu-id="9fe01-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fe01-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="9fe01-108">Die Adresse des Objekts im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="9fe01-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="9fe01-109">Die Gesamtgröße des Objekts, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="9fe01-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="9fe01-110">Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fe01-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fe01-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9fe01-111">Remarks</span></span>  
 `COR_HEAPOBJECT` <span data-ttu-id="9fe01-112">Instanzen abgerufen werden können, durch das Auflisten einer [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das durch den Aufruf enthält das [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9fe01-112">instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="9fe01-113">Ein `COR_HEAPOBJECT` Instanz enthält Informationen, die entweder über ein aktives Objekt auf dem verwalteten Heap oder über ein Objekt, das nicht wurden die nutzungsbeschränkungen entfernt jedes Objekt, aber noch nicht vom Garbage Collector übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9fe01-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="9fe01-114">Zur Verbesserung der Leistung der `COR_HEAPOBJECT.address` Feld ist ein `CORDB_ADDRESS` Wert anstelle der ICorDebugValue-Schnittstelle in einem Großteil der Debug-API verwendete Wert.</span><span class="sxs-lookup"><span data-stu-id="9fe01-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="9fe01-115">Um ICorDebugValue-Objekts für eine Adresse für die angegebene Objekt zu erhalten, können Sie übergeben die `CORDB_ADDRESS` Wert der [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9fe01-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="9fe01-116">Zur Verbesserung der Leistung der `COR_HEAPOBJECT.type` Feld ist ein `COR_TYPEID` Wert anstelle der ICorDebugType-Schnittstelle in einem Großteil der Debug-API verwendete Wert.</span><span class="sxs-lookup"><span data-stu-id="9fe01-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="9fe01-117">Um ein ICorDebugType für einen angegebenen Typ-ID zu erhalten, können Sie übergeben die `COR_TYPEID` Wert der [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="9fe01-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="9fe01-118">Die `COR_HEAPOBJECT` Struktur enthält eine COM-Schnittstelle mit referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="9fe01-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="9fe01-119">Wenn Sie abrufen eine `COR_HEAPOBJECT` Instanz aus dem Enumerator durch Aufrufen der [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) -Methode, Sie müssen anschließend den Verweis frei.</span><span class="sxs-lookup"><span data-stu-id="9fe01-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe01-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fe01-120">Requirements</span></span>  
 <span data-ttu-id="9fe01-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe01-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe01-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fe01-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fe01-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fe01-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9fe01-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9fe01-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9fe01-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fe01-125">See also</span></span>

- [<span data-ttu-id="9fe01-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="9fe01-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9fe01-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9fe01-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
