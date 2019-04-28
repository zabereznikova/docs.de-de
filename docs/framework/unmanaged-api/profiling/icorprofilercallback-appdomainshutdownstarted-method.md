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
ms.openlocfilehash: f422e99a5f6a4153368304ff0b33bbc55381575a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597848"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="4f470-102">ICorProfilerCallback::AppDomainShutdownStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="4f470-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="4f470-103">Benachrichtigt den Profiler, dass von einem Prozess, eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="4f470-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f470-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f470-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f470-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f470-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="4f470-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4f470-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f470-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4f470-107">Remarks</span></span>  
 <span data-ttu-id="4f470-108">Der Wert des `appDomainId` gilt nicht für jede informationsanforderung nach der `AppDomainShutdownStarted` Methodenrückgabe – Dies ist der Profiler letzte Gelegenheit zum Abrufen von Informationen zu dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="4f470-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f470-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f470-109">Requirements</span></span>  
 <span data-ttu-id="4f470-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f470-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f470-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f470-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f470-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f470-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f470-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f470-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f470-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f470-114">See also</span></span>

- [<span data-ttu-id="4f470-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f470-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
