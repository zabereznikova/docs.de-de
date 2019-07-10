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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea09b9d66a288b0616870d971e5063bab83cda0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780791"
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="d373f-102">IHostIoCompletionManager::SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="d373f-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="d373f-103">Legt die maximale Anzahl von Threads, die der Host-Bereitstellung e/a-Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="d373f-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d373f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d373f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d373f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d373f-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="d373f-106">[in] Die maximale Anzahl von Threads für e/a-Anforderungen-Manual.</span><span class="sxs-lookup"><span data-stu-id="d373f-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d373f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d373f-107">Return Value</span></span>  
  
|<span data-ttu-id="d373f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d373f-108">HRESULT</span></span>|<span data-ttu-id="d373f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d373f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d373f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d373f-110">S_OK</span></span>|<span data-ttu-id="d373f-111">`SetMaxThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d373f-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="d373f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d373f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d373f-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d373f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d373f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d373f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d373f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d373f-115">The call timed out.</span></span>|  
|<span data-ttu-id="d373f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d373f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d373f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d373f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d373f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d373f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d373f-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d373f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d373f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d373f-120">E_FAIL</span></span>|<span data-ttu-id="d373f-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d373f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d373f-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d373f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d373f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d373f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d373f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d373f-124">E_NOTIMPL</span></span>|<span data-ttu-id="d373f-125">Der Host stellt keine Implementierung von `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="d373f-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d373f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d373f-126">Remarks</span></span>  
 <span data-ttu-id="d373f-127">`SetMaxThreads` Stellt die CLR mit der Möglichkeit, legen Sie die maximale Anzahl von Threads, die Anforderungen für e/a-Ports verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d373f-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="d373f-128">Ein Host möglicherweise exklusive Kontrolle über die Größe des Threadpools, beispielsweise die Implementierung, Leistung und Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d373f-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="d373f-129">Aus diesem Grund der Host ist nicht erforderlich, implementiert `SetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="d373f-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="d373f-130">In diesem Fall sollte ein Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d373f-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d373f-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d373f-131">Requirements</span></span>  
 <span data-ttu-id="d373f-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d373f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d373f-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d373f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d373f-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d373f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d373f-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d373f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d373f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d373f-136">See also</span></span>

- [<span data-ttu-id="d373f-137">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d373f-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d373f-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d373f-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
