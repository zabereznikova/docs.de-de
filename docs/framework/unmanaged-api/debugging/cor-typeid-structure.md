---
title: COR_TYPEID-Struktur
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
ms.openlocfilehash: 5eeb5aef7edaa23385190a309144e1477da741e8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697440"
---
# <a name="cor_typeid-structure"></a><span data-ttu-id="8a6d8-102">COR_TYPEID-Struktur</span><span class="sxs-lookup"><span data-stu-id="8a6d8-102">COR_TYPEID Structure</span></span>

<span data-ttu-id="8a6d8-103">Enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a6d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a6d8-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="8a6d8-105">Member</span><span class="sxs-lookup"><span data-stu-id="8a6d8-105">Members</span></span>  
  
|<span data-ttu-id="8a6d8-106">Member</span><span class="sxs-lookup"><span data-stu-id="8a6d8-106">Member</span></span>|<span data-ttu-id="8a6d8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8a6d8-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="8a6d8-108">Das erste Token.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="8a6d8-109">Das zweite Token.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a6d8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a6d8-110">Remarks</span></span>  

 <span data-ttu-id="8a6d8-111">Die `COR_TYPEID` Struktur wird von einer Reihe von Debugmethoden zurückgegeben, die Informationen zu Objekten bereitstellen, die für die Garbage Collection freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="8a6d8-112">Sie kann dann als Argument an andere Debugmethoden weitergegeben werden, die zusätzliche Informationen über dieses Element bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="8a6d8-113">Beispielsweise können Sie durch das Auflisten eines [icordebugheapenum](icordebugheapenum-interface.md) -Objekts einzelne [COR_HEAPOBJECT](cor-heapobject-structure.md) Objekte abrufen, die einzelne Objekte im verwalteten Heap darstellen.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-113">For example, by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="8a6d8-114">Sie können dann den `COR_TYPEID` Wert aus dem `COR_HEAPOBJECT.type` Feld an die [ICorDebugProcess5:: gettyetfortypeid](icordebugprocess5-gettypefortypeid-method.md) -Methode übergeben, um ein ICorDebugType-Objekt abzurufen, das Typinformationen über das Objekt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="8a6d8-115">Ein-Objekt ist als nicht transparent `COR_TYPEID` vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="8a6d8-116">Auf die einzelnen Felder sollte nicht zugegriffen werden oder Sie können nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="8a6d8-117">Die einzige Verwendung ist ein Bezeichner, der als- `out` Parameter in einem Methoden Aufrufwert bereitgestellt wird und der wiederum an andere Methoden übergeben werden kann, um zusätzliche Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8a6d8-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a6d8-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8a6d8-118">Requirements</span></span>  

 <span data-ttu-id="8a6d8-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a6d8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a6d8-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a6d8-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a6d8-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a6d8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a6d8-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a6d8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a6d8-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a6d8-123">See also</span></span>

- [<span data-ttu-id="8a6d8-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="8a6d8-124">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="8a6d8-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8a6d8-125">Debugging</span></span>](index.md)
