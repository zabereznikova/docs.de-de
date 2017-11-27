---
title: ICLRSyncManager::GetMonitorOwner-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.GetMonitorOwner
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fbba9a5aead27d79c5355d69bc12481e826b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="ad9e9-102">ICLRSyncManager::GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="ad9e9-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="ad9e9-103">Ruft die [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, die den Monitor, der durch das angegebene Cookie identifiziert besitzt.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad9e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad9e9-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ad9e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad9e9-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ad9e9-106">[in] Das Cookie mit dem Monitor verknüpften.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="ad9e9-107">[out] Ein Zeiger auf die `IHostTask` , die derzeit besitzt der Monitor oder Null, wenn keine Aufgabe Besitzer ist.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad9e9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad9e9-108">Return Value</span></span>  
  
|<span data-ttu-id="ad9e9-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad9e9-109">HRESULT</span></span>|<span data-ttu-id="ad9e9-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad9e9-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad9e9-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad9e9-111">S_OK</span></span>|<span data-ttu-id="ad9e9-112">`GetMonitorOwner`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="ad9e9-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ad9e9-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad9e9-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad9e9-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad9e9-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad9e9-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-116">The call timed out.</span></span>|  
|<span data-ttu-id="ad9e9-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad9e9-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad9e9-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad9e9-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad9e9-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad9e9-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad9e9-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad9e9-121">E_FAIL</span></span>|<span data-ttu-id="ad9e9-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad9e9-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad9e9-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad9e9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad9e9-125">Remarks</span></span>  
 <span data-ttu-id="ad9e9-126">Ruft der Host in der Regel `GetMonitorOwner` als Teil einer Deadlockerkennung Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="ad9e9-127">Das Cookie mit einem Monitor zugeordnet ist, wenn es erstellt wird, mithilfe eines Aufrufs an [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad9e9-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad9e9-128">Ein Aufruf zur Freigabe von der zugrunde liegenden des Monitors Ereignisses blockiert werden könnten – aber nicht deadlock wird – Wenn ein Aufruf dieser Methode derzeit gültig für das Cookie zur Überwachung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="ad9e9-129">Andere Aufgaben können auch blockieren, wenn sie versuchen, diesen Monitor zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="ad9e9-130">`GetMonitorOwner`immer sofort zurückgegeben, und kann jederzeit nach einem Aufruf von aufgerufen werden `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="ad9e9-131">Der Host muss nicht warten, bis ein Task auf das Ereignis wartet.</span><span class="sxs-lookup"><span data-stu-id="ad9e9-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad9e9-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad9e9-132">Requirements</span></span>  
 <span data-ttu-id="ad9e9-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad9e9-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad9e9-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad9e9-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad9e9-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ad9e9-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad9e9-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad9e9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad9e9-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad9e9-137">See Also</span></span>  
 [<span data-ttu-id="ad9e9-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad9e9-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="ad9e9-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad9e9-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
