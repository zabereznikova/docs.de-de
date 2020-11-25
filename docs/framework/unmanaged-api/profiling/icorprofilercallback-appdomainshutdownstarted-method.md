---
title: ICorProfilerCallback::AppDomainShutdownStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: cb0b763059c787b8f3e93e6c46b0e7fb2f8f8b2c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718461"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="d11b8-102">ICorProfilerCallback::AppDomainShutdownStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="d11b8-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>

<span data-ttu-id="d11b8-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wird.</span><span class="sxs-lookup"><span data-stu-id="d11b8-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d11b8-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d11b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d11b8-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="d11b8-106">\[in] identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="d11b8-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="d11b8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d11b8-107">Remarks</span></span>  

 <span data-ttu-id="d11b8-108">Der Wert von `appDomainId` ist für eine Informationsanforderung nach dem `AppDomainShutdownStarted` zurückkehren der Methode ungültig – Dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Anwendungsdomäne zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d11b8-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d11b8-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d11b8-109">Requirements</span></span>  

 <span data-ttu-id="d11b8-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d11b8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d11b8-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d11b8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d11b8-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d11b8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d11b8-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d11b8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d11b8-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d11b8-114">See also</span></span>

- [<span data-ttu-id="d11b8-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d11b8-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
