---
title: IHostThreadPoolManager::GetAvailableThreads-Methoden
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
ms.openlocfilehash: 21449d9365e6260267d3c79f384f6136ce894821
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122095"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="1fedc-102">IHostThreadPoolManager::GetAvailableThreads-Methoden</span><span class="sxs-lookup"><span data-stu-id="1fedc-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="1fedc-103">Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1fedc-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fedc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1fedc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fedc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1fedc-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="1fedc-106">vorgenommen Ein Zeiger auf die Anzahl der Threads im Thread Pool, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1fedc-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fedc-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1fedc-107">Return Value</span></span>  
  
|<span data-ttu-id="1fedc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1fedc-108">HRESULT</span></span>|<span data-ttu-id="1fedc-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1fedc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fedc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fedc-110">S_OK</span></span>|<span data-ttu-id="1fedc-111">`GetAvailableThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1fedc-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1fedc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1fedc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1fedc-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1fedc-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1fedc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1fedc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1fedc-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1fedc-115">The call timed out.</span></span>|  
|<span data-ttu-id="1fedc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1fedc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1fedc-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1fedc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1fedc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1fedc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1fedc-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1fedc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1fedc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1fedc-120">E_FAIL</span></span>|<span data-ttu-id="1fedc-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1fedc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1fedc-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fedc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1fedc-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1fedc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1fedc-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1fedc-124">E_NOTIMPL</span></span>|<span data-ttu-id="1fedc-125">Der Host stellt keine Implementierung von `GetAvailableThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="1fedc-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fedc-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1fedc-126">Remarks</span></span>  
 <span data-ttu-id="1fedc-127">Wenn der Host keine Implementierung von `GetAvailableThreads`bereitstellt, sollte er den HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1fedc-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fedc-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1fedc-128">Requirements</span></span>  
 <span data-ttu-id="1fedc-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fedc-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fedc-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1fedc-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1fedc-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1fedc-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1fedc-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fedc-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fedc-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1fedc-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1fedc-134">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1fedc-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
