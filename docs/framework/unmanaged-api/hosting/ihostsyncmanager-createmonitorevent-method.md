---
title: IHostSyncManager::CreateMonitorEvent-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e5a66a87424c2ff8367aaf9ad4da27595880912
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753421"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="857fa-102">IHostSyncManager::CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="857fa-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="857fa-103">Erstellt ein überwachtes automatisches Zurücksetzungsereignis-Objekt.</span><span class="sxs-lookup"><span data-stu-id="857fa-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="857fa-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="857fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="857fa-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="857fa-106">[in] Ein Cookie, das Ereignisobjekt zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="857fa-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="857fa-107">[out] Ein Zeiger auf die Adresse einer [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="857fa-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="857fa-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="857fa-108">Return Value</span></span>  
  
|<span data-ttu-id="857fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="857fa-109">HRESULT</span></span>|<span data-ttu-id="857fa-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="857fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="857fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="857fa-111">S_OK</span></span>|<span data-ttu-id="857fa-112">`CreateMonitorEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="857fa-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="857fa-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="857fa-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="857fa-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="857fa-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="857fa-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="857fa-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="857fa-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="857fa-116">The call timed out.</span></span>|  
|<span data-ttu-id="857fa-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="857fa-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="857fa-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="857fa-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="857fa-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="857fa-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="857fa-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="857fa-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="857fa-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="857fa-121">E_FAIL</span></span>|<span data-ttu-id="857fa-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="857fa-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="857fa-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="857fa-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="857fa-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="857fa-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="857fa-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="857fa-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="857fa-126">Es war nicht genügend Arbeitsspeicher verfügbar, um das angeforderte Ereignis-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="857fa-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="857fa-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="857fa-127">Remarks</span></span>  
 <span data-ttu-id="857fa-128">`CreateMonitorEvent` Gibt eine `IHostAutoEvent` , die die CLR verwendet wird, in seiner Implementierung von verwalteten <xref:System.Threading.Monitor?displayProperty=nameWithType> Typ.</span><span class="sxs-lookup"><span data-stu-id="857fa-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="857fa-129">Diese Methode entspricht der Win32 `CreateEvent` Funktion, mit dem Wert `false` für die `bManualReset` Parameter.</span><span class="sxs-lookup"><span data-stu-id="857fa-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="857fa-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgabe auf dem Monitor wartet durch Aufrufen der [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="857fa-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="857fa-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="857fa-131">Requirements</span></span>  
 <span data-ttu-id="857fa-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="857fa-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="857fa-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="857fa-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="857fa-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="857fa-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="857fa-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="857fa-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="857fa-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="857fa-136">See also</span></span>

- [<span data-ttu-id="857fa-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="857fa-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="857fa-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="857fa-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="857fa-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="857fa-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
