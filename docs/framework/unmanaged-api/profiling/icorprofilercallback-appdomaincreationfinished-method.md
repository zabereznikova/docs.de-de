---
title: ICorProfilerCallback::AppDomainCreationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35dac5fd000f5ae30af917e3813239b2e365e64a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598558"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="bea36-102">ICorProfilerCallback::AppDomainCreationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="bea36-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="bea36-103">Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bea36-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bea36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bea36-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="bea36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bea36-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="bea36-106">[in] Gibt die Domäne, die erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bea36-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="bea36-107">[in] Ein HRESULT, der angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bea36-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bea36-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bea36-108">Remarks</span></span>  
 <span data-ttu-id="bea36-109">Die Anwendungs-ID ist ungültig für jede informationsanforderung, bis die `AppDomainCreationFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bea36-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="bea36-110">Laden Sie die Anwendungsdomäne möglicherweise weiterhin nach den `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="bea36-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="bea36-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="bea36-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="bea36-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil der Erstellung der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bea36-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bea36-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bea36-113">Requirements</span></span>  
 <span data-ttu-id="bea36-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bea36-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bea36-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bea36-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bea36-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bea36-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bea36-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bea36-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea36-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bea36-118">See also</span></span>

- [<span data-ttu-id="bea36-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bea36-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
