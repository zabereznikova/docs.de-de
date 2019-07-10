---
title: IHostThreadPoolManager::GetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f4c2ea6deadeb0e9e1869a4ab064f2a948a74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749216"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="a0941-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a0941-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="a0941-103">Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in den Threadpool in der Erwartung Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="a0941-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0941-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0941-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0941-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0941-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="a0941-106">[out] Ein Zeiger auf die minimale Anzahl von Arbeitsthreads im Leerlauf, die der Host zurzeit verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a0941-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0941-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0941-107">Return Value</span></span>  
  
|<span data-ttu-id="a0941-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0941-108">HRESULT</span></span>|<span data-ttu-id="a0941-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0941-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0941-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0941-110">S_OK</span></span>|<span data-ttu-id="a0941-111">`GetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0941-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a0941-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0941-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0941-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0941-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0941-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0941-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0941-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0941-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0941-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0941-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0941-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a0941-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0941-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0941-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0941-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a0941-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0941-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0941-120">E_FAIL</span></span>|<span data-ttu-id="a0941-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0941-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0941-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0941-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0941-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a0941-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0941-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a0941-124">E_NOTIMPL</span></span>|<span data-ttu-id="a0941-125">Der Host stellt keine Implementierung von `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a0941-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0941-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0941-126">Remarks</span></span>  
 <span data-ttu-id="a0941-127">Der Host ist nicht erforderlich, um eine Implementierung der `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a0941-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="a0941-128">In diesem Fall sollte es einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a0941-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0941-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0941-129">Requirements</span></span>  
 <span data-ttu-id="a0941-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0941-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0941-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0941-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0941-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a0941-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0941-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0941-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0941-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0941-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a0941-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a0941-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="a0941-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a0941-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="a0941-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0941-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
