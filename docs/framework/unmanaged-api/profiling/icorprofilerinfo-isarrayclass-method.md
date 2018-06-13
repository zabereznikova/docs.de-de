---
title: ICorProfilerInfo::IsArrayClass-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f34fee19c796f65d315fcbd26d55e1d5322303a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453027"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="aa0d9-102">ICorProfilerInfo::IsArrayClass-Methode</span><span class="sxs-lookup"><span data-stu-id="aa0d9-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="aa0d9-103">Bestimmt, ob die angegebene Klasse eine Array-Klasse.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa0d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa0d9-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa0d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa0d9-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="aa0d9-106">[in] Die ID der Klasse untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="aa0d9-107">[out] Ein Zeiger auf einen Wert der CorElementType-Enumeration, die den Typ der Elemente des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="aa0d9-108">[out] Ein Zeiger auf die Klassen-ID der Arrayelemente, falls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="aa0d9-109">[out] Ein Zeiger auf eine ganze Zahl, die den Rang (d. h. die Anzahl der Dimensionen) des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa0d9-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa0d9-110">Remarks</span></span>  
 <span data-ttu-id="aa0d9-111">Wenn die angegebene Klasse eine Array-Klasse, ist die `IsArrayClass` Methodenrückgabe ein S_OK HRESULT und Werte für alle nicht-Null-Output-Parameter.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="aa0d9-112">Andernfalls wird "S_FALSE" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aa0d9-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa0d9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa0d9-113">Requirements</span></span>  
 <span data-ttu-id="aa0d9-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa0d9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa0d9-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa0d9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa0d9-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa0d9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa0d9-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa0d9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0d9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa0d9-118">See Also</span></span>  
 [<span data-ttu-id="aa0d9-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa0d9-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
