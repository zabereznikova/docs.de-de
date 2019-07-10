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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c79f18c1deec4183a5a736c5acf88e9a1fd8021
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749093"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="c514d-102">IHostThreadPoolManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="c514d-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="c514d-103">Legt die minimale Anzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="c514d-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c514d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c514d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c514d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c514d-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="c514d-106">[in] Die neue minimale Anzahl von Threads, die der Host verwalten muss.</span><span class="sxs-lookup"><span data-stu-id="c514d-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c514d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c514d-107">Return Value</span></span>  
  
|<span data-ttu-id="c514d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c514d-108">HRESULT</span></span>|<span data-ttu-id="c514d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c514d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c514d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c514d-110">S_OK</span></span>|<span data-ttu-id="c514d-111">`SetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c514d-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c514d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c514d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c514d-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c514d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c514d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c514d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c514d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c514d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c514d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c514d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c514d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c514d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c514d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c514d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c514d-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c514d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c514d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c514d-120">E_FAIL</span></span>|<span data-ttu-id="c514d-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c514d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c514d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c514d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c514d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c514d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c514d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c514d-124">E_NOTIMPL</span></span>|<span data-ttu-id="c514d-125">Der Host stellt keine Implementierung von `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c514d-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c514d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c514d-126">Remarks</span></span>  
 <span data-ttu-id="c514d-127">Ein Host ist nicht erforderlich, um eine Implementierung der `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="c514d-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="c514d-128">In diesem Fall sollte es einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c514d-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c514d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c514d-129">Requirements</span></span>  
 <span data-ttu-id="c514d-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c514d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c514d-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c514d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c514d-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c514d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c514d-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c514d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c514d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c514d-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c514d-135">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="c514d-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="c514d-136">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="c514d-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="c514d-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c514d-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
