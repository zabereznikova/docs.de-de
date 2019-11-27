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
ms.openlocfilehash: 40cb666c47c690dc930ec2cb7f6c89662464780e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445909"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="499a1-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="499a1-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="499a1-103">Benachrichtigt den Profiler, dass ein Modul das entladen abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="499a1-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="499a1-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="499a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="499a1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="499a1-106">in Die ID des Moduls, das entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="499a1-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="499a1-107">in Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="499a1-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="499a1-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="499a1-108">Remarks</span></span>  
 <span data-ttu-id="499a1-109">Der Wert `moduleId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="499a1-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="499a1-110">Einige Teile des Entladen der-Klasse können nach dem `ModuleUnloadFinished`-Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="499a1-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="499a1-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="499a1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="499a1-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="499a1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499a1-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="499a1-113">Requirements</span></span>  
 <span data-ttu-id="499a1-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499a1-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="499a1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="499a1-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="499a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="499a1-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499a1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="499a1-118">See also</span></span>

- [<span data-ttu-id="499a1-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="499a1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
