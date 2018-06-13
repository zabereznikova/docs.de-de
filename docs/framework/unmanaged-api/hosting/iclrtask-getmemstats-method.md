---
title: ICLRTask::GetMemStats-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.GetMemStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::GetMemStats
helpviewer_keywords:
- ICLRTask::GetMemStats method [.NET Framework hosting]
- GetMemStats method [.NET Framework hosting]
ms.assetid: c9e07657-1682-4c30-a336-f8658ff1a125
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2284a311f8355b65f312112db9cddd458517b46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433891"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="c2edd-102">ICLRTask::GetMemStats-Methode</span><span class="sxs-lookup"><span data-stu-id="c2edd-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="c2edd-103">Ruft die statistische Informationen für die Speicherverwendung im Zusammenhang mit der Aufgabe ab, die das aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2edd-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2edd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2edd-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2edd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2edd-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="c2edd-106">[out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) -Instanz, die Details über die Auslastung des Speichers des Vorgangs, einschließlich der Anzahl der reservierten Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="c2edd-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2edd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2edd-107">Return Value</span></span>  
  
|<span data-ttu-id="c2edd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2edd-108">HRESULT</span></span>|<span data-ttu-id="c2edd-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2edd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2edd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2edd-110">S_OK</span></span>|<span data-ttu-id="c2edd-111">`GetMemStats` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2edd-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="c2edd-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c2edd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2edd-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c2edd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2edd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2edd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2edd-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c2edd-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2edd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2edd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2edd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c2edd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2edd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2edd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2edd-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c2edd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2edd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2edd-120">E_FAIL</span></span>|<span data-ttu-id="c2edd-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c2edd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2edd-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c2edd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2edd-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c2edd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2edd-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2edd-124">Requirements</span></span>  
 <span data-ttu-id="c2edd-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2edd-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2edd-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2edd-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2edd-127">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2edd-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2edd-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2edd-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2edd-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2edd-129">See Also</span></span>  
 [<span data-ttu-id="c2edd-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2edd-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c2edd-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2edd-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c2edd-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2edd-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c2edd-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2edd-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
