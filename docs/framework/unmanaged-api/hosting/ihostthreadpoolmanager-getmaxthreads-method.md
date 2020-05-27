---
title: IHostThreadPoolManager::GetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: efbfa310c90f48c99219cb185f090a1b854949a2
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842282"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="1b4d1-102">IHostThreadPoolManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1b4d1-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="1b4d1-103">Ruft die maximale Anzahl von Threads ab, die der Host gleichzeitig im Thread Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4d1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b4d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b4d1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b4d1-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="1b4d1-106">vorgenommen Ein Zeiger auf die maximale Anzahl von Threads, die der Host im Thread Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b4d1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b4d1-107">Return Value</span></span>  
  
|<span data-ttu-id="1b4d1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b4d1-108">HRESULT</span></span>|<span data-ttu-id="1b4d1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1b4d1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b4d1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b4d1-110">S_OK</span></span>|<span data-ttu-id="1b4d1-111">`GetMaxThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1b4d1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b4d1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b4d1-113">Die Common Language Runtime (CLR () wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b4d1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b4d1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b4d1-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-115">The call timed out.</span></span>|  
|<span data-ttu-id="1b4d1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b4d1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b4d1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b4d1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b4d1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b4d1-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b4d1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b4d1-120">E_FAIL</span></span>|<span data-ttu-id="1b4d1-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b4d1-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b4d1-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b4d1-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1b4d1-124">E_NOTIMPL</span></span>|<span data-ttu-id="1b4d1-125">Der Host stellt keine Implementierung von bereit `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="1b4d1-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b4d1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b4d1-126">Remarks</span></span>  
 <span data-ttu-id="1b4d1-127">Die CLR ruft `GetMaxThreads` auf, um die Gesamtanzahl der Threads im Thread Pool zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="1b4d1-128">Die [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) -Methode ruft die Anzahl der Threads ab, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-128">The [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="1b4d1-129">Alle Anforderungen oberhalb des zurückgegebenen Werts des- `pdwMaxWorkerThreads` Parameters bleiben in der Warteschlange, bis die Threads verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="1b4d1-130">Wenn der Host keine Implementierung von bereitstellt `GetMaxThreads` , sollte er den HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b4d1-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b4d1-131">Requirements</span></span>  
 <span data-ttu-id="1b4d1-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b4d1-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b4d1-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1b4d1-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b4d1-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1b4d1-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b4d1-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b4d1-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4d1-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b4d1-136">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="1b4d1-137">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1b4d1-137">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="1b4d1-138">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1b4d1-138">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="1b4d1-139">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b4d1-139">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
