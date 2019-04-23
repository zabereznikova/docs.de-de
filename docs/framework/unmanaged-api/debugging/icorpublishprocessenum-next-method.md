---
title: ICorPublishProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum::Next
helpviewer_keywords:
- ICorPublishProcessEnum::Next method [.NET Framework debugging]
- Next method, ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: 6c399f37-1e38-4ca1-b70d-8ae41f7228b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 169716d1a6d0dd633821cc832de96c9a02958d76
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183100"
---
# <a name="icorpublishprocessenumnext-method"></a><span data-ttu-id="dc5dd-102">ICorPublishProcessEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="dc5dd-102">ICorPublishProcessEnum::Next Method</span></span>
<span data-ttu-id="dc5dd-103">Ruft die angegebene Anzahl von Prozessen aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="dc5dd-103">Gets the specified number of processes from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc5dd-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorPublishProcess **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc5dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc5dd-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="dc5dd-106">[in] Die Anzahl der Prozesse abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dc5dd-106">[in] The number of processes to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="dc5dd-107">[out] Ein Zeiger auf das Array der abgerufenen [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekte, von denen jede einen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc5dd-107">[out] A pointer to the array of retrieved [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects, each of which represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="dc5dd-108">[out] Zeiger auf die Anzahl der tatsächlich zurückgegebenen Prozesse.</span><span class="sxs-lookup"><span data-stu-id="dc5dd-108">[out] Pointer to the number of processes actually returned.</span></span> <span data-ttu-id="dc5dd-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="dc5dd-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc5dd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc5dd-110">Requirements</span></span>  
 <span data-ttu-id="dc5dd-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc5dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5dd-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="dc5dd-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="dc5dd-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc5dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc5dd-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5dd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc5dd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc5dd-115">See also</span></span>

- [<span data-ttu-id="dc5dd-116">ICorPublishProcessEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc5dd-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)
