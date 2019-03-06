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
ms.openlocfilehash: 9f76b727511ad604c407fb2998a5ecea26f91c49
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481362"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="cd162-102">ICorDebugGCReferenceEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="cd162-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="cd162-103">Ruft die angegebene Anzahl von [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Instanzen, die Informationen zu Objekten enthalten, die Garbage Collection durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cd162-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd162-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cd162-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd162-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cd162-105">Parameters</span></span>  
 <span data-ttu-id="cd162-106">celt</span><span class="sxs-lookup"><span data-stu-id="cd162-106">celt</span></span>  
 <span data-ttu-id="cd162-107">[in] Die Anzahl der Stämme abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cd162-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="cd162-108">Stämme</span><span class="sxs-lookup"><span data-stu-id="cd162-108">roots</span></span>  
 <span data-ttu-id="cd162-109">[out] Ein Array von Zeigern, die jeweils auf eine [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) -Objekt, das den Stamm eines Objekts, das speicherbereinigt werden soll darstellt.</span><span class="sxs-lookup"><span data-stu-id="cd162-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="cd162-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="cd162-110">pceltFetched</span></span>  
 <span data-ttu-id="cd162-111">[out] Ein Zeiger auf die Anzahl der [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) tatsächlich zurückgegebenen Objekte `roots`.</span><span class="sxs-lookup"><span data-stu-id="cd162-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="cd162-112">Dieser Wert kann `null` sein, wenn `celt` 1 ist.</span><span class="sxs-lookup"><span data-stu-id="cd162-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd162-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cd162-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd162-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cd162-114">Requirements</span></span>  
 <span data-ttu-id="cd162-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd162-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd162-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd162-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd162-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd162-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd162-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd162-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd162-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd162-119">See also</span></span>
- [<span data-ttu-id="cd162-120">ICorDebugGCReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cd162-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="cd162-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cd162-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
