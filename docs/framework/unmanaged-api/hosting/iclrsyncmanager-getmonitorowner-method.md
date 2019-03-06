---
title: ICLRSyncManager::GetMonitorOwner-Methode
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 342039e21774668ed9e6bfac289aca7c1e99b1e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467081"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="9ee3f-102">ICLRSyncManager::GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="9ee3f-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="9ee3f-103">Ruft die [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, die der Besitzer den Monitor, der durch das angegebene Cookie identifiziert wird ist.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee3f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ee3f-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ee3f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ee3f-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="9ee3f-106">[in] Das Cookie mit dem Monitor verknüpften.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="9ee3f-107">[out] Ein Zeiger auf die `IHostTask` , die derzeit besitzt der Monitor oder Null, wenn keine Aufgabe Besitzer ist.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ee3f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ee3f-108">Return Value</span></span>  
  
|<span data-ttu-id="9ee3f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ee3f-109">HRESULT</span></span>|<span data-ttu-id="9ee3f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee3f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ee3f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ee3f-111">S_OK</span></span>|<span data-ttu-id="9ee3f-112">`GetMonitorOwner` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="9ee3f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ee3f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ee3f-114">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ee3f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ee3f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ee3f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-116">The call timed out.</span></span>|  
|<span data-ttu-id="9ee3f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ee3f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ee3f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ee3f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ee3f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ee3f-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ee3f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ee3f-121">E_FAIL</span></span>|<span data-ttu-id="9ee3f-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ee3f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ee3f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee3f-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ee3f-125">Remarks</span></span>  
 <span data-ttu-id="9ee3f-126">In der Regel ruft der Host `GetMonitorOwner` als Teil eines Deadlockerkennung Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="9ee3f-127">Das Cookie ein Monitor zugeordnet ist, bei der Erstellung mit einem Aufruf von [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ee3f-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ee3f-128">Ein Aufruf des Ereignisses, das zugrunde liegende Monitor freigegeben blockiert werden könnten, aber nicht in einem deadlock – Wenn ein Aufruf dieser Methode derzeit gültig für das Cookie zur Überwachung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="9ee3f-129">Auch können andere Tasks blockiert, wenn sie versuchen, diesen Monitor zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="9ee3f-130">`GetMonitorOwner` immer sofort zurückgegeben, und kann aufgerufen werden, einem beliebigen Zeitpunkt nach einem Aufruf von `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="9ee3f-131">Der Host muss nicht warten, bis ein Task auf das Ereignis wartet.</span><span class="sxs-lookup"><span data-stu-id="9ee3f-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee3f-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ee3f-132">Requirements</span></span>  
 <span data-ttu-id="9ee3f-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ee3f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee3f-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ee3f-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ee3f-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9ee3f-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee3f-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee3f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee3f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ee3f-137">See also</span></span>
- [<span data-ttu-id="9ee3f-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ee3f-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9ee3f-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ee3f-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
