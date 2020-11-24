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
ms.openlocfilehash: 5a29507ca56cac4ab800845e3a88706dc7a25379
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683991"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a><span data-ttu-id="908a2-102">ICorProfilerCallback::ModuleLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="908a2-102">ICorProfilerCallback::ModuleLoadFinished Method</span></span>

<span data-ttu-id="908a2-103">Benachrichtigt den Profiler, dass ein Modul den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="908a2-103">Notifies the profiler that a module has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="908a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="908a2-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="908a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="908a2-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="908a2-106">in Die ID des Moduls, das den Ladevorgang abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="908a2-106">[in] The ID of the module that has finished loading.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="908a2-107">in Ein HRESULT, das angibt, ob das Modul erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="908a2-107">[in] An HRESULT that indicates whether the module was loaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="908a2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="908a2-108">Remarks</span></span>  

 <span data-ttu-id="908a2-109">Der Wert von `moduleId` ist für eine Informationsanforderung erst gültig, wenn die- `ModuleLoadFinished` Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="908a2-109">The value of `moduleId` is not valid for an information request until the `ModuleLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="908a2-110">Einige Teile des Ladens des Moduls können nach dem Rückruf fortgesetzt werden `ModuleLoadFinished` .</span><span class="sxs-lookup"><span data-stu-id="908a2-110">Some parts of loading the module might continue after the `ModuleLoadFinished` callback.</span></span> <span data-ttu-id="908a2-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="908a2-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="908a2-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="908a2-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="908a2-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="908a2-113">Requirements</span></span>  

 <span data-ttu-id="908a2-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="908a2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="908a2-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="908a2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="908a2-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="908a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="908a2-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="908a2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="908a2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="908a2-118">See also</span></span>

- [<span data-ttu-id="908a2-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="908a2-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="908a2-120">ModuleLoadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="908a2-120">ModuleLoadStarted Method</span></span>](icorprofilercallback-moduleloadstarted-method.md)
