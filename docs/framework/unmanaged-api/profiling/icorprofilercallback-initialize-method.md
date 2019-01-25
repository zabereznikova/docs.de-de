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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5aa1025d3f24126c6f8b8585e39dda0201fad3d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623312"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="d16e5-102">ICorProfilerCallback::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="d16e5-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="d16e5-103">Wird aufgerufen, um den Profiler zu initialisieren, wenn eine neue common Language Runtime (CLR)-Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d16e5-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d16e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d16e5-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d16e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d16e5-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="d16e5-106">[in](/cpp/atl/iunknown) -Schnittstelle, die der Profiler für die Abfrage muss eine [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="d16e5-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d16e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d16e5-107">Remarks</span></span>  
 <span data-ttu-id="d16e5-108">Die `Initialize` Aufruf ist die einzige Möglichkeit zu aktivieren (oder deaktivieren) Sie Rückrufe, die unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d16e5-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="d16e5-109">Nachdem Sie ein Rückruf aktiviert ist, indem die `Initialize` aufrufen, er kann nicht mit einem späteren Zeitpunkt deaktiviert werden [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="d16e5-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="d16e5-110">Die COR_PRF_MONITOR_IMMUTABLE-Wert, der die [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration gibt an, welche Ereignisse unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d16e5-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d16e5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d16e5-111">Requirements</span></span>  
 <span data-ttu-id="d16e5-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d16e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d16e5-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d16e5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d16e5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d16e5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d16e5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d16e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d16e5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d16e5-116">See also</span></span>
- [<span data-ttu-id="d16e5-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d16e5-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d16e5-118">Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="d16e5-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
