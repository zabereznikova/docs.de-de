---
title: ICorProfilerInfo2::GetCodeInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 22463a56911354c9706bbfbc7d1824aee5d3c74d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725024"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="aaa6d-102">ICorProfilerInfo2::GetCodeInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="aaa6d-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="aaa6d-103">Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aaa6d-104">Syntax</span></span>  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aaa6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aaa6d-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="aaa6d-106">[in] Die ID der Funktion, der der native Code zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="aaa6d-107">[in] Die Größe des `codeInfos`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="aaa6d-108">[out] Ein Zeiger auf die Gesamtanzahl der [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="aaa6d-109">[out] Ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="aaa6d-110">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des nativen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aaa6d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aaa6d-111">Remarks</span></span>  
 <span data-ttu-id="aaa6d-112">Die Wertebereiche sind in aufsteigender Reihenfolge des MSIL-Offsets (Microsoft Intermediate Language (MSIL) sortiert.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="aaa6d-113">Nachdem `GetCodeInfo2` ausgeführt ist, müssen Sie sich vergewissern, dass der `codeInfos`-Puffer groß genug war, um alle `COR_PRF_CODE_INFO`-Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="aaa6d-114">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="aaa6d-115">Wenn `cCodeInfos` dividiert durch die Größe einer `COR_PRF_CODE_INFO`-Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos`-Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="aaa6d-116">Alternativ können Sie zuerst `GetCodeInfo2` mit einem `codeInfos`-Puffer der Länge 0 (null) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="aaa6d-117">Sie können dann die Größe des `codeInfos`-Puffers auf den von `pcCodeInfos` zurückgegebenen Wert multipliziert mit der Größe einer `COR_PRF_CODE_INFO`-Struktur festlegen und `GetCodeInfo2` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="aaa6d-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa6d-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aaa6d-118">Requirements</span></span>  
 <span data-ttu-id="aaa6d-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaa6d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa6d-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aaa6d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aaa6d-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aaa6d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aaa6d-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa6d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa6d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aaa6d-123">See also</span></span>
- [<span data-ttu-id="aaa6d-124">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="aaa6d-124">GetCodeInfo3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)
- [<span data-ttu-id="aaa6d-125">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aaa6d-125">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [<span data-ttu-id="aaa6d-126">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="aaa6d-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="aaa6d-127">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="aaa6d-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
