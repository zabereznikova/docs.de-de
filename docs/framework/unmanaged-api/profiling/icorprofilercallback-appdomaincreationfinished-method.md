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
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177071"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="7ef84-102">ICorProfilerCallback::AppDomainCreationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="7ef84-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="7ef84-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7ef84-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ef84-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="7ef84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ef84-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="7ef84-106">\[in] Identifiziert die erstellte Domäne.</span><span class="sxs-lookup"><span data-stu-id="7ef84-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="7ef84-107">\[in] Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="7ef84-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ef84-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ef84-108">Remarks</span></span>  
 <span data-ttu-id="7ef84-109">Die Anwendungs-ID ist für Informationsanforderung `AppDomainCreationFinished` nicht gültig, bis die Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7ef84-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="7ef84-110">Einige Teile des Ladens der `AppDomainCreationFinished` Anwendungsdomäne werden möglicherweise nach dem Rückruf fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7ef84-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="7ef84-111">Ein Fehler HRESULT in `hrStatus` weist auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="7ef84-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="7ef84-112">Ein erfolgreicher HRESULT `hrStatus` in zeigt jedoch nur an, dass der erste Teil des Erstellens der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="7ef84-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ef84-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ef84-113">Requirements</span></span>  
 <span data-ttu-id="7ef84-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ef84-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ef84-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7ef84-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7ef84-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ef84-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ef84-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ef84-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef84-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ef84-118">See also</span></span>

- [<span data-ttu-id="7ef84-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ef84-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
