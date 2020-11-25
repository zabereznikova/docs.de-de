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
ms.openlocfilehash: 514c20455b95ecf74ffaecd349982fd8f8f49816
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723232"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="3d017-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="3d017-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>

<span data-ttu-id="3d017-103">Benachrichtigt den Profiler, dass ein Modul das entladen abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="3d017-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d017-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d017-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d017-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d017-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="3d017-106">in Die ID des Moduls, das entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="3d017-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3d017-107">in Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="3d017-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d017-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d017-108">Remarks</span></span>  

 <span data-ttu-id="3d017-109">Der Wert von `moduleId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3d017-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="3d017-110">Einige Teile des Entladen der Klasse können nach dem Rückruf fortgesetzt werden `ModuleUnloadFinished` .</span><span class="sxs-lookup"><span data-stu-id="3d017-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="3d017-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="3d017-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3d017-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="3d017-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d017-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3d017-113">Requirements</span></span>  

 <span data-ttu-id="3d017-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d017-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d017-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d017-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d017-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d017-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d017-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d017-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d017-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d017-118">See also</span></span>

- [<span data-ttu-id="3d017-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d017-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
