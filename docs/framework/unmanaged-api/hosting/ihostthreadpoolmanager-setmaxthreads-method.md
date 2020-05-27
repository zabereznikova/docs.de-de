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
ms.openlocfilehash: 53d42afda6668acc6462c419fcefd6bc1435a34c
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842451"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="6897a-102">IHostThreadPoolManager::SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="6897a-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="6897a-103">Legt die maximale Anzahl von Threads fest, die der Host im Thread Pool verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="6897a-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6897a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6897a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6897a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6897a-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="6897a-106">Die maximale Anzahl der Arbeitsthreads im Threadpool.</span><span class="sxs-lookup"><span data-stu-id="6897a-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6897a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6897a-107">Return Value</span></span>  
  
|<span data-ttu-id="6897a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6897a-108">HRESULT</span></span>|<span data-ttu-id="6897a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6897a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6897a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6897a-110">S_OK</span></span>|<span data-ttu-id="6897a-111">`SetMaxThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6897a-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="6897a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6897a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6897a-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6897a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6897a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6897a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6897a-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="6897a-115">The call timed out.</span></span>|  
|<span data-ttu-id="6897a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6897a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6897a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6897a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6897a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6897a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6897a-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="6897a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6897a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6897a-120">E_FAIL</span></span>|<span data-ttu-id="6897a-121">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6897a-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6897a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="6897a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6897a-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6897a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6897a-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6897a-124">E_NOTIMPL</span></span>|<span data-ttu-id="6897a-125">Der Host stellt keine Implementierung von bereit `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="6897a-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6897a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6897a-126">Remarks</span></span>  
 <span data-ttu-id="6897a-127">Ein Host ist nicht erforderlich, damit die CLR die Größe des Thread Pools konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="6897a-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="6897a-128">Einige Hosts möchten möglicherweise eine exklusive Kontrolle über den Thread Pool haben, wie z. b. Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="6897a-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="6897a-129">In diesem Fall sollte ein Host den HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6897a-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6897a-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6897a-130">Requirements</span></span>  
 <span data-ttu-id="6897a-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6897a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6897a-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6897a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6897a-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6897a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6897a-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6897a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6897a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6897a-135">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="6897a-136">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="6897a-136">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="6897a-137">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="6897a-137">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="6897a-138">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6897a-138">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
