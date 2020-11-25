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
ms.openlocfilehash: 26df1599af247bd08d3702d4ef3c5aa2f648620c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720372"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="d4408-102">ICorProfilerCallback::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="d4408-102">ICorProfilerCallback::Initialize Method</span></span>

<span data-ttu-id="d4408-103">Wird aufgerufen, um den Codeprofiler zu initialisieren, wenn eine neue Common Language Runtime-Anwendung (CLR) gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d4408-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4408-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4408-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4408-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4408-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="d4408-106">\[in] Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Schnittstelle, die der Profiler nach einem [ICorProfilerInfo](icorprofilerinfo-interface.md) -Schnittstellen Zeiger Abfragen muss.</span><span class="sxs-lookup"><span data-stu-id="d4408-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="d4408-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4408-107">Remarks</span></span>  

 <span data-ttu-id="d4408-108">Der `Initialize` Aufruf ist die einzige Möglichkeit, Rückrufe zu aktivieren (oder zu deaktivieren), die unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d4408-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="d4408-109">Nachdem ein Rückruf durch den-Befehl aktiviert `Initialize` wurde, kann er später nicht mithilfe von [ICorProfilerInfo::](icorprofilerinfo-seteventmask-method.md)absetzendebuggerinfo deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d4408-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="d4408-110">Der COR_PRF_MONITOR_IMMUTABLE Wert der [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) -Enumeration gibt an, welche Ereignisse unveränderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d4408-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4408-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d4408-111">Requirements</span></span>  

 <span data-ttu-id="d4408-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4408-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4408-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d4408-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d4408-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4408-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4408-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4408-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4408-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4408-116">See also</span></span>

- [<span data-ttu-id="d4408-117">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4408-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d4408-118">Shutdown-Methode</span><span class="sxs-lookup"><span data-stu-id="d4408-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
