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
ms.openlocfilehash: 04ce9ebded4be7ac3b20a4ceb78dd02294bbff4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502896"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a><span data-ttu-id="8c5d9-102">ICorProfilerInfo2::GetCodeInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="8c5d9-102">ICorProfilerInfo2::GetCodeInfo2 Method</span></span>
<span data-ttu-id="8c5d9-103">Ruft die Wertebereiche von nativem Code ab, der der angegebenen `FunctionID` zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-103">Gets the extents of native code associated with the specified `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c5d9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c5d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c5d9-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="8c5d9-106">[in] Die ID der Funktion, der der systemeigene Code zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="8c5d9-107">[in] Die Größe des `codeInfos`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-107">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="8c5d9-108">vorgenommen Ein Zeiger auf die Gesamtzahl der verfügbaren [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) Strukturen.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="8c5d9-109">[out] Ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="8c5d9-110">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c5d9-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8c5d9-111">Remarks</span></span>  
 <span data-ttu-id="8c5d9-112">Die Wertebereiche sind in aufsteigender Reihenfolge des MSIL-Offsets (Microsoft Intermediate Language (MSIL) sortiert.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-112">The extents are sorted in order of increasing Microsoft intermediate language (MSIL) offset.</span></span>  
  
 <span data-ttu-id="8c5d9-113">Nachdem `GetCodeInfo2` ausgeführt ist, müssen Sie sich vergewissern, dass der `codeInfos`-Puffer groß genug war, um alle `COR_PRF_CODE_INFO`-Strukturen zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-113">After `GetCodeInfo2` returns, you must verify that the `codeInfos` buffer was large enough to contain all the `COR_PRF_CODE_INFO` structures.</span></span> <span data-ttu-id="8c5d9-114">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-114">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="8c5d9-115">Wenn `cCodeInfos` dividiert durch die Größe einer `COR_PRF_CODE_INFO`-Struktur kleiner ist als `pcCodeInfos`, weisen Sie einen größeren `codeInfos`-Puffer zu, aktualisieren Sie `cCodeInfos` mit der neuen Größe, und rufen `GetCodeInfo2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-115">If `cCodeInfos` divided by the size of a `COR_PRF_CODE_INFO` structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo2` again.</span></span>  
  
 <span data-ttu-id="8c5d9-116">Alternativ können Sie zuerst `GetCodeInfo2` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-116">Alternatively, you can first call `GetCodeInfo2` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="8c5d9-117">Sie können dann die Größe des `codeInfos`-Puffers auf den von `pcCodeInfos` zurückgegebenen Wert multipliziert mit der Größe einer `COR_PRF_CODE_INFO`-Struktur festlegen und `GetCodeInfo2` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8c5d9-117">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a `COR_PRF_CODE_INFO` structure, and call `GetCodeInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5d9-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8c5d9-118">Requirements</span></span>  
 <span data-ttu-id="8c5d9-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5d9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5d9-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8c5d9-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8c5d9-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c5d9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c5d9-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5d9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5d9-123">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8c5d9-123">See also</span></span>

- [<span data-ttu-id="8c5d9-124">GetCodeInfo3-Methode</span><span class="sxs-lookup"><span data-stu-id="8c5d9-124">GetCodeInfo3 Method</span></span>](icorprofilerinfo4-getcodeinfo3-method.md)
- [<span data-ttu-id="8c5d9-125">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c5d9-125">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
- [<span data-ttu-id="8c5d9-126">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8c5d9-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8c5d9-127">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="8c5d9-127">Profiling</span></span>](index.md)
