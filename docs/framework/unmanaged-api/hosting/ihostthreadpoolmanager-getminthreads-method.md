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
ms.openlocfilehash: 54dfa2741d3b4c1b2eada75ee8d214a2d0b250a0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730772"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="7a719-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="7a719-102">IHostThreadPoolManager::GetMinThreads Method</span></span>

<span data-ttu-id="7a719-103">Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host im Thread Pool in Erwartung von Anforderungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7a719-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a719-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a719-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a719-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a719-105">Parameters</span></span>  

 `MinThreads`  
 <span data-ttu-id="7a719-106">vorgenommen Ein Zeiger auf die Mindestanzahl von Arbeitsthreads im Leerlauf, die zurzeit vom Host verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="7a719-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a719-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a719-107">Return Value</span></span>  
  
|<span data-ttu-id="7a719-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a719-108">HRESULT</span></span>|<span data-ttu-id="7a719-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7a719-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a719-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a719-110">S_OK</span></span>|<span data-ttu-id="7a719-111">`GetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a719-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7a719-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a719-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a719-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7a719-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a719-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a719-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a719-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7a719-115">The call timed out.</span></span>|  
|<span data-ttu-id="7a719-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a719-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a719-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7a719-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a719-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a719-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a719-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7a719-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a719-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a719-120">E_FAIL</span></span>|<span data-ttu-id="7a719-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a719-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a719-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="7a719-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a719-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7a719-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a719-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7a719-124">E_NOTIMPL</span></span>|<span data-ttu-id="7a719-125">Der Host stellt keine Implementierung von bereit `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="7a719-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a719-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a719-126">Remarks</span></span>  

 <span data-ttu-id="7a719-127">Der Host muss keine Implementierung von bereitstellen `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="7a719-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="7a719-128">In diesem Fall sollte ein HRESULT-Wert von E_NOTIMPL zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7a719-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a719-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7a719-129">Requirements</span></span>  

 <span data-ttu-id="7a719-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a719-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a719-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7a719-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a719-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7a719-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a719-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a719-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a719-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7a719-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="7a719-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="7a719-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="7a719-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="7a719-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="7a719-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a719-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
