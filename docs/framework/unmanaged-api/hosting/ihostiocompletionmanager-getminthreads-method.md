---
title: IHostIoCompletionManager::GetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0ac90729e4885f0b76e1cd78ec31a0e2e251452
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497807"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="e5e55-102">IHostIoCompletionManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="e5e55-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="e5e55-103">Ruft die minimale Anzahl von Threads, die der Host zum Verarbeiten von e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e5e55-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5e55-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5e55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5e55-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="e5e55-106">[out] Ein Zeiger auf die minimale Anzahl von Threads, die der Host für Prozess e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e5e55-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5e55-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e5e55-107">Return Value</span></span>  
  
|<span data-ttu-id="e5e55-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5e55-108">HRESULT</span></span>|<span data-ttu-id="e5e55-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5e55-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5e55-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5e55-110">S_OK</span></span>|<span data-ttu-id="e5e55-111">`GetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5e55-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e5e55-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5e55-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5e55-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e5e55-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e5e55-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5e55-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5e55-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e5e55-115">The call timed out.</span></span>|  
|<span data-ttu-id="e5e55-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5e55-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5e55-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e5e55-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5e55-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5e55-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5e55-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e5e55-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5e55-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5e55-120">E_FAIL</span></span>|<span data-ttu-id="e5e55-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e5e55-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5e55-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5e55-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5e55-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e5e55-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e5e55-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e5e55-124">E_NOTIMPL</span></span>|<span data-ttu-id="e5e55-125">Der Host stellt keine Implementierung von `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="e5e55-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5e55-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5e55-126">Remarks</span></span>  
 <span data-ttu-id="e5e55-127">Ein Host sollten die exklusive Kontrolle über die Anzahl der Threads zugewiesen, die e/a-Anforderungen verarbeiten, beispielsweise die Implementierung, Leistung und Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="e5e55-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e5e55-128">Aus diesem Grund der Host ist nicht erforderlich, implementiert `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="e5e55-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="e5e55-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e5e55-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5e55-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5e55-130">Requirements</span></span>  
 <span data-ttu-id="e5e55-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5e55-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e55-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e5e55-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5e55-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e5e55-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5e55-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e55-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e55-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5e55-135">See also</span></span>
- [<span data-ttu-id="e5e55-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5e55-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="e5e55-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5e55-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
