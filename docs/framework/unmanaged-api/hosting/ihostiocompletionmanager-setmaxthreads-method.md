---
title: IHostIoCompletionManager::SetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
ms.openlocfilehash: 3cb001db74587beb5417bf57738c5efb9a274591
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724818"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="20b99-102">IHostIoCompletionManager::SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="20b99-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>

<span data-ttu-id="20b99-103">Legt die maximale Anzahl von Threads fest, die der Host Dienst-e/a-Anforderungen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="20b99-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20b99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20b99-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20b99-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20b99-105">Parameters</span></span>  

 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="20b99-106">in Die maximale Anzahl von Threads für e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="20b99-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20b99-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20b99-107">Return Value</span></span>  
  
|<span data-ttu-id="20b99-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20b99-108">HRESULT</span></span>|<span data-ttu-id="20b99-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20b99-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20b99-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="20b99-110">S_OK</span></span>|<span data-ttu-id="20b99-111">`SetMaxThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20b99-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="20b99-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20b99-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20b99-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="20b99-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20b99-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20b99-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20b99-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="20b99-115">The call timed out.</span></span>|  
|<span data-ttu-id="20b99-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20b99-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20b99-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="20b99-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20b99-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20b99-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20b99-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="20b99-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20b99-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20b99-120">E_FAIL</span></span>|<span data-ttu-id="20b99-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="20b99-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20b99-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="20b99-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20b99-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="20b99-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="20b99-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="20b99-124">E_NOTIMPL</span></span>|<span data-ttu-id="20b99-125">Der Host stellt keine Implementierung von bereit `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="20b99-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20b99-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20b99-126">Remarks</span></span>  

 <span data-ttu-id="20b99-127">`SetMaxThreads` bietet der CLR die Möglichkeit, die maximale Anzahl von Threads festzulegen, die für Service Requests auf e/a-Ports verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="20b99-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="20b99-128">Ein Host benötigt möglicherweise exklusive Kontrolle über die Größe des Thread Pools, wie z. b. Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="20b99-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="20b99-129">Aus diesem Grund ist es nicht erforderlich, dass der Host implementiert `SetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="20b99-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="20b99-130">In diesem Fall sollte ein Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="20b99-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20b99-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20b99-131">Requirements</span></span>  

 <span data-ttu-id="20b99-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20b99-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20b99-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="20b99-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20b99-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20b99-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20b99-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20b99-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b99-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20b99-136">See also</span></span>

- [<span data-ttu-id="20b99-137">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20b99-137">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="20b99-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20b99-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
