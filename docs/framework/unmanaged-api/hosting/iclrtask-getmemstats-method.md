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
ms.openlocfilehash: 0bf8b6f393806e590be8f97dbfe2d01d5746c339
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139704"
---
# <a name="iclrtaskgetmemstats-method"></a><span data-ttu-id="416b8-102">ICLRTask::GetMemStats-Methode</span><span class="sxs-lookup"><span data-stu-id="416b8-102">ICLRTask::GetMemStats Method</span></span>
<span data-ttu-id="416b8-103">Ruft Informationen zur statistischen Speicherauslastung im Zusammenhang mit der Aufgabe ab, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="416b8-103">Gets statistical memory usage information related to the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="416b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="416b8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemStats (  
    [out] COR_GC_THREAD_STATS *pMemUsage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="416b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="416b8-105">Parameters</span></span>  
 `pMemUsage`  
 <span data-ttu-id="416b8-106">vorgenommen Ein Zeiger auf eine [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) -Instanz, die Details zur Speicherauslastung der Aufgabe enthält, einschließlich der Anzahl der zugeordneten Bytes.</span><span class="sxs-lookup"><span data-stu-id="416b8-106">[out] A pointer to a [COR_GC_THREAD_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md) instance that contains details about the memory usage of the task, including the number of bytes allocated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="416b8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="416b8-107">Return Value</span></span>  
  
|<span data-ttu-id="416b8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="416b8-108">HRESULT</span></span>|<span data-ttu-id="416b8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="416b8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="416b8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="416b8-110">S_OK</span></span>|<span data-ttu-id="416b8-111">`GetMemStats` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="416b8-111">`GetMemStats` returned successfully.</span></span>|  
|<span data-ttu-id="416b8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="416b8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="416b8-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="416b8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="416b8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="416b8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="416b8-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="416b8-115">The call timed out.</span></span>|  
|<span data-ttu-id="416b8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="416b8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="416b8-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="416b8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="416b8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="416b8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="416b8-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="416b8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="416b8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="416b8-120">E_FAIL</span></span>|<span data-ttu-id="416b8-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="416b8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="416b8-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="416b8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="416b8-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="416b8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="416b8-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="416b8-124">Requirements</span></span>  
 <span data-ttu-id="416b8-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="416b8-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="416b8-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="416b8-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="416b8-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="416b8-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="416b8-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="416b8-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416b8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="416b8-129">See also</span></span>

- [<span data-ttu-id="416b8-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="416b8-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="416b8-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="416b8-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="416b8-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="416b8-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="416b8-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="416b8-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
