---
title: ICorProfilerCallback::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434549"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="809a2-102">ICorProfilerCallback::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="809a2-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="809a2-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span><span class="sxs-lookup"><span data-stu-id="809a2-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="809a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="809a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="809a2-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="809a2-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span><span class="sxs-lookup"><span data-stu-id="809a2-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="809a2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="809a2-107">Remarks</span></span>  
 <span data-ttu-id="809a2-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span><span class="sxs-lookup"><span data-stu-id="809a2-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="809a2-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="809a2-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="809a2-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span><span class="sxs-lookup"><span data-stu-id="809a2-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809a2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="809a2-111">Requirements</span></span>  
 <span data-ttu-id="809a2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="809a2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="809a2-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="809a2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="809a2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="809a2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="809a2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="809a2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809a2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="809a2-116">See also</span></span>

- [<span data-ttu-id="809a2-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="809a2-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="809a2-118">Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="809a2-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
