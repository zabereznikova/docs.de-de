---
title: IHostThreadPoolManager::GetAvailableThreads-Methoden
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetAvailableThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11cd8de264a332cd553ad44a35355bf45039ab84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="9a80d-102">IHostThreadPoolManager::GetAvailableThreads-Methoden</span><span class="sxs-lookup"><span data-stu-id="9a80d-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="9a80d-103">Ruft die Anzahl der Threads im Threadpool, der von Arbeitselementen derzeit nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a80d-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a80d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a80d-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a80d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a80d-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="9a80d-106">[out] Ein Zeiger auf die Anzahl der Threads im Threadpool, die von Arbeitselementen derzeit nicht durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9a80d-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a80d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a80d-107">Return Value</span></span>  
  
|<span data-ttu-id="9a80d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a80d-108">HRESULT</span></span>|<span data-ttu-id="9a80d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a80d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a80d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a80d-110">S_OK</span></span>|<span data-ttu-id="9a80d-111">`GetAvailableThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a80d-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9a80d-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="9a80d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a80d-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9a80d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a80d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a80d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a80d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9a80d-115">The call timed out.</span></span>|  
|<span data-ttu-id="9a80d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a80d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a80d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9a80d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a80d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a80d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a80d-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9a80d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a80d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a80d-120">E_FAIL</span></span>|<span data-ttu-id="9a80d-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="9a80d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a80d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="9a80d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a80d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9a80d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9a80d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9a80d-124">E_NOTIMPL</span></span>|<span data-ttu-id="9a80d-125">Der Host bietet keine Implementierung von `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="9a80d-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a80d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a80d-126">Remarks</span></span>  
 <span data-ttu-id="9a80d-127">Wenn der Host nicht über eine Implementierung der erbringt `GetAvailableThreads`, sollte einen HRESULT-Wert E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a80d-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a80d-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a80d-128">Requirements</span></span>  
 <span data-ttu-id="9a80d-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a80d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a80d-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a80d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a80d-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9a80d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a80d-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a80d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a80d-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a80d-133">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="9a80d-134">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a80d-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
