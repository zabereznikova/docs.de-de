---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ce29703a181106353695414e8b291b14c697fc56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444787"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="72e8b-102">ICorProfilerInfo9::GetCodeInfo4 Method</span><span class="sxs-lookup"><span data-stu-id="72e8b-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="72e8b-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span><span class="sxs-lookup"><span data-stu-id="72e8b-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="72e8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72e8b-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

#### <a name="parameters"></a><span data-ttu-id="72e8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72e8b-105">Parameters</span></span>

`pNativeCodeStartAddress` \
<span data-ttu-id="72e8b-106">[in] A pointer to the start of a native function.</span><span class="sxs-lookup"><span data-stu-id="72e8b-106">[in] A pointer to the start of a native function.</span></span>

`cCodeInfos` \
<span data-ttu-id="72e8b-107">[in] Die Größe des `codeInfos`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="72e8b-107">[in] The size of the `codeInfos` array.</span></span>

`pcCodeInfos` \
<span data-ttu-id="72e8b-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span><span class="sxs-lookup"><span data-stu-id="72e8b-108">[out] A pointer to the total number of [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures available.</span></span>

`codeInfos` \
<span data-ttu-id="72e8b-109">[out] Ein vom Aufrufer bereitgestellter Puffer.</span><span class="sxs-lookup"><span data-stu-id="72e8b-109">[out] A caller-provided buffer.</span></span> <span data-ttu-id="72e8b-110">Nach dem Ausführen enthält die Methode ein Array aus `COR_PRF_CODE_INFO`-Strukturen, von denen jede einen Block des systemeigenen Codes beschreibt.</span><span class="sxs-lookup"><span data-stu-id="72e8b-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="72e8b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72e8b-111">Remarks</span></span>

<span data-ttu-id="72e8b-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span><span class="sxs-lookup"><span data-stu-id="72e8b-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="72e8b-113">`GetCodeInfo4` can trigger a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="72e8b-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="72e8b-114">Die Wertebereiche sind in aufsteigender Reihenfolge des CIL-Offsets (Common Intermediate Language) sortiert.</span><span class="sxs-lookup"><span data-stu-id="72e8b-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="72e8b-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span><span class="sxs-lookup"><span data-stu-id="72e8b-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="72e8b-116">Vergleichen Sie hierzu den Wert von `cCodeInfos` mit dem Wert des `cchName`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="72e8b-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="72e8b-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span><span class="sxs-lookup"><span data-stu-id="72e8b-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="72e8b-118">Alternativ können Sie zuerst `GetCodeInfo4` mit einem `codeInfos`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="72e8b-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="72e8b-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span><span class="sxs-lookup"><span data-stu-id="72e8b-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="72e8b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72e8b-120">Requirements</span></span>

<span data-ttu-id="72e8b-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="72e8b-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="72e8b-122">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72e8b-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="72e8b-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72e8b-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="72e8b-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72e8b-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="72e8b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e8b-125">See also</span></span>

- [<span data-ttu-id="72e8b-126">ICorProfilerInfo9 Interface</span><span class="sxs-lookup"><span data-stu-id="72e8b-126">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)
