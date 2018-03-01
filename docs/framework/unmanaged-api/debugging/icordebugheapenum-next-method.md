---
title: ICorDebugHeapEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9869542b04b26fdf343b4112c2f84a26a3061c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="280f5-102">ICorDebugHeapEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="280f5-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="280f5-103">Ruft die angegebene Anzahl von [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu Objekten im verwalteten Heap enthalten.</span><span class="sxs-lookup"><span data-stu-id="280f5-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="280f5-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="280f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="280f5-105">Parameters</span></span>  
 <span data-ttu-id="280f5-106">celt</span><span class="sxs-lookup"><span data-stu-id="280f5-106">celt</span></span>  
 <span data-ttu-id="280f5-107">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="280f5-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="280f5-108">Objekte</span><span class="sxs-lookup"><span data-stu-id="280f5-108">objects</span></span>  
 <span data-ttu-id="280f5-109">[out] Ein Array von Zeigern, die jeweils auf eine [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekt, das Informationen zu einem Objekt auf dem verwalteten Heap bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="280f5-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="280f5-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="280f5-110">pceltFetched</span></span>  
 <span data-ttu-id="280f5-111">[out] Ein Zeiger auf die Anzahl der [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) tatsächlich zurückgegebenen Objekte `objects`.</span><span class="sxs-lookup"><span data-stu-id="280f5-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="280f5-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="280f5-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="280f5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="280f5-113">Remarks</span></span>  
 <span data-ttu-id="280f5-114">Das `COR_HEAPOBJECT.type`-Feld ist der Bezeichner einer geschachtelten COM-Schnittstelle mit Referenzzählung.</span><span class="sxs-lookup"><span data-stu-id="280f5-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="280f5-115">Diese Referenz muss von dem Aufrufer von `ICorDebugHeapEnum::Next` freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="280f5-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="280f5-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="280f5-116">Requirements</span></span>  
 <span data-ttu-id="280f5-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="280f5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="280f5-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="280f5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="280f5-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="280f5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="280f5-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="280f5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280f5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="280f5-121">See Also</span></span>  
 [<span data-ttu-id="280f5-122">ICorDebugHeapEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="280f5-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 [<span data-ttu-id="280f5-123">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="280f5-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
