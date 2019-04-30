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
ms.openlocfilehash: 350221ae205636cef82581f3fe11367006dd8b2b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968076"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="3ddb0-102">ICorProfilerInfo::IsArrayClass-Methode</span><span class="sxs-lookup"><span data-stu-id="3ddb0-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="3ddb0-103">Bestimmt, ob die angegebene Klasse ein Array-Klasse ist.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ddb0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ddb0-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ddb0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ddb0-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="3ddb0-106">[in] Die ID der Klasse, die untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="3ddb0-107">[out] Ein Zeiger auf einen Wert der CorElementType-Enumeration, die den Typ der Elemente des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="3ddb0-108">[out] Ein Zeiger auf die Klassen-ID der Arrayelemente, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="3ddb0-109">[out] Ein Zeiger auf eine ganze Zahl, die den Rang (d. h. die Anzahl der Dimensionen) des Arrays angibt.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ddb0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ddb0-110">Remarks</span></span>  
 <span data-ttu-id="3ddb0-111">Wenn die angegebene Klasse ein Array-Klasse, ist die `IsArrayClass` Methodenrückgabe ein S_OK HRESULT und die Werte für alle nicht-Null Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="3ddb0-112">Wird zurückgegeben, andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="3ddb0-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ddb0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ddb0-113">Requirements</span></span>  
 <span data-ttu-id="3ddb0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ddb0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ddb0-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3ddb0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3ddb0-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ddb0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ddb0-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ddb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddb0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ddb0-118">See also</span></span>

- [<span data-ttu-id="3ddb0-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ddb0-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
