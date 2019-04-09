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
ms.openlocfilehash: 668e570c315f5473f222905a061f05ac94afa81a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183403"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="f848e-102">ICLRTask::GetMemStats-Methode</span><span class="sxs-lookup"><span data-stu-id="f848e-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="f848e-103">Ruft die statistische Informationen für die Speicherverwendung im Zusammenhang mit der Aufgabe ab, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="f848e-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f848e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f848e-104">Syntax</span></span>  
  
```  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f848e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f848e-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="f848e-106">[out] Ein Zeiger auf eine [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) -Instanz, die Details zur arbeitsspeichernutzung des Vorgangs, einschließlich der Anzahl der zugeordneten Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="f848e-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f848e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f848e-107">Return Value</span></span>  
  
|<span data-ttu-id="f848e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f848e-108">HRESULT</span></span>|<span data-ttu-id="f848e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f848e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f848e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f848e-110">S_OK</span></span>|`GetMemStats` <span data-ttu-id="f848e-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f848e-111">returned successfully.</span></span>|  
|<span data-ttu-id="f848e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f848e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f848e-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f848e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f848e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f848e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f848e-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f848e-115">The call timed out.</span></span>|  
|<span data-ttu-id="f848e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f848e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f848e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f848e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f848e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f848e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f848e-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f848e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f848e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f848e-120">E_FAIL</span></span>|<span data-ttu-id="f848e-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f848e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f848e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f848e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f848e-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f848e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f848e-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f848e-124">Requirements</span></span>  
 <span data-ttu-id="f848e-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f848e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f848e-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f848e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f848e-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f848e-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f848e-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f848e-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f848e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f848e-129">See also</span></span>

- [<span data-ttu-id="f848e-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f848e-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="f848e-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f848e-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="f848e-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f848e-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="f848e-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f848e-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
