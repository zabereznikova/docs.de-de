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
ms.openlocfilehash: 1d7cff23fc0b58d316ce19950a982249e84b79ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441951"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="74fe6-102">IHostSyncManager::CreateMonitorEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="74fe6-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="74fe6-103">Erstellt ein Ereignisobjekt überwachten AutoReset.</span><span class="sxs-lookup"><span data-stu-id="74fe6-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74fe6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="74fe6-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74fe6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="74fe6-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="74fe6-106">[in] Ein Cookie, das Ereignisobjekt zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="74fe6-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="74fe6-107">[out] Ein Zeiger auf die Adresse des ein [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="74fe6-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74fe6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74fe6-108">Return Value</span></span>  
  
|<span data-ttu-id="74fe6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74fe6-109">HRESULT</span></span>|<span data-ttu-id="74fe6-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74fe6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74fe6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="74fe6-111">S_OK</span></span>|<span data-ttu-id="74fe6-112">`CreateMonitorEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="74fe6-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="74fe6-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="74fe6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="74fe6-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="74fe6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="74fe6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="74fe6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="74fe6-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="74fe6-116">The call timed out.</span></span>|  
|<span data-ttu-id="74fe6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="74fe6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="74fe6-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="74fe6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="74fe6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="74fe6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="74fe6-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="74fe6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="74fe6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="74fe6-121">E_FAIL</span></span>|<span data-ttu-id="74fe6-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="74fe6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="74fe6-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="74fe6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="74fe6-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="74fe6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="74fe6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="74fe6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="74fe6-126">Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74fe6-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74fe6-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74fe6-127">Remarks</span></span>  
 <span data-ttu-id="74fe6-128">`CreateMonitorEvent` Gibt eine `IHostAutoEvent` , die die CLR verwendet wird, in seiner Implementierung von verwalteten <xref:System.Threading.Monitor?displayProperty=nameWithType> Typ.</span><span class="sxs-lookup"><span data-stu-id="74fe6-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="74fe6-129">Diese Methode spiegelt die Win32- `CreateEvent` Funktion, mit dem Wert `false` angegeben für die `bManualReset` Parameter.</span><span class="sxs-lookup"><span data-stu-id="74fe6-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="74fe6-130">Der Host kann das Cookie verwenden, um zu bestimmen, welche Aufgabe auf dem Monitor wartet durch Aufrufen der [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="74fe6-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74fe6-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74fe6-131">Requirements</span></span>  
 <span data-ttu-id="74fe6-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74fe6-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74fe6-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="74fe6-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="74fe6-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="74fe6-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74fe6-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74fe6-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74fe6-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74fe6-136">See Also</span></span>  
 [<span data-ttu-id="74fe6-137">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74fe6-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="74fe6-138">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74fe6-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="74fe6-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74fe6-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="74fe6-140">Monitore</span><span class="sxs-lookup"><span data-stu-id="74fe6-140">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
