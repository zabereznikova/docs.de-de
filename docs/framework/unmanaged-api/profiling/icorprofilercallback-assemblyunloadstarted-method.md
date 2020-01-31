---
title: ICorProfilerCallback::AssemblyUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted
helpviewer_keywords:
- ICorProfilerCallback::AssemblyUnloadStarted method [.NET Framework profiling]
- AssemblyUnloadStarted method [.NET Framework profiling]
ms.assetid: 6e47b7e5-0335-4dd3-8c42-d3c07d62b102
topic_type:
- apiref
ms.openlocfilehash: 0a677e33950f178b916a5e9e9cbb7bd918c1349b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866610"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="ef4cb-102">ICorProfilerCallback::AssemblyUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="ef4cb-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="ef4cb-103">Benachrichtigt den Profiler, dass eine Assembly entladen wird.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef4cb-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef4cb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="ef4cb-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="ef4cb-106">\[in] identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="ef4cb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef4cb-107">Remarks</span></span>  
 <span data-ttu-id="ef4cb-108">Der Wert `assemblyId` ist für eine Informationsanforderung nicht gültig, nachdem die `AssemblyUnloadStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Assembly zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ef4cb-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef4cb-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef4cb-109">Requirements</span></span>  
 <span data-ttu-id="ef4cb-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef4cb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef4cb-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef4cb-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef4cb-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef4cb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef4cb-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef4cb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4cb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef4cb-114">See also</span></span>

- [<span data-ttu-id="ef4cb-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef4cb-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ef4cb-116">AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="ef4cb-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
