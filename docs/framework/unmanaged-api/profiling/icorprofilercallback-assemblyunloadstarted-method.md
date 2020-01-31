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
ms.openlocfilehash: 4c14b3e8b9d0116d638e2983955598a6c51c405a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790207"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="b4455-102">ICorProfilerCallback::AssemblyUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b4455-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="b4455-103">Benachrichtigt den Profiler, dass eine Assembly entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b4455-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4455-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4455-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4455-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b4455-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="b4455-106">\[in] identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="b4455-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4455-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4455-107">Remarks</span></span>  
 <span data-ttu-id="b4455-108">Der Wert `assemblyId` ist für eine Informationsanforderung nicht gültig, nachdem die `AssemblyUnloadStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Assembly zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b4455-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4455-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4455-109">Requirements</span></span>  
 <span data-ttu-id="b4455-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4455-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4455-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4455-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4455-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4455-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4455-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4455-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4455-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4455-114">See also</span></span>

- [<span data-ttu-id="b4455-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4455-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="b4455-116">AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b4455-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
