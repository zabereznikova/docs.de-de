---
title: IHostTaskManager::Sleep-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.Sleep
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 648d705f21b23feb740e1791c8f32a707b985df2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442659"
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="d621d-102">IHostTaskManager::Sleep-Methode</span><span class="sxs-lookup"><span data-stu-id="d621d-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="d621d-103">Benachrichtigt den Host, dass die aktuelle Aufgabe, in den Energiesparmodus abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="d621d-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d621d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d621d-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d621d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d621d-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="d621d-106">[in] Das Zeitintervall in Millisekunden, die der Thread deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="d621d-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="d621d-107">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Enumerationswerte, der angibt, welche Aktion der Host ausführen soll, wenn diese Aktion blockiert.</span><span class="sxs-lookup"><span data-stu-id="d621d-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d621d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d621d-108">Return Value</span></span>  
  
|<span data-ttu-id="d621d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d621d-109">HRESULT</span></span>|<span data-ttu-id="d621d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d621d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d621d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d621d-111">S_OK</span></span>|<span data-ttu-id="d621d-112">`Sleep` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d621d-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="d621d-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="d621d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d621d-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="d621d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d621d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d621d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d621d-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d621d-116">The call timed out.</span></span>|  
|<span data-ttu-id="d621d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d621d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d621d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d621d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d621d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d621d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d621d-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d621d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d621d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d621d-121">E_FAIL</span></span>|<span data-ttu-id="d621d-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="d621d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d621d-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="d621d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d621d-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d621d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d621d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d621d-125">Remarks</span></span>  
 <span data-ttu-id="d621d-126">Die CLR ruft in der Regel `IHostTaskManager::Sleep` Wenn <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> von Benutzercode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d621d-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d621d-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d621d-127">Requirements</span></span>  
 <span data-ttu-id="d621d-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d621d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d621d-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d621d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d621d-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d621d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d621d-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d621d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d621d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d621d-132">See Also</span></span>  
 [<span data-ttu-id="d621d-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d621d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d621d-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d621d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d621d-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d621d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d621d-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d621d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
