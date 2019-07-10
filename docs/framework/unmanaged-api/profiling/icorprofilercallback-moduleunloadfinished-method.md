---
title: ICorProfilerCallback::ModuleUnloadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8dd5e2ecf22ce14765df8972611f1f95109f76ed
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769197"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="2723d-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="2723d-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="2723d-103">Benachrichtigt den Profiler, dass ein Modul entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2723d-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2723d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2723d-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2723d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2723d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2723d-106">[in] Die ID des Moduls, das entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2723d-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="2723d-107">[in] Ein HRESULT, der angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2723d-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2723d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2723d-108">Remarks</span></span>  
 <span data-ttu-id="2723d-109">Der Wert des `moduleId` gilt nicht für eine informationsanforderung nach der [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) Methodenrückgabe.</span><span class="sxs-lookup"><span data-stu-id="2723d-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="2723d-110">Das Entladen der Klasse möglicherweise weiterhin nach den `ModuleUnloadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2723d-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="2723d-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="2723d-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="2723d-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil des Entladevorgangs für das Modul erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2723d-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2723d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2723d-113">Requirements</span></span>  
 <span data-ttu-id="2723d-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2723d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2723d-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2723d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2723d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2723d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2723d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2723d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2723d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2723d-118">See also</span></span>

- [<span data-ttu-id="2723d-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2723d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
