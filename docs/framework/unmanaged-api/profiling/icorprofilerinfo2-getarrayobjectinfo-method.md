---
title: ICorProfilerInfo2::GetArrayObjectInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: a1e321e141059ccf1da7292d28e7099418a5134e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727197"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="4e008-102">ICorProfilerInfo2::GetArrayObjectInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="4e008-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>

<span data-ttu-id="4e008-103">Ruft ausführliche Informationen zu einem Array Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="4e008-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e008-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e008-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e008-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e008-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="4e008-106">in Die ID eines gültigen Array Objekts.</span><span class="sxs-lookup"><span data-stu-id="4e008-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="4e008-107">in Der Rang (Anzahl der Dimensionen) des Arrays.</span><span class="sxs-lookup"><span data-stu-id="4e008-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="4e008-108">vorgenommen Ein Array, das ganze Zahlen enthält, die jeweils die Größe einer Dimension des Arrays darstellen.</span><span class="sxs-lookup"><span data-stu-id="4e008-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="4e008-109">vorgenommen Ein Array, das ganze Zahlen enthält, die jeweils die untere Grenze einer Dimension des Arrays darstellen.</span><span class="sxs-lookup"><span data-stu-id="4e008-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="4e008-110">vorgenommen Ein Zeiger auf die Adresse des Rohdaten Puffers für das Array, das entsprechend der C++-Konvention angeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="4e008-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e008-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e008-111">Remarks</span></span>  

 <span data-ttu-id="4e008-112">`pDimensionSizes`Und `pDimensionLowerBounds` sind parallele Arrays, sodass die Elemente, die sich am selben Index in jedem Array befinden, Merkmale derselben Entität sind.</span><span class="sxs-lookup"><span data-stu-id="4e008-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e008-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4e008-113">Requirements</span></span>  

 <span data-ttu-id="4e008-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e008-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e008-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e008-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e008-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e008-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e008-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e008-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e008-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e008-118">See also</span></span>

- [<span data-ttu-id="4e008-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e008-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="4e008-120">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e008-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
