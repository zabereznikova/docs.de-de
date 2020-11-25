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
ms.openlocfilehash: d6f56f689a35fa025a924be0db67c893f160fc7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730733"
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="2efcd-102">IHostThreadPoolManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="2efcd-102">IHostThreadPoolManager::SetMinThreads Method</span></span>

<span data-ttu-id="2efcd-103">Legt die Mindestanzahl von Leerlaufthreads fest, die der Host in Erwartung von Anforderungen beibehalten muss.</span><span class="sxs-lookup"><span data-stu-id="2efcd-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2efcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2efcd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2efcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2efcd-105">Parameters</span></span>  

 `MinThreads`  
 <span data-ttu-id="2efcd-106">in Die neue Mindestanzahl von Threads, die vom Host gewartet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2efcd-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2efcd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2efcd-107">Return Value</span></span>  
  
|<span data-ttu-id="2efcd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2efcd-108">HRESULT</span></span>|<span data-ttu-id="2efcd-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2efcd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2efcd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2efcd-110">S_OK</span></span>|<span data-ttu-id="2efcd-111">`SetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2efcd-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2efcd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2efcd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2efcd-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2efcd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2efcd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2efcd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2efcd-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2efcd-115">The call timed out.</span></span>|  
|<span data-ttu-id="2efcd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2efcd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2efcd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2efcd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2efcd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2efcd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2efcd-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2efcd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2efcd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2efcd-120">E_FAIL</span></span>|<span data-ttu-id="2efcd-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2efcd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2efcd-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2efcd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2efcd-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2efcd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2efcd-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2efcd-124">E_NOTIMPL</span></span>|<span data-ttu-id="2efcd-125">Der Host stellt keine Implementierung von bereit `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2efcd-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2efcd-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2efcd-126">Remarks</span></span>  

 <span data-ttu-id="2efcd-127">Ein Host ist nicht erforderlich, um eine Implementierung von bereitzustellen `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="2efcd-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="2efcd-128">In diesem Fall sollte ein HRESULT-Wert von E_NOTIMPL zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2efcd-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2efcd-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2efcd-129">Requirements</span></span>  

 <span data-ttu-id="2efcd-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2efcd-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2efcd-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2efcd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2efcd-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2efcd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2efcd-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2efcd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efcd-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2efcd-134">See also</span></span>

- <xref:System.Threading.ThreadPool.SetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="2efcd-135">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="2efcd-135">GetMinThreads Method</span></span>](ihostthreadpoolmanager-getminthreads-method.md)
- [<span data-ttu-id="2efcd-136">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="2efcd-136">SetMaxThreads Method</span></span>](ihostthreadpoolmanager-setmaxthreads-method.md)
- [<span data-ttu-id="2efcd-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2efcd-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
