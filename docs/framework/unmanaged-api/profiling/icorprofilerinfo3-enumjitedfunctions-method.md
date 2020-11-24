---
title: ICorProfilerInfo3::EnumJITedFunctions-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
ms.openlocfilehash: 6227baaead518eae2de5913369b72de1072ac052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681495"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="c484f-102">ICorProfilerInfo3::EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="c484f-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>

<span data-ttu-id="c484f-103">Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="c484f-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c484f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c484f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c484f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c484f-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="c484f-106">vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](icorprofilerfunctionenum-interface.md) -Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c484f-106">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c484f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c484f-107">Remarks</span></span>  

 <span data-ttu-id="c484f-108">Diese Methode überschneidet sich möglicherweise mit Rückrufen, `JITCompilation` wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c484f-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="c484f-109">Der Enumerator, der von dieser Methode zurückgegeben wird, enthält keine Funktionen, die aus systemeigenen, mit Ngen.exe generierten Images geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c484f-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c484f-110">Die zurückgegebene Enumeration enthält nur "0" für den Wert des `COR_PRF_FUNCTION::reJitId` Felds.</span><span class="sxs-lookup"><span data-stu-id="c484f-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="c484f-111">Wenn Sie gültige `COR_PRF_FUNCTION::reJitId` Werte benötigen, verwenden Sie die [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c484f-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c484f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c484f-112">Requirements</span></span>  

 <span data-ttu-id="c484f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c484f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c484f-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c484f-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c484f-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c484f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c484f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c484f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c484f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c484f-117">See also</span></span>

- [<span data-ttu-id="c484f-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c484f-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="c484f-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c484f-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c484f-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c484f-120">Profiling</span></span>](index.md)
