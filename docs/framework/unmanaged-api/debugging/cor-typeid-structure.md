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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 426420175a7d05f39859b9e217a888a8c01b6d63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740503"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="58caa-102">COR_TYPEID-Struktur</span><span class="sxs-lookup"><span data-stu-id="58caa-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="58caa-103">Enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="58caa-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58caa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58caa-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="58caa-105">Member</span><span class="sxs-lookup"><span data-stu-id="58caa-105">Members</span></span>  
  
|<span data-ttu-id="58caa-106">Member</span><span class="sxs-lookup"><span data-stu-id="58caa-106">Member</span></span>|<span data-ttu-id="58caa-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58caa-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="58caa-108">Das erste Token.</span><span class="sxs-lookup"><span data-stu-id="58caa-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="58caa-109">Das zweite-Token.</span><span class="sxs-lookup"><span data-stu-id="58caa-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58caa-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58caa-110">Remarks</span></span>  
 <span data-ttu-id="58caa-111">Die `COR_TYPEID` Struktur wird zurückgegeben, um eine Anzahl von debugging-Methoden, die Informationen zu Objekten, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="58caa-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="58caa-112">Sie können dann als Argument an andere debugging-Methoden übergeben werden, die zusätzliche Informationen zu diesem Element bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="58caa-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="58caa-113">Z. B. durch die Enumeration eine [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Objekt ist, können Sie einzelne abrufen [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte, die einzelnen Objekte im verwalteten Heap darstellen.</span><span class="sxs-lookup"><span data-stu-id="58caa-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="58caa-114">Anschließend können Sie übergeben die `COR_TYPEID` Wert aus der `COR_HEAPOBJECT.type` Feld der [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) Methode zum Abrufen eines ICorDebugType-Objekts, das Informationen über das Objekt bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="58caa-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="58caa-115">Ein `COR_TYPEID` Objekt ist nicht transparent sein soll.</span><span class="sxs-lookup"><span data-stu-id="58caa-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="58caa-116">Die einzelnen Felder sollten nicht zugegriffen oder bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="58caa-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="58caa-117">Die alleinige Verwendung ist ein Bezeichner, der als bereitgestellt wird ein `out` Parameter im Aufruf einer Methode und diese kann wiederum übergeben werden andere Methoden, um zusätzliche Informationen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="58caa-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58caa-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58caa-118">Requirements</span></span>  
 <span data-ttu-id="58caa-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58caa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58caa-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58caa-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58caa-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58caa-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58caa-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58caa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58caa-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58caa-123">See also</span></span>

- [<span data-ttu-id="58caa-124">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="58caa-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="58caa-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="58caa-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
