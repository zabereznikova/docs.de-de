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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153984"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="55830-102">ICorProfilerCallback::AppDomainCreationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="55830-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="55830-103">Benachrichtigt den Profiler an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="55830-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55830-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55830-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="55830-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55830-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="55830-106">[in] Gibt die Domäne, die erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="55830-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="55830-107">[in] Ein HRESULT, der angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="55830-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55830-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55830-108">Remarks</span></span>  
 <span data-ttu-id="55830-109">Die Anwendungs-ID ist ungültig für jede informationsanforderung, bis die `AppDomainCreationFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="55830-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="55830-110">Laden Sie die Anwendungsdomäne möglicherweise weiterhin nach den `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="55830-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="55830-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="55830-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="55830-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil der Erstellung der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="55830-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55830-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55830-113">Requirements</span></span>  
 <span data-ttu-id="55830-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55830-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55830-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55830-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55830-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55830-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="55830-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="55830-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55830-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55830-118">See also</span></span>

- [<span data-ttu-id="55830-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55830-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
