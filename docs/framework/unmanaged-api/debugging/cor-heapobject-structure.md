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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179334"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="c4ffe-102">COR_HEAPOBJECT-Struktur</span><span class="sxs-lookup"><span data-stu-id="c4ffe-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="c4ffe-103">Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ffe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4ffe-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="c4ffe-105">Members</span><span class="sxs-lookup"><span data-stu-id="c4ffe-105">Members</span></span>  
  
|<span data-ttu-id="c4ffe-106">Member</span><span class="sxs-lookup"><span data-stu-id="c4ffe-106">Member</span></span>|<span data-ttu-id="c4ffe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4ffe-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="c4ffe-108">Die Adresse des Objekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="c4ffe-109">Die Gesamtgröße des Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="c4ffe-110">Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4ffe-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c4ffe-111">Remarks</span></span>  
 <span data-ttu-id="c4ffe-112">`COR_HEAPOBJECT`Instanzen können abgerufen werden, indem ein [ICorDebugHeapEnum-Schnittstellenobjekt](icordebugheapenum-interface.md) aufgezählt wird, das durch Aufrufen der [ICorDebugProcess5::EnumerateHeap-Methode](icordebugprocess5-enumerateheap-method.md) aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="c4ffe-113">Eine `COR_HEAPOBJECT` Instanz stellt Informationen entweder zu einem Liveobjekt auf dem verwalteten Heap oder zu einem Objekt bereit, das nicht von einem Objekt gerootet ist, aber noch nicht vom Garbage Collector gesammelt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="c4ffe-114">Für eine bessere `COR_HEAPOBJECT.address` Leistung `CORDB_ADDRESS` ist das Feld ein Wert und kein ICorDebugValue-Schnittstellenwert, der in einem Großteil der Debug-API verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="c4ffe-115">Um ein ICorDebugValue-Objekt für eine bestimmte Objektadresse zu erhalten, können Sie den `CORDB_ADDRESS` Wert an die [ICorDebugProcess5::GetObject-Methode](icordebugprocess5-getobject-method.md) übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="c4ffe-116">Für eine bessere `COR_HEAPOBJECT.type` Leistung `COR_TYPEID` ist das Feld ein Wert und kein ICorDebugType-Schnittstellenwert, der in einem Großteil der Debug-API verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="c4ffe-117">Um ein ICorDebugType-Objekt für eine bestimmte Typ-ID zu erhalten, können Sie den `COR_TYPEID` Wert an die [ICorDebugProcess5::GetTypeForTypeID-Methode](icordebugprocess5-gettypefortypeid-method.md) übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="c4ffe-118">Die `COR_HEAPOBJECT` Struktur enthält eine COM-Schnittstelle mit Referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="c4ffe-119">Wenn Sie `COR_HEAPOBJECT` eine Instanz aus dem Enumerator abrufen, indem Sie die [ICorDebugHeapEnum::Next-Methode](icordebugheapenum-next-method.md) aufrufen, müssen Sie den Verweis anschließend freigeben.</span><span class="sxs-lookup"><span data-stu-id="c4ffe-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ffe-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4ffe-120">Requirements</span></span>  
 <span data-ttu-id="c4ffe-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4ffe-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ffe-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4ffe-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4ffe-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4ffe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4ffe-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ffe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ffe-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4ffe-125">See also</span></span>

- [<span data-ttu-id="c4ffe-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c4ffe-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c4ffe-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c4ffe-127">Debugging</span></span>](index.md)
