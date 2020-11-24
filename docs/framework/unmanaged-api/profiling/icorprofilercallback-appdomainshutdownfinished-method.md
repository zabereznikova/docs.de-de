---
title: ICorProfilerCallback::AppDomainShutdownFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: ddb2d6eeb75a118a12f681b354f6feccd1231c64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685380"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="c4878-102">ICorProfilerCallback::AppDomainShutdownFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="c4878-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>

<span data-ttu-id="c4878-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4878-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4878-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4878-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4878-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4878-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="c4878-106">\[in] identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c4878-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="c4878-107">\[in] ein HRESULT, das angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="c4878-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4878-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4878-108">Remarks</span></span>  

 <span data-ttu-id="c4878-109">Der Wert von `appDomainId` ist für eine Informationsanforderung nicht gültig, nachdem die [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) -Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c4878-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c4878-110">Einige Teile des Entladen der Anwendungsdomäne können nach dem Rückruf fortgesetzt werden `AppDomainCreationFinished` .</span><span class="sxs-lookup"><span data-stu-id="c4878-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="c4878-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="c4878-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c4878-112">Ein HRESULT-Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil des Ladens der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c4878-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4878-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4878-113">Requirements</span></span>  

 <span data-ttu-id="c4878-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4878-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4878-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4878-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4878-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4878-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4878-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4878-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4878-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4878-118">See also</span></span>

- [<span data-ttu-id="c4878-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4878-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
