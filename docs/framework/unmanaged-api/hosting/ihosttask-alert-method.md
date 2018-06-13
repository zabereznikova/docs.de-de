---
title: IHostTask::Alert-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 057e2aafff726b187f36b8b52859b2f2e812e70e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442363"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="32eb6-102">IHostTask::Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="32eb6-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="32eb6-103">Fordert an, dass der Host die Aufgabe, die vom aktuellen Wake-on [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz, damit der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="32eb6-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32eb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32eb6-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="32eb6-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="32eb6-105">Return Value</span></span>  
  
|<span data-ttu-id="32eb6-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32eb6-106">HRESULT</span></span>|<span data-ttu-id="32eb6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32eb6-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32eb6-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="32eb6-108">S_OK</span></span>|<span data-ttu-id="32eb6-109">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32eb6-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="32eb6-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="32eb6-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32eb6-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="32eb6-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32eb6-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32eb6-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32eb6-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="32eb6-113">The call timed out.</span></span>|  
|<span data-ttu-id="32eb6-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32eb6-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32eb6-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="32eb6-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32eb6-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32eb6-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32eb6-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="32eb6-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32eb6-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32eb6-118">E_FAIL</span></span>|<span data-ttu-id="32eb6-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="32eb6-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32eb6-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="32eb6-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32eb6-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="32eb6-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32eb6-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32eb6-122">Remarks</span></span>  
 <span data-ttu-id="32eb6-123">Die CLR ruft die `Alert` Methode beim <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aus Benutzercode aufgerufen wird oder wenn die <xref:System.AppDomain> verknüpft sind, mit dem aktuellen <xref:System.Threading.Thread> heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="32eb6-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="32eb6-124">Der Host muss sofort zurückgeben, da der Aufruf asynchron ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32eb6-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="32eb6-125">Wenn der Host die Aufgabe sofort benachrichtigen kann, muss er das nächste Mal aktiviert es ein einen Zustand wechselt, in dem sie benachrichtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="32eb6-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32eb6-126">`Alert` wirkt sich auf nur solche Tasks, die an den die Common Language Runtime übergeben hat eine [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Wert WAIT_ALERTABLE für Methoden, z. B. [verknüpfen](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="32eb6-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32eb6-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32eb6-127">Requirements</span></span>  
 <span data-ttu-id="32eb6-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32eb6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32eb6-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32eb6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32eb6-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="32eb6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32eb6-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32eb6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32eb6-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32eb6-132">See Also</span></span>  
 [<span data-ttu-id="32eb6-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32eb6-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="32eb6-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32eb6-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="32eb6-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32eb6-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="32eb6-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32eb6-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
