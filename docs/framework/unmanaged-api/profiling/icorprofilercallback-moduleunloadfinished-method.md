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
ms.openlocfilehash: b13573d19ab4d8bb655c1e153530dc70173abe82
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866142"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a><span data-ttu-id="b07fc-102">ICorProfilerCallback::ModuleUnloadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="b07fc-102">ICorProfilerCallback::ModuleUnloadFinished Method</span></span>
<span data-ttu-id="b07fc-103">Benachrichtigt den Profiler, dass ein Modul das entladen abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="b07fc-103">Notifies the profiler that a module has finished unloading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b07fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b07fc-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b07fc-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b07fc-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b07fc-106">in Die ID des Moduls, das entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b07fc-106">[in] The ID of the module that was unloaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="b07fc-107">in Ein HRESULT, das angibt, ob das Modul erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b07fc-107">[in] An HRESULT that indicates whether the module was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b07fc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b07fc-108">Remarks</span></span>  
 <span data-ttu-id="b07fc-109">Der Wert `moduleId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b07fc-109">The value of `moduleId` is not valid for an information request after the [ICorProfilerCallback::ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="b07fc-110">Einige Teile des Entladen der-Klasse können nach dem `ModuleUnloadFinished`-Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b07fc-110">Some parts of unloading the class might continue after the `ModuleUnloadFinished` callback.</span></span> <span data-ttu-id="b07fc-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="b07fc-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="b07fc-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Entladen des Moduls erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b07fc-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the module has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b07fc-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b07fc-113">Requirements</span></span>  
 <span data-ttu-id="b07fc-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b07fc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b07fc-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b07fc-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b07fc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b07fc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b07fc-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b07fc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07fc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b07fc-118">See also</span></span>

- [<span data-ttu-id="b07fc-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b07fc-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
