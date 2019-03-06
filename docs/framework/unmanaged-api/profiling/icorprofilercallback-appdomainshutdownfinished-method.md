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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16973fe322a0fbd7a2433cd94982df04eb13dc50
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468727"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="fab2b-102">ICorProfilerCallback::AppDomainShutdownFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="fab2b-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="fab2b-103">Benachrichtigt den Profiler an, eine Anwendungsdomäne von einem Prozess entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fab2b-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fab2b-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fab2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fab2b-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="fab2b-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="fab2b-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fab2b-107">[in] Ein HRESULT, der angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fab2b-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fab2b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fab2b-108">Remarks</span></span>  
 <span data-ttu-id="fab2b-109">Der Wert des `appDomainId` gilt nicht für eine informationsanforderung nach der [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) Methodenrückgabe.</span><span class="sxs-lookup"><span data-stu-id="fab2b-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="fab2b-110">Das Entladen der Anwendungsdomäne möglicherweise weiterhin nach den `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="fab2b-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="fab2b-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fab2b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="fab2b-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil des Entladen der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fab2b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fab2b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fab2b-113">Requirements</span></span>  
 <span data-ttu-id="fab2b-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fab2b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fab2b-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fab2b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fab2b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fab2b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fab2b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fab2b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab2b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fab2b-118">See also</span></span>
- [<span data-ttu-id="fab2b-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fab2b-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
