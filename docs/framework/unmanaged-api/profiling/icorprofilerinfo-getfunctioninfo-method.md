---
title: ICorProfilerInfo::GetFunctionInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00b20134c0134aa30d2056b634c8525f66ed8cf5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602455"
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="71186-102">ICorProfilerInfo::GetFunctionInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="71186-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="71186-103">Ruft die übergeordnete Klasse und die Metadaten token für die angegebene Funktion stellen.</span><span class="sxs-lookup"><span data-stu-id="71186-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71186-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71186-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71186-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71186-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="71186-106">[in] Die ID der Funktion für die die übergeordnete Klasse und die Metadaten token abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="71186-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="71186-107">[out] Ein Zeiger auf die übergeordnete Klasse der Funktion.</span><span class="sxs-lookup"><span data-stu-id="71186-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="71186-108">[out] Ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="71186-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="71186-109">[out] Ein Zeiger auf das Metadatentoken für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="71186-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71186-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71186-110">Remarks</span></span>  
 <span data-ttu-id="71186-111">Der Profilercode kann Aufrufen [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) um eine Schnittstelle für die Metadaten für ein bestimmtes Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="71186-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="71186-112">Das Metadatentoken, das an den Speicherort zurückgegeben wird, auf den durch `pToken` verwiesen wird, kann anschließend für den Zugriff auf die Metadaten für die Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71186-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="71186-113">Die `ClassID` einer Funktion in einer generischen Klasse kann es sein, ohne weitere Kontextinformationen über die Verwendung der Funktion.</span><span class="sxs-lookup"><span data-stu-id="71186-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="71186-114">In diesem Fall `pClassId` 0.</span><span class="sxs-lookup"><span data-stu-id="71186-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="71186-115">Profiler-Code verwenden sollte [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) mit einem COR_PRF_FRAME_INFO-Wert, um mehr Kontext bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="71186-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71186-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71186-116">Requirements</span></span>  
 <span data-ttu-id="71186-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71186-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71186-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71186-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71186-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71186-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71186-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71186-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71186-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71186-121">See also</span></span>
- [<span data-ttu-id="71186-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71186-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
