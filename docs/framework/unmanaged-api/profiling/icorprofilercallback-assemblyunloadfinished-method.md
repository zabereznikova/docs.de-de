---
title: ICorProfilerCallback::AssemblyUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6a9fe86d6160ebac084625ef94013cce9a27a3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501879"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="e913a-102">ICorProfilerCallback::AssemblyUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e913a-102">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>
<span data-ttu-id="e913a-103">Benachrichtigt den Profiler an, dass eine Assembly entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="e913a-103">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e913a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e913a-104">Syntax</span></span>  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e913a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e913a-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="e913a-106">[in] Identifiziert die Assembly, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="e913a-106">[in] Identifies the assembly that is being unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="e913a-107">[in] Ein HRESULT, der angibt, ob die Assembly erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="e913a-107">[in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e913a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e913a-108">Remarks</span></span>  
 <span data-ttu-id="e913a-109">Der Wert des `assemblyId` gilt nicht für eine informationsanforderung nach der [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) Methodenrückgabe.</span><span class="sxs-lookup"><span data-stu-id="e913a-109">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e913a-110">Entladen Sie die Assembly möglicherweise weiterhin nach den `AssemblyUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="e913a-110">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="e913a-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="e913a-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e913a-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil des Entladevorgangs für die Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="e913a-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e913a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e913a-113">Requirements</span></span>  
 <span data-ttu-id="e913a-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e913a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e913a-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e913a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e913a-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e913a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e913a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e913a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e913a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e913a-118">See also</span></span>
- [<span data-ttu-id="e913a-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e913a-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
