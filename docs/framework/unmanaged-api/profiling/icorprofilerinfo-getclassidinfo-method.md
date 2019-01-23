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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97465b5d39b3f6adbb6bccfc7b478ddad97066fc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563729"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="7e024-102">ICorProfilerInfo::GetClassIDInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="7e024-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="7e024-103">Ruft das übergeordnete Modul und das Metadatentoken für die angegebene Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="7e024-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e024-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e024-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e024-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e024-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="7e024-106">[in] Die ID der Klasse für den die Informationen abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7e024-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="7e024-107">[out] Ein Zeiger auf die ID des übergeordneten Moduls der Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e024-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="7e024-108">[out] Ein Zeiger auf das Metadatentoken für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="7e024-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e024-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e024-109">Remarks</span></span>  
 <span data-ttu-id="7e024-110">Der Profilercode kann Aufrufen [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) um eine Schnittstelle für die Metadaten für ein bestimmtes Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7e024-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="7e024-111">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pTypeDefToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e024-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="7e024-112">Rufen Sie weitere Informationen zu generischen Typen mit [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="7e024-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e024-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e024-113">Requirements</span></span>  
 <span data-ttu-id="7e024-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e024-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e024-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e024-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e024-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e024-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e024-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e024-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e024-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e024-118">See also</span></span>
- [<span data-ttu-id="7e024-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7e024-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
