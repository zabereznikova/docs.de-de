---
title: ICorProfilerObjectEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Next
helpviewer_keywords:
- Next method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Next method [.NET Framework profiling]
ms.assetid: b420433c-5ebe-4986-bba1-97902e6db819
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c938c7c51c867d8e8d8d23390a3c16a23084fbc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775009"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="db020-102">ICorProfilerObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="db020-102">ICorProfilerObjectEnum::Next Method</span></span>
<span data-ttu-id="db020-103">Ruft die angegebene Anzahl zusammenhängender Objekte aus einer sequenziellen Auflistung von Objekten, beginnend ab der Position des Enumerators aktuelle in der Sequenz ab.</span><span class="sxs-lookup"><span data-stu-id="db020-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db020-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db020-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db020-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db020-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="db020-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="db020-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="db020-107">[out] Ein Array von `ObjectID` Werten, von denen jeder ein abgerufene Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="db020-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="db020-108">[out] Ein Zeiger auf die Anzahl von Elementen, die tatsächlich im `objects`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="db020-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db020-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db020-109">Requirements</span></span>  
 <span data-ttu-id="db020-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db020-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db020-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db020-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db020-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db020-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db020-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db020-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db020-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db020-114">See also</span></span>

- [<span data-ttu-id="db020-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db020-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
