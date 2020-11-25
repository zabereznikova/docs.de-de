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
ms.openlocfilehash: 64d5ba9ad5557f99b175c277d48003529d77861c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730798"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="c5708-102">IHostThreadPoolManager::GetAvailableThreads-Methoden</span><span class="sxs-lookup"><span data-stu-id="c5708-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="c5708-103">Ruft die Anzahl der Threads im Thread Pool ab, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c5708-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5708-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5708-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5708-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5708-105">Parameters</span></span>  

 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="c5708-106">vorgenommen Ein Zeiger auf die Anzahl der Threads im Thread Pool, die derzeit keine Arbeitselemente verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c5708-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5708-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c5708-107">Return Value</span></span>  
  
|<span data-ttu-id="c5708-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5708-108">HRESULT</span></span>|<span data-ttu-id="c5708-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c5708-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c5708-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c5708-110">S_OK</span></span>|<span data-ttu-id="c5708-111">`GetAvailableThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c5708-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="c5708-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c5708-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c5708-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c5708-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c5708-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c5708-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c5708-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c5708-115">The call timed out.</span></span>|  
|<span data-ttu-id="c5708-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c5708-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c5708-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c5708-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c5708-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c5708-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c5708-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c5708-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c5708-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c5708-120">E_FAIL</span></span>|<span data-ttu-id="c5708-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c5708-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c5708-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c5708-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c5708-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c5708-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c5708-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="c5708-124">E_NOTIMPL</span></span>|<span data-ttu-id="c5708-125">Der Host stellt keine Implementierung von bereit `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="c5708-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5708-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5708-126">Remarks</span></span>  

 <span data-ttu-id="c5708-127">Wenn der Host keine Implementierung von bereitstellt `GetAvailableThreads` , sollte er den HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c5708-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5708-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c5708-128">Requirements</span></span>  

 <span data-ttu-id="c5708-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5708-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5708-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c5708-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c5708-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c5708-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5708-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5708-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5708-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5708-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="c5708-134">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5708-134">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
