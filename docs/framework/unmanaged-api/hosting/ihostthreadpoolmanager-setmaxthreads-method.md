---
title: IHostThreadPoolManager::SetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0df8d11bba870dfec880401064ec3f78f5f04e1f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961277"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="518d6-102">IHostThreadPoolManager::SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="518d6-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="518d6-103">Legt die maximale Anzahl von Threads, die der Host im Threadpool der Warteschleife hinzu verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="518d6-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="518d6-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="518d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="518d6-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="518d6-106">Die maximale Anzahl der Arbeitsthreads im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="518d6-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="518d6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="518d6-107">Return Value</span></span>  
  
|<span data-ttu-id="518d6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="518d6-108">HRESULT</span></span>|<span data-ttu-id="518d6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="518d6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="518d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="518d6-110">S_OK</span></span>|<span data-ttu-id="518d6-111">`SetMaxThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="518d6-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="518d6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="518d6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="518d6-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="518d6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="518d6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="518d6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="518d6-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="518d6-115">The call timed out.</span></span>|  
|<span data-ttu-id="518d6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="518d6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="518d6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="518d6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="518d6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="518d6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="518d6-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="518d6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="518d6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="518d6-120">E_FAIL</span></span>|<span data-ttu-id="518d6-121">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="518d6-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="518d6-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="518d6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="518d6-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="518d6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="518d6-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="518d6-124">E_NOTIMPL</span></span>|<span data-ttu-id="518d6-125">Der Host stellt keine Implementierung von `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="518d6-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="518d6-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="518d6-126">Remarks</span></span>  
 <span data-ttu-id="518d6-127">Ein Host ist nicht erforderlich, um die CLR so konfigurieren Sie die Größe des Threadpools zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="518d6-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="518d6-128">Einige Hosts sollten die exklusive Kontrolle über den Threadpool beispielsweise-Implementierung, Leistung und Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="518d6-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="518d6-129">In diesem Fall sollte ein Host einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="518d6-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="518d6-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="518d6-130">Requirements</span></span>  
 <span data-ttu-id="518d6-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="518d6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518d6-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="518d6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="518d6-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="518d6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="518d6-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518d6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518d6-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="518d6-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="518d6-136">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="518d6-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="518d6-137">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="518d6-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="518d6-138">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="518d6-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
