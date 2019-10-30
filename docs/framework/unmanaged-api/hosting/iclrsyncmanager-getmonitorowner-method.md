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
ms.openlocfilehash: 3aec11674275769bb5c4b68521a40a72a1d68a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124683"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="9e510-102">ICLRSyncManager::GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="9e510-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="9e510-103">Ruft die [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz ab, die den Monitor besitzt, der durch das angegebene Cookie identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9e510-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e510-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e510-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e510-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e510-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="9e510-106">in Das Cookie, das dem Monitor zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9e510-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="9e510-107">vorgenommen Ein Zeiger auf die `IHostTask`, die derzeit den Monitor besitzt, oder NULL, wenn keine Aufgabe den Besitz besitzt.</span><span class="sxs-lookup"><span data-stu-id="9e510-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e510-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9e510-108">Return Value</span></span>  
  
|<span data-ttu-id="9e510-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e510-109">HRESULT</span></span>|<span data-ttu-id="9e510-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e510-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e510-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e510-111">S_OK</span></span>|<span data-ttu-id="9e510-112">`GetMonitorOwner` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9e510-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="9e510-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e510-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e510-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9e510-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e510-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e510-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e510-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9e510-116">The call timed out.</span></span>|  
|<span data-ttu-id="9e510-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e510-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e510-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9e510-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e510-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e510-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e510-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9e510-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e510-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e510-121">E_FAIL</span></span>|<span data-ttu-id="9e510-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9e510-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e510-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e510-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e510-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9e510-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e510-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e510-125">Remarks</span></span>  
 <span data-ttu-id="9e510-126">Der Host ruft in der Regel `GetMonitorOwner` als Teil eines Deadlock-Erkennungsmechanismus auf.</span><span class="sxs-lookup"><span data-stu-id="9e510-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="9e510-127">Das Cookie ist einem Monitor zugeordnet, wenn er mithilfe eines [IHostSyncManager:: | atemonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)-Aufrufens erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9e510-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e510-128">Ein aufzurufende Ereignis, das dem Monitor zugrunde liegt, blockiert möglicherweise –, aber keinen Deadlock –, wenn aktuell ein aufrufungs Vorgang für das diesem Monitor zugeordnete Cookie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="9e510-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="9e510-129">Andere Tasks können auch blockiert werden, wenn Sie versuchen, diesen Monitor zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="9e510-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="9e510-130">`GetMonitorOwner` wird immer sofort zurückgegeben und kann nach einem Aufruf von `CreateMonitorEvent`jederzeit aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e510-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="9e510-131">Der Host muss nicht warten, bis ein Task auf das Ereignis wartet.</span><span class="sxs-lookup"><span data-stu-id="9e510-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e510-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e510-132">Requirements</span></span>  
 <span data-ttu-id="9e510-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e510-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e510-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9e510-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e510-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9e510-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e510-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e510-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e510-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e510-137">See also</span></span>

- [<span data-ttu-id="9e510-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e510-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9e510-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e510-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
