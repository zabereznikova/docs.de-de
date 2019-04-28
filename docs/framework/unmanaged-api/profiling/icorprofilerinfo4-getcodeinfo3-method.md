---
title: ICorProfilerInfo4::GetCodeInfo3-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb067d16ef7f8177f979a083707f8c6ef36750c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61685627"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="c9702-102">ICorProfilerInfo4::GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="c9702-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="c9702-103">Ruft die Erweiterungen des systemeigenen Codes ab, die der JIT-kompilierten Version der angegebenen Funktion zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c9702-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9702-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9702-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9702-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9702-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="c9702-106">[in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c9702-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="c9702-107">[in] Die Identität der erneut JIT-kompilierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="c9702-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="c9702-108">[in] Die Größe des `codeInfos`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c9702-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="c9702-109">[out] Ein Zeiger auf die Gesamtanzahl der [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c9702-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="c9702-110">[out] Ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="c9702-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="c9702-111">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c9702-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9702-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9702-112">Remarks</span></span>  
 <span data-ttu-id="c9702-113">Die `GetCodeInfo3` -Methode ist vergleichbar mit [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), außer dass der erneut JIT-kompilierte ID der Funktion abgerufen werden sollen, die die angegebene IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="c9702-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9702-114">`GetCodeInfo3` kann eine Garbagecollection auslösen, während [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="c9702-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="c9702-115">Weitere Informationen finden Sie unter den [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c9702-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="c9702-116">Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.</span><span class="sxs-lookup"><span data-stu-id="c9702-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="c9702-117">Nach dem `GetCodeInfo3` zurückgegeben wird, müssen Sie sicherstellen, dass die `codeInfos` -Puffer groß genug, um alle enthalten war die [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="c9702-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="c9702-118">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="c9702-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c9702-119">Wenn `cCodeInfos` dividiert durch die Größe einer [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos` -Puffer zu, aktualisieren `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo3` erneut aus.</span><span class="sxs-lookup"><span data-stu-id="c9702-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="c9702-120">Alternativ können Sie zuerst `GetCodeInfo3` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c9702-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c9702-121">Sie können dann Festlegen der `codeInfos` -Puffers auf den Rückgabewert `pcCodeInfos`multipliziert mit der Größe der eine [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) -Struktur, und rufen `GetCodeInfo3` erneut.</span><span class="sxs-lookup"><span data-stu-id="c9702-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9702-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9702-122">Requirements</span></span>  
 <span data-ttu-id="c9702-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9702-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9702-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9702-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9702-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9702-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9702-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9702-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9702-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9702-127">See also</span></span>

- [<span data-ttu-id="c9702-128">GetCodeInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="c9702-128">GetCodeInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="c9702-129">ICorProfilerInfo4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9702-129">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="c9702-130">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c9702-130">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c9702-131">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c9702-131">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
