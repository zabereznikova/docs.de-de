---
title: ICorProfilerInfo4::GetCodeInfo3-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetCodeInfo3
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b669714774ecfccad436f064350569d27ef13883
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="85e1e-102">ICorProfilerInfo4::GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="85e1e-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="85e1e-103">Ruft die Erweiterungen des nativen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="85e1e-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85e1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85e1e-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85e1e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85e1e-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="85e1e-106">[in] Die ID der Funktion, der der native Code zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="85e1e-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="85e1e-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="85e1e-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="85e1e-108">[in] Die Größe des `codeInfos`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="85e1e-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="85e1e-109">[out] Ein Zeiger auf die Gesamtzahl der [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) Strukturen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="85e1e-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="85e1e-110">[out] Ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="85e1e-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="85e1e-111">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="85e1e-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85e1e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85e1e-112">Remarks</span></span>  
 <span data-ttu-id="85e1e-113">Die `GetCodeInfo3` Methode ist vergleichbar mit [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), außer dass die JIT-kompilierten ID der Funktion abgerufen werden sollen, die die angegebene IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="85e1e-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85e1e-114">`GetCodeInfo3`kann eine Garbagecollection auslösen, wohingegen [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) geschieht dies nicht.</span><span class="sxs-lookup"><span data-stu-id="85e1e-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="85e1e-115">Weitere Informationen finden Sie unter der [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="85e1e-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="85e1e-116">Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.</span><span class="sxs-lookup"><span data-stu-id="85e1e-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="85e1e-117">Nach dem `GetCodeInfo3` zurückgegeben wird, müssen Sie sicherstellen, dass die `codeInfos` -Puffer groß genug ist, um alle enthalten war die [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="85e1e-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="85e1e-118">Vergleichen Sie zu diesem Zweck den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="85e1e-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="85e1e-119">Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos` -Puffer zu, aktualisieren `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo3` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="85e1e-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="85e1e-120">Alternativ können Sie zuerst `GetCodeInfo3` mit einem `codeInfos`-Puffer der Länge 0 aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="85e1e-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="85e1e-121">Legen Sie Sie dann die `codeInfos` -Puffers auf den zurückgegebenen Wert `pcCodeInfos`multipliziert mit der Größe des eine [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur, und rufen `GetCodeInfo3` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="85e1e-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85e1e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85e1e-122">Requirements</span></span>  
 <span data-ttu-id="85e1e-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85e1e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85e1e-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="85e1e-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="85e1e-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85e1e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85e1e-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85e1e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e1e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85e1e-127">See Also</span></span>  
 [<span data-ttu-id="85e1e-128">GetCodeInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="85e1e-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
 [<span data-ttu-id="85e1e-129">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85e1e-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="85e1e-130">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="85e1e-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="85e1e-131">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="85e1e-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
