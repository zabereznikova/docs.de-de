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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fd1e5daada8793e94980afc5f0cf509915bd288e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450927"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="c4618-102">ICorProfilerCallback::AppDomainShutdownStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="c4618-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="c4618-103">Benachrichtigt den Profiler, dass von einem Prozess eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="c4618-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4618-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4618-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4618-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4618-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c4618-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c4618-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4618-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4618-107">Remarks</span></span>  
 <span data-ttu-id="c4618-108">Der Wert der `appDomainId` gilt nicht für jede Anforderung Informationen nach der `AppDomainShutdownStarted` -Methode zurückkehrt – Dies ist der Profiler die letzte Möglichkeit zum Abrufen von Informationen zu dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c4618-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4618-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4618-109">Requirements</span></span>  
 <span data-ttu-id="c4618-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4618-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4618-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4618-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4618-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4618-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4618-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4618-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4618-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4618-114">See Also</span></span>  
 [<span data-ttu-id="c4618-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4618-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
