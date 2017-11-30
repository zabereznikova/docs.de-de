---
title: IHostThreadPoolManager::GetMinThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8ee8adfb93a3e098bb6df69ad00202118bc1731e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="ead97-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="ead97-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="ead97-103">Ruft die minimale Anzahl von Threads im Leerlauf, die der Host im Threadpool in Vorwegnahme Ihrer Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="ead97-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ead97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ead97-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ead97-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ead97-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="ead97-106">[out] Ein Zeiger auf die minimale Anzahl von Arbeitsthreads im Leerlauf, die der Host zurzeit verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ead97-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ead97-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ead97-107">Return Value</span></span>  
  
|<span data-ttu-id="ead97-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ead97-108">HRESULT</span></span>|<span data-ttu-id="ead97-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ead97-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ead97-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ead97-110">S_OK</span></span>|<span data-ttu-id="ead97-111">`GetMinThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ead97-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ead97-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ead97-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ead97-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ead97-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ead97-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ead97-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ead97-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ead97-115">The call timed out.</span></span>|  
|<span data-ttu-id="ead97-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ead97-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ead97-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ead97-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ead97-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ead97-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ead97-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ead97-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ead97-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ead97-120">E_FAIL</span></span>|<span data-ttu-id="ead97-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ead97-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ead97-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ead97-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ead97-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ead97-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ead97-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ead97-124">E_NOTIMPL</span></span>|<span data-ttu-id="ead97-125">Der Host bietet keine Implementierung von `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="ead97-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ead97-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ead97-126">Remarks</span></span>  
 <span data-ttu-id="ead97-127">Der Host ist nicht erforderlich, um eine Implementierung bereitstellen `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="ead97-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="ead97-128">In diesem Fall sollte er einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ead97-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ead97-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ead97-129">Requirements</span></span>  
 <span data-ttu-id="ead97-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ead97-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ead97-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ead97-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ead97-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ead97-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ead97-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ead97-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ead97-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ead97-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="ead97-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="ead97-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="ead97-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="ead97-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="ead97-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ead97-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
