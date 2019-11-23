---
title: ICorProfilerInfo::GetClassIDInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: c3b1bdac8ccd37cf2f6aac5073def313f04acf28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439244"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="b8014-102">ICorProfilerInfo::GetClassIDInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="b8014-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="b8014-103">Gets the parent module and the metadata token for the specified class.</span><span class="sxs-lookup"><span data-stu-id="b8014-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8014-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8014-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8014-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8014-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="b8014-106">[in] The ID of the class for which to get the information.</span><span class="sxs-lookup"><span data-stu-id="b8014-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="b8014-107">[out] A pointer to the ID of the parent module of the class.</span><span class="sxs-lookup"><span data-stu-id="b8014-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="b8014-108">[out] A pointer to the metadata token for the class.</span><span class="sxs-lookup"><span data-stu-id="b8014-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8014-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8014-109">Remarks</span></span>  
 <span data-ttu-id="b8014-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span><span class="sxs-lookup"><span data-stu-id="b8014-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="b8014-111">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8014-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="b8014-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="b8014-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8014-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8014-113">Requirements</span></span>  
 <span data-ttu-id="b8014-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8014-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8014-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8014-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8014-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8014-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8014-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8014-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8014-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8014-118">See also</span></span>

- [<span data-ttu-id="b8014-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8014-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
