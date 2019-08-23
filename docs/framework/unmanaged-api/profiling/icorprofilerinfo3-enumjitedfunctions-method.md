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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ceb1d22500f73a29ffdfa6f16907478628358c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969394"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="f8c76-102">ICorProfilerInfo3::EnumJITedFunctions-Methode</span><span class="sxs-lookup"><span data-stu-id="f8c76-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="f8c76-103">Gibt einen Enumerator für alle Funktionen zurück, die zuvor JIT-kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="f8c76-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8c76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8c76-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8c76-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8c76-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f8c76-106">vorgenommen Ein Zeiger auf den [icorprofilerfunctionenumerator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) -Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f8c76-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8c76-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8c76-107">Remarks</span></span>  
 <span data-ttu-id="f8c76-108">Diese Methode überschneidet sich `JITCompilation` möglicherweise mit Rückrufen, wie z. b. der [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f8c76-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="f8c76-109">Der von dieser Methode zurückgegebene Enumerator enthält keine Funktionen, die aus mit Ngen. exe generierten systemeigenen Images geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f8c76-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8c76-110">Die zurückgegebene Enumeration enthält nur "0" für den Wert des `COR_PRF_FUNCTION::reJitId` Felds.</span><span class="sxs-lookup"><span data-stu-id="f8c76-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="f8c76-111">Wenn Sie gültige `COR_PRF_FUNCTION::reJitId` Werte benötigen, verwenden Sie die [ICorProfilerInfo4:: EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f8c76-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8c76-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8c76-112">Requirements</span></span>  
 <span data-ttu-id="f8c76-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8c76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8c76-114">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="f8c76-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8c76-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8c76-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8c76-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8c76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c76-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8c76-117">See also</span></span>

- [<span data-ttu-id="f8c76-118">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8c76-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f8c76-119">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f8c76-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f8c76-120">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="f8c76-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
