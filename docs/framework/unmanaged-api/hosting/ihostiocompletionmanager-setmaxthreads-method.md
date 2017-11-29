---
title: IHostIoCompletionManager::SetMaxThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 084cbf5509583a45f09bcf903e833f4890c5651e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="585bf-102">IHostIoCompletionManager::SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="585bf-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="585bf-103">Legt die maximale Anzahl von Threads, die der Host-Bereitstellung für e/a-Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="585bf-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="585bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="585bf-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="585bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="585bf-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="585bf-106">[in] Die maximale Anzahl von Threads für e/a-Anforderungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="585bf-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="585bf-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="585bf-107">Return Value</span></span>  
  
|<span data-ttu-id="585bf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="585bf-108">HRESULT</span></span>|<span data-ttu-id="585bf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="585bf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="585bf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="585bf-110">S_OK</span></span>|<span data-ttu-id="585bf-111">`SetMaxThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="585bf-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="585bf-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="585bf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="585bf-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="585bf-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="585bf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="585bf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="585bf-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="585bf-115">The call timed out.</span></span>|  
|<span data-ttu-id="585bf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="585bf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="585bf-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="585bf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="585bf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="585bf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="585bf-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="585bf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="585bf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="585bf-120">E_FAIL</span></span>|<span data-ttu-id="585bf-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="585bf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="585bf-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="585bf-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="585bf-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="585bf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="585bf-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="585bf-124">E_NOTIMPL</span></span>|<span data-ttu-id="585bf-125">Der Host bietet keine Implementierung von `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="585bf-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="585bf-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="585bf-126">Remarks</span></span>  
 <span data-ttu-id="585bf-127">`SetMaxThreads`Stellt die CLR eine Möglichkeit, die maximale Anzahl von Threads festgelegt, die für Anforderungen an e/a-Ports verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="585bf-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="585bf-128">Ein Host möglicherweise die exklusive Kontrolle über die Größe des Threadpools, Gründen wie Implementierung, Leistung und Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="585bf-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="585bf-129">Aus diesem Grund ist der Host nicht implementieren erforderlich `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="585bf-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="585bf-130">In diesem Fall sollte ein Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="585bf-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="585bf-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="585bf-131">Requirements</span></span>  
 <span data-ttu-id="585bf-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="585bf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="585bf-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="585bf-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="585bf-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="585bf-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="585bf-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="585bf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585bf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="585bf-136">See Also</span></span>  
 [<span data-ttu-id="585bf-137">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="585bf-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="585bf-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="585bf-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
