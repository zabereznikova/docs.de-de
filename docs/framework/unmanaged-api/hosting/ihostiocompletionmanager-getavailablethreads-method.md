---
title: IHostIoCompletionManager::GetAvailableThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ef25267f6af5d1f8503825e2784383a0eb241e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535533"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="1933b-102">IHostIoCompletionManager::GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1933b-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="1933b-103">Ruft die Anzahl der e/a-Abschlussthreads, der die Gesamtzahl der Threads, die vom Host verwaltet, die derzeit keine Anforderungen bedient werden.</span><span class="sxs-lookup"><span data-stu-id="1933b-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1933b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1933b-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1933b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1933b-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="1933b-106">[out] Ein Zeiger auf die Anzahl der e/a-Abschlussthreads vom Host verwaltet, die derzeit für dienstanforderungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1933b-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1933b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1933b-107">Return Value</span></span>  
  
|<span data-ttu-id="1933b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1933b-108">HRESULT</span></span>|<span data-ttu-id="1933b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1933b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1933b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1933b-110">S_OK</span></span>|<span data-ttu-id="1933b-111">`GetAvailableThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1933b-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1933b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1933b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1933b-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1933b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1933b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1933b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1933b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1933b-115">The call timed out.</span></span>|  
|<span data-ttu-id="1933b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1933b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1933b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1933b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1933b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1933b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1933b-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1933b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1933b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1933b-120">E_FAIL</span></span>|<span data-ttu-id="1933b-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1933b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1933b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1933b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1933b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1933b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1933b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1933b-124">E_NOTIMPL</span></span>|<span data-ttu-id="1933b-125">Der Host stellt keine Implementierung von `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="1933b-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1933b-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1933b-126">Remarks</span></span>  
 <span data-ttu-id="1933b-127">Ein Host sollten exklusive Kontrolle über die Größe der e/a-Abschluss Threadpool der Warteschleife hinzu, beispielsweise die Implementierung, Leistung und Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="1933b-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="1933b-128">Der Host ist daher nicht erforderlich, implementieren `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="1933b-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="1933b-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1933b-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1933b-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1933b-130">Requirements</span></span>  
 <span data-ttu-id="1933b-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1933b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1933b-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1933b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1933b-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1933b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1933b-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1933b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1933b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1933b-135">See also</span></span>
- [<span data-ttu-id="1933b-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1933b-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1933b-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1933b-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
