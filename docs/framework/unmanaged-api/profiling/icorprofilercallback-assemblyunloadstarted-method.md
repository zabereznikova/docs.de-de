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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a45c757a9176c77c7dbf58333b66d9b26514265
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471211"
---
# <a name="icorprofilercallbackassemblyunloadstarted-method"></a><span data-ttu-id="a753e-102">ICorProfilerCallback::AssemblyUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="a753e-102">ICorProfilerCallback::AssemblyUnloadStarted Method</span></span>
<span data-ttu-id="a753e-103">Benachrichtigt den Profiler, dass eine Assembly entladen wird.</span><span class="sxs-lookup"><span data-stu-id="a753e-103">Notifies the profiler that an assembly is being unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a753e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a753e-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadStarted(  
    [in] AssemblyID assemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a753e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a753e-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="a753e-106">[in] Identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="a753e-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a753e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a753e-107">Remarks</span></span>  
 <span data-ttu-id="a753e-108">Der Wert des `assemblyId` gilt nicht für eine informationsanforderung nach der `AssemblyUnloadStarted` Methodenrückgabe – Dies ist der Profiler letzte Gelegenheit zum Abrufen von Informationen zu dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="a753e-108">The value of `assemblyId` is not valid for an information request after the `AssemblyUnloadStarted` method returns — this is the profiler's last chance to get information about this assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a753e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a753e-109">Requirements</span></span>  
 <span data-ttu-id="a753e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a753e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a753e-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a753e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a753e-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a753e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a753e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a753e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a753e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a753e-114">See also</span></span>
- [<span data-ttu-id="a753e-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a753e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a753e-116">AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="a753e-116">AssemblyUnloadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)
