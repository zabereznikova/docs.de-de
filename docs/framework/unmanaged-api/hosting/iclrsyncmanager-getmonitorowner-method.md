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
ms.openlocfilehash: a2cb82d8071518af4d4bc3276871f3846a5a5693
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687081"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="a65a1-102">ICLRSyncManager::GetMonitorOwner-Methode</span><span class="sxs-lookup"><span data-stu-id="a65a1-102">ICLRSyncManager::GetMonitorOwner Method</span></span>

<span data-ttu-id="a65a1-103">Ruft die [IHostTask](ihosttask-interface.md) -Instanz ab, die den Monitor besitzt, der durch das angegebene Cookie identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a65a1-103">Gets the [IHostTask](ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a65a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a65a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a65a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a65a1-105">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="a65a1-106">in Das Cookie, das dem Monitor zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a65a1-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="a65a1-107">vorgenommen Ein Zeiger auf den, der `IHostTask` derzeit den Monitor besitzt, oder NULL, wenn keine Aufgabe den Besitz besitzt.</span><span class="sxs-lookup"><span data-stu-id="a65a1-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a65a1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a65a1-108">Return Value</span></span>  
  
|<span data-ttu-id="a65a1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a65a1-109">HRESULT</span></span>|<span data-ttu-id="a65a1-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a65a1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a65a1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a65a1-111">S_OK</span></span>|<span data-ttu-id="a65a1-112">`GetMonitorOwner` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a65a1-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="a65a1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a65a1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a65a1-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a65a1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a65a1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a65a1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a65a1-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a65a1-116">The call timed out.</span></span>|  
|<span data-ttu-id="a65a1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a65a1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a65a1-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a65a1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a65a1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a65a1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a65a1-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a65a1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a65a1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a65a1-121">E_FAIL</span></span>|<span data-ttu-id="a65a1-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a65a1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a65a1-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="a65a1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a65a1-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a65a1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a65a1-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a65a1-125">Remarks</span></span>  

 <span data-ttu-id="a65a1-126">Der Host ruft in der Regel `GetMonitorOwner` als Teil eines Deadlock-Erkennungsmechanismus auf.</span><span class="sxs-lookup"><span data-stu-id="a65a1-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="a65a1-127">Das Cookie ist einem Monitor zugeordnet, wenn er mithilfe eines [IHostSyncManager:: | atemonitorevent](ihostsyncmanager-createmonitorevent-method.md)-Aufrufens erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a65a1-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a65a1-128">Ein aufzurufende Ereignis, das dem Monitor zugrunde liegt, blockiert möglicherweise –, aber keinen Deadlock –, wenn aktuell ein aufrufungs Vorgang für das diesem Monitor zugeordnete Cookie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="a65a1-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="a65a1-129">Andere Tasks können auch blockiert werden, wenn Sie versuchen, diesen Monitor zu erwerben.</span><span class="sxs-lookup"><span data-stu-id="a65a1-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="a65a1-130">`GetMonitorOwner` gibt immer sofort zurück und kann nach einem Aufruf von jederzeit aufgerufen werden `CreateMonitorEvent` .</span><span class="sxs-lookup"><span data-stu-id="a65a1-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="a65a1-131">Der Host muss nicht warten, bis ein Task auf das Ereignis wartet.</span><span class="sxs-lookup"><span data-stu-id="a65a1-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a65a1-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a65a1-132">Requirements</span></span>  

 <span data-ttu-id="a65a1-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a65a1-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a65a1-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a65a1-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a65a1-135">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a65a1-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a65a1-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a65a1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65a1-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a65a1-137">See also</span></span>

- [<span data-ttu-id="a65a1-138">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a65a1-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a65a1-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a65a1-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
