---
title: IHostGCManager::ThreadIsBlockingForSuspension-Methode
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 740f408b84dad67ee20c2508ae42a9569ed095f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993238"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="7f567-102">IHostGCManager::ThreadIsBlockingForSuspension-Methode</span><span class="sxs-lookup"><span data-stu-id="7f567-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="7f567-103">Benachrichtigt den Host, der der Thread aus dem Aufruf der Methode wurde zu, um für eine Garbagecollection zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="7f567-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f567-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f567-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7f567-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7f567-105">Return Value</span></span>  
  
|<span data-ttu-id="7f567-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f567-106">HRESULT</span></span>|<span data-ttu-id="7f567-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f567-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f567-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f567-108">S_OK</span></span>|<span data-ttu-id="7f567-109">`ThreadIsBlockingForSuspension` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7f567-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="7f567-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f567-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f567-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7f567-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f567-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f567-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f567-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7f567-113">The call timed out.</span></span>|  
|<span data-ttu-id="7f567-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f567-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f567-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7f567-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f567-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f567-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f567-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7f567-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f567-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f567-118">E_FAIL</span></span>|<span data-ttu-id="7f567-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7f567-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f567-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f567-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f567-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7f567-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f567-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7f567-122">Remarks</span></span>  
 <span data-ttu-id="7f567-123">Die CLR in der Regel ruft der `ThreadIsBlockForSuspension` -Methode in der Vorbereitung für eine Garbagecollection, um dem Host eine Möglichkeit, den Thread für nicht verwaltete Aufgaben erneut zu planen.</span><span class="sxs-lookup"><span data-stu-id="7f567-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7f567-124">Der Host kann nur nach einem Aufruf von neu Aufgaben planen `ThreadIsBlockingForSuspension`.</span><span class="sxs-lookup"><span data-stu-id="7f567-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="7f567-125">Nach dem Aufrufen der Common Language Runtime [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), der Host muss nicht neu planen eine Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="7f567-125">After the runtime calls [SuspensionStarting](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f567-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f567-126">Requirements</span></span>  
 <span data-ttu-id="7f567-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f567-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f567-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7f567-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f567-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7f567-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f567-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f567-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f567-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f567-131">See also</span></span>

- [<span data-ttu-id="7f567-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f567-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7f567-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f567-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7f567-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f567-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7f567-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f567-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7f567-136">IHostGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f567-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
