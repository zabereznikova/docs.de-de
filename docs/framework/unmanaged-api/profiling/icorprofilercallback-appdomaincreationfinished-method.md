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
ms.openlocfilehash: eaf0ae2a1b86234495c1804cff8b74331b3e8021
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445274"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="534c8-102">ICorProfilerCallback::AppDomainCreationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="534c8-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="534c8-103">Benachrichtigt den Profiler, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="534c8-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="534c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="534c8-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="534c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="534c8-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="534c8-106">in Identifiziert die Domäne, die erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="534c8-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="534c8-107">in Ein HRESULT, das angibt, ob die Erstellung der Anwendungsdomäne erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="534c8-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="534c8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="534c8-108">Remarks</span></span>  
 <span data-ttu-id="534c8-109">Die Anwendungs-ID ist für eine beliebige Informationsanforderung erst gültig, wenn die `AppDomainCreationFinished`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="534c8-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="534c8-110">Einige Teile des Ladens der Anwendungsdomäne können nach dem `AppDomainCreationFinished` Rückruf fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="534c8-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="534c8-111">Ein HRESULT-Fehler in `hrStatus` deutet auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="534c8-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="534c8-112">Ein HRESULT mit Erfolg in `hrStatus` gibt jedoch nur an, dass der erste Teil der Erstellung der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="534c8-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534c8-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="534c8-113">Requirements</span></span>  
 <span data-ttu-id="534c8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534c8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534c8-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="534c8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="534c8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="534c8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="534c8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534c8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534c8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="534c8-118">See also</span></span>

- [<span data-ttu-id="534c8-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="534c8-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
