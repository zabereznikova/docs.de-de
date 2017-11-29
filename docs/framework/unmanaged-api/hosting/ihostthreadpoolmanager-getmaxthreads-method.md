---
title: IHostThreadPoolManager::GetMaxThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd15b1448c23785437b3dc62562b5d96abb3601c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="db76c-102">IHostThreadPoolManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="db76c-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="db76c-103">Ruft die maximale Anzahl von Threads, die der Host gleichzeitig im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="db76c-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db76c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db76c-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db76c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db76c-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="db76c-106">[out] Ein Zeiger auf die maximale Anzahl von Threads, die der Host im Threadpool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="db76c-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db76c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db76c-107">Return Value</span></span>  
  
|<span data-ttu-id="db76c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db76c-108">HRESULT</span></span>|<span data-ttu-id="db76c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db76c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db76c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="db76c-110">S_OK</span></span>|<span data-ttu-id="db76c-111">`GetMaxThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db76c-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="db76c-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="db76c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db76c-113">Die common Language Runtime (CLR (wurde nicht in einen Prozess geladen oder befindet sich in einem Zustand in der sie verwalteten Code oder der Prozess der Aufruf erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="db76c-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db76c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db76c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db76c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="db76c-115">The call timed out.</span></span>|  
|<span data-ttu-id="db76c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db76c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db76c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="db76c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db76c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db76c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db76c-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="db76c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db76c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db76c-120">E_FAIL</span></span>|<span data-ttu-id="db76c-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="db76c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db76c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="db76c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db76c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="db76c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="db76c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="db76c-124">E_NOTIMPL</span></span>|<span data-ttu-id="db76c-125">Der Host bietet keine Implementierung von `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="db76c-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db76c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db76c-126">Remarks</span></span>  
 <span data-ttu-id="db76c-127">Die CLR ruft `GetMaxThreads` zum Bestimmen der Gesamtzahl von Threads im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="db76c-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="db76c-128">Die [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) Methode ruft die Anzahl der Threads, die derzeit keine Arbeitsaufgaben verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="db76c-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="db76c-129">Alle Anforderungen über den zurückgegebenen Wert der `pdwMaxWorkerThreads` Parameter in der Warteschlange bleiben, bis die Threads verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="db76c-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="db76c-130">Wenn der Host nicht über eine Implementierung der erbringt `GetMaxThreads`, sollte einen HRESULT-Wert E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db76c-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db76c-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db76c-131">Requirements</span></span>  
 <span data-ttu-id="db76c-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db76c-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db76c-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db76c-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db76c-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db76c-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db76c-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db76c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db76c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db76c-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="db76c-137">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="db76c-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="db76c-138">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="db76c-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="db76c-139">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db76c-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
