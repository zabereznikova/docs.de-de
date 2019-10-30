---
title: IHostThreadPoolManager::SetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type:
- apiref
ms.openlocfilehash: f2d2665382559596563d9b155d2afa4d99c91ee7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141257"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="fd0f1-102">IHostThreadPoolManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="fd0f1-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="fd0f1-103">Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd0f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd0f1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd0f1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd0f1-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="fd0f1-106">in Die neue Mindestanzahl von Threads, die vom Host gewartet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd0f1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd0f1-107">Return Value</span></span>  
  
|<span data-ttu-id="fd0f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd0f1-108">HRESULT</span></span>|<span data-ttu-id="fd0f1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd0f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd0f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd0f1-110">S_OK</span></span>|<span data-ttu-id="fd0f1-111">`SetMinThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="fd0f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd0f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd0f1-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fd0f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fd0f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fd0f1-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="fd0f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fd0f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fd0f1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fd0f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fd0f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fd0f1-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fd0f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd0f1-120">E_FAIL</span></span>|<span data-ttu-id="fd0f1-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fd0f1-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fd0f1-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd0f1-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="fd0f1-124">E_NOTIMPL</span></span>|<span data-ttu-id="fd0f1-125">Der Host stellt keine Implementierung von `SetMinThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd0f1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd0f1-126">Remarks</span></span>  
 <span data-ttu-id="fd0f1-127">Ein Host ist nicht erforderlich, um eine Implementierung von `SetMinThreads`bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="fd0f1-128">In diesem Fall sollte ein HRESULT-Wert von E_NOTIMPL zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="fd0f1-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd0f1-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd0f1-129">Requirements</span></span>  
 <span data-ttu-id="fd0f1-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd0f1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd0f1-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fd0f1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd0f1-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd0f1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd0f1-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd0f1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0f1-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd0f1-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="fd0f1-135">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="fd0f1-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="fd0f1-136">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="fd0f1-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="fd0f1-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd0f1-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
