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
ms.openlocfilehash: 80054a8292c69b957664cb3573b0a8694c7f9fd2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500402"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="25491-102">ICorProfilerCallback::AssemblyUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="25491-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="25491-103">Benachrichtigt den Profiler, dass eine Assembly entladen wird.</span><span class="sxs-lookup"><span data-stu-id="25491-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25491-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25491-104">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25491-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25491-105">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="25491-106">\[in] identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="25491-106">\[in] Identifies the assembly that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="25491-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="25491-107">Remarks</span></span>  
 <span data-ttu-id="25491-108">Der Wert von `assemblyId` ist für eine Informationsanforderung nach dem `AssemblyUnloadStarted` zurückkehren der Methode ungültig – Dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Assembly zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25491-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25491-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="25491-109">Requirements</span></span>  
 <span data-ttu-id="25491-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25491-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25491-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25491-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25491-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25491-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25491-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25491-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25491-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="25491-114">See also</span></span>

- [<span data-ttu-id="25491-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25491-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="25491-116">AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="25491-116">AssemblyUnloadFinished Method</span></span>](icorprofilercallback-assemblyunloadfinished-method.md)
