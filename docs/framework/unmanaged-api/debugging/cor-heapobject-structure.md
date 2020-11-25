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
ms.openlocfilehash: 54af02b48dabdf2042763954805f0d454323ac89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726365"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="8429f-102">COR_HEAPOBJECT-Struktur</span><span class="sxs-lookup"><span data-stu-id="8429f-102">COR_HEAPOBJECT Structure</span></span>

<span data-ttu-id="8429f-103">Stellt Informationen zu einem Objekt auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="8429f-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8429f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8429f-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;
    ULONG64 size;
    COR_TYPEID type;
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="8429f-105">Member</span><span class="sxs-lookup"><span data-stu-id="8429f-105">Members</span></span>  
  
|<span data-ttu-id="8429f-106">Member</span><span class="sxs-lookup"><span data-stu-id="8429f-106">Member</span></span>|<span data-ttu-id="8429f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8429f-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="8429f-108">Die Adresse des Objekts im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="8429f-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="8429f-109">Die Gesamtgröße des-Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8429f-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="8429f-110">Ein [COR_TYPEID](cor-typeid-structure.md) Token, das den Typ des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="8429f-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8429f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8429f-111">Remarks</span></span>  

 <span data-ttu-id="8429f-112">`COR_HEAPOBJECT` Instanzen können abgerufen werden, indem ein [icordebugheapenum](icordebugheapenum-interface.md) -Schnittstellen Objekt aufgezählt wird, das durch Aufrufen der [ICorDebugProcess5:: enumerateheap](icordebugprocess5-enumerateheap-method.md) -Methode ausgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="8429f-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="8429f-113">Eine- `COR_HEAPOBJECT` Instanz stellt Informationen entweder über ein Live Objekt im verwalteten Heap oder über ein Objekt bereit, das nicht von einem Objekt betroffen ist, aber noch nicht von der Garbage Collector erfasst wurde.</span><span class="sxs-lookup"><span data-stu-id="8429f-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="8429f-114">Um eine bessere Leistung zu erzielen, `COR_HEAPOBJECT.address` ist das Feld ein `CORDB_ADDRESS` Wert und nicht der ICorDebugValue-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8429f-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="8429f-115">Zum Abrufen eines ICorDebugValue-Objekts für eine angegebene Objekt Adresse können Sie den `CORDB_ADDRESS` Wert an die [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="8429f-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="8429f-116">Um eine bessere Leistung zu erzielen, `COR_HEAPOBJECT.type` ist das Feld ein `COR_TYPEID` Wert und nicht der ICorDebugType-Schnittstellen Wert, der in einem Großteil der Debug-API verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8429f-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="8429f-117">Zum Abrufen eines ICorDebugType-Objekts für eine bestimmte Typ-ID können Sie den `COR_TYPEID` Wert an die [ICorDebugProcess5:: gettyps](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="8429f-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="8429f-118">Die `COR_HEAPOBJECT` -Struktur enthält eine COM-Schnittstelle mit Verweis Zählung.</span><span class="sxs-lookup"><span data-stu-id="8429f-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="8429f-119">Wenn Sie eine- `COR_HEAPOBJECT` Instanz aus dem Enumerator abrufen, indem Sie die [icordebugheapenum:: Next](icordebugheapenum-next-method.md) -Methode aufrufen, müssen Sie anschließend den-Verweis freigeben.</span><span class="sxs-lookup"><span data-stu-id="8429f-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8429f-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8429f-120">Requirements</span></span>  

 <span data-ttu-id="8429f-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8429f-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8429f-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8429f-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8429f-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8429f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8429f-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8429f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8429f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8429f-125">See also</span></span>

- [<span data-ttu-id="8429f-126">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="8429f-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8429f-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8429f-127">Debugging</span></span>](index.md)
