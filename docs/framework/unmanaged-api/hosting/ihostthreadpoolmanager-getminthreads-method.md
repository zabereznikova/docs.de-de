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
ms.openlocfilehash: a05cfb43b5b4a328d22c4df04049a7fa156ca080
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841931"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="a649e-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a649e-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="a649e-103">Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host im Thread Pool in Erwartung von Anforderungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a649e-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a649e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a649e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a649e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a649e-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="a649e-106">vorgenommen Ein Zeiger auf die Mindestanzahl von Arbeitsthreads im Leerlauf, die zurzeit vom Host verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="a649e-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a649e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a649e-107">Return Value</span></span>  
  
|<span data-ttu-id="a649e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a649e-108">HRESULT</span></span>|<span data-ttu-id="a649e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a649e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a649e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a649e-110">S_OK</span></span>|<span data-ttu-id="a649e-111">`GetMinThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a649e-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a649e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a649e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a649e-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="a649e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a649e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a649e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a649e-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="a649e-115">The call timed out.</span></span>|  
|<span data-ttu-id="a649e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a649e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a649e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a649e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a649e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a649e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a649e-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="a649e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a649e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a649e-120">E_FAIL</span></span>|<span data-ttu-id="a649e-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a649e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a649e-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="a649e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a649e-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a649e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a649e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a649e-124">E_NOTIMPL</span></span>|<span data-ttu-id="a649e-125">Der Host stellt keine Implementierung von bereit `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="a649e-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a649e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a649e-126">Remarks</span></span>  
 <span data-ttu-id="a649e-127">Der Host muss keine Implementierung von bereitstellen `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="a649e-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="a649e-128">In diesem Fall sollte ein HRESULT-Wert von E_NOTIMPL zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a649e-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a649e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a649e-129">Requirements</span></span>  
 <span data-ttu-id="a649e-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a649e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a649e-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="a649e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a649e-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a649e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a649e-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a649e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a649e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a649e-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="a649e-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a649e-135">GetMaxThreads Method</span></span>](ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="a649e-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a649e-136">SetMinThreads Method</span></span>](ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="a649e-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a649e-137">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
