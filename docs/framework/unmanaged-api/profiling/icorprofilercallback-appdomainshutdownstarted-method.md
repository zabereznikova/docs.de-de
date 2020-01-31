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
ms.openlocfilehash: d280b008b34befce04159d02dfbb3de37b262c3c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866662"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="75e36-102">ICorProfilerCallback::AppDomainShutdownStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="75e36-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="75e36-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne von einem Prozess entladen wird.</span><span class="sxs-lookup"><span data-stu-id="75e36-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="75e36-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75e36-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="75e36-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="75e36-106">\[in] identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="75e36-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="75e36-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75e36-107">Remarks</span></span>  
 <span data-ttu-id="75e36-108">Der Wert von `appDomainId` ist für keine Informationsanforderung gültig, nachdem die `AppDomainShutdownStarted`-Methode zurückgegeben wurde – dies ist die letzte Möglichkeit des Profilers, Informationen zu dieser Anwendungsdomäne zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="75e36-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e36-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75e36-109">Requirements</span></span>  
 <span data-ttu-id="75e36-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75e36-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e36-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="75e36-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="75e36-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e36-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e36-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e36-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e36-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75e36-114">See also</span></span>

- [<span data-ttu-id="75e36-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75e36-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
