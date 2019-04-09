---
title: IHostTaskManager::BeginThreadAffinity-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eb5c7ec85c0adb301fb722155caaed3c14e0e19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137721"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="3cf68-102">IHostTaskManager::BeginThreadAffinity-Methode</span><span class="sxs-lookup"><span data-stu-id="3cf68-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="3cf68-103">Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht auf einen anderen Betriebssystemthread verschoben werden muss.</span><span class="sxs-lookup"><span data-stu-id="3cf68-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cf68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3cf68-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3cf68-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3cf68-105">Return Value</span></span>  
  
|<span data-ttu-id="3cf68-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3cf68-106">HRESULT</span></span>|<span data-ttu-id="3cf68-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3cf68-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3cf68-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cf68-108">S_OK</span></span>|`BeginThreadAffinity` <span data-ttu-id="3cf68-109">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3cf68-109">returned successfully.</span></span>|  
|<span data-ttu-id="3cf68-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3cf68-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3cf68-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3cf68-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3cf68-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3cf68-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3cf68-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3cf68-113">The call timed out.</span></span>|  
|<span data-ttu-id="3cf68-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3cf68-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3cf68-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3cf68-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3cf68-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3cf68-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3cf68-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3cf68-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3cf68-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3cf68-118">E_FAIL</span></span>|<span data-ttu-id="3cf68-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3cf68-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3cf68-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3cf68-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3cf68-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3cf68-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3cf68-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3cf68-122">Remarks</span></span>  
 <span data-ttu-id="3cf68-123">Die CLR in der Regel ruft `IHostTaskManager::BeginThreadAffinity` im Kontext eines Aufrufs von <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3cf68-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3cf68-124">Die aktuelle Aufgabe muss nicht neu geplant werden bis zu ein entsprechenden Aufruf erfolgt ist [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="3cf68-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="3cf68-125">Aufgaben können ausgelagert werden, aber wenn sie wieder übertragen werden, müssen zugewiesen werden, die demselben Betriebssystemthread, von dem sie ausgelagert wurden. Aufrufe von geschachtelten `BeginThreadAffinity` wirken sich nicht, weil der Aufruf auf die aktuelle Aufgabe verweist.</span><span class="sxs-lookup"><span data-stu-id="3cf68-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cf68-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3cf68-126">Requirements</span></span>  
 <span data-ttu-id="3cf68-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cf68-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cf68-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3cf68-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3cf68-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3cf68-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3cf68-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3cf68-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3cf68-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3cf68-131">See also</span></span>

- [<span data-ttu-id="3cf68-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cf68-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3cf68-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cf68-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3cf68-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cf68-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3cf68-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3cf68-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
