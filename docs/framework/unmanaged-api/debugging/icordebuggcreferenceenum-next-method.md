---
title: ICorDebugGCReferenceEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01e52385f1a94ffb9682bdbe92e5c95e9870611e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416802"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="6d6f4-102">ICorDebugGCReferenceEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="6d6f4-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="6d6f4-103">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen, die Informationen zu Objekten enthalten, die Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="6d6f4-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d6f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d6f4-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d6f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d6f4-105">Parameters</span></span>  
 <span data-ttu-id="6d6f4-106">celt</span><span class="sxs-lookup"><span data-stu-id="6d6f4-106">celt</span></span>  
 <span data-ttu-id="6d6f4-107">[in] Die Anzahl der Stämme abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6d6f4-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="6d6f4-108">Stämme</span><span class="sxs-lookup"><span data-stu-id="6d6f4-108">roots</span></span>  
 <span data-ttu-id="6d6f4-109">[out] Ein Array von Zeigern, die jeweils auf eine [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekt, das den Stamm eines Objekts, das speicherbereinigt werden soll darstellt.</span><span class="sxs-lookup"><span data-stu-id="6d6f4-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="6d6f4-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="6d6f4-110">pceltFetched</span></span>  
 <span data-ttu-id="6d6f4-111">[out] Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) tatsächlich zurückgegebenen Objekte `roots`.</span><span class="sxs-lookup"><span data-stu-id="6d6f4-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="6d6f4-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="6d6f4-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d6f4-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d6f4-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d6f4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d6f4-114">Requirements</span></span>  
 <span data-ttu-id="6d6f4-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d6f4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d6f4-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d6f4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d6f4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d6f4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d6f4-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d6f4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6f4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d6f4-119">See Also</span></span>  
 [<span data-ttu-id="6d6f4-120">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d6f4-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="6d6f4-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6d6f4-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
