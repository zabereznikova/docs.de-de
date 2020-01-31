---
title: ICorProfilerCallback::ModuleLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 661229e5fbd5d106662f0e823a1753bd76c33311
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866168"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="b853b-102">ICorProfilerCallback::ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b853b-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>
<span data-ttu-id="b853b-103">Benachrichtigt den Profiler, dass ein Modul den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="b853b-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b853b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b853b-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b853b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b853b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b853b-106">in Die ID des Moduls, das den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="b853b-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="b853b-107">in Ein HRESULT, das angibt, ob das Modul erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b853b-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b853b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b853b-108">Remarks</span></span>  
 <span data-ttu-id="b853b-109">Der Wert `moduleId` ist für eine Informationsanforderung erst gültig, wenn die `ModuleLoadFinished`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b853b-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="b853b-110">Einige Teile des Ladens des Moduls können nach dem `ModuleLoadFinished` Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b853b-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="b853b-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="b853b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="b853b-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b853b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b853b-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b853b-113">Requirements</span></span>  
 <span data-ttu-id="b853b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b853b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b853b-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b853b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b853b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b853b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b853b-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b853b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b853b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b853b-118">See also</span></span>

- [<span data-ttu-id="b853b-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b853b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b853b-120">ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b853b-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
