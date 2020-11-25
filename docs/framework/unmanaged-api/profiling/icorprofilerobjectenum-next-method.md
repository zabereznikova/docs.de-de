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
ms.openlocfilehash: e0c10549ab9075c2e7604a9adb18cae8b9a3b32b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702367"
---
# <a name="icorprofilerobjectenumnext-method"></a><span data-ttu-id="5ab7b-102">ICorProfilerObjectEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="5ab7b-102">ICorProfilerObjectEnum::Next Method</span></span>

<span data-ttu-id="5ab7b-103">Ruft die angegebene Anzahl von zusammenhängenden Objekten aus einer sequenziellen Auflistung von-Objekten ab, beginnend bei der aktuellen Position des Enumerators in der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="5ab7b-103">Gets the specified number of contiguous objects from a sequential collection of objects, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ab7b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG                    celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ObjectID                  objects[],  
    [out] ULONG                   *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ab7b-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5ab7b-106">[in] Die Anzahl der abzurufenden Objekte.</span><span class="sxs-lookup"><span data-stu-id="5ab7b-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="5ab7b-107">vorgenommen Ein Array von- `ObjectID` Werten, von denen jedes ein abgerufenes-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ab7b-107">[out] An array of `ObjectID` values, each of which represents a retrieved object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5ab7b-108">[out] Ein Zeiger auf die Anzahl von Elementen, die tatsächlich im `objects`-Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5ab7b-108">[out] A pointer to the number of elements actually returned in the `objects` array.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab7b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5ab7b-109">Requirements</span></span>  

 <span data-ttu-id="5ab7b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ab7b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab7b-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ab7b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ab7b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab7b-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab7b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ab7b-114">See also</span></span>

- [<span data-ttu-id="5ab7b-115">ICorProfilerObjectEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ab7b-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
