---
title: IHostIoCompletionManager::SetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a966c1827f868c51b0a4dce93e9f536e8ae0e51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659240"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="cfca4-102">IHostIoCompletionManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="cfca4-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="cfca4-103">Legt die minimale Anzahl von Threads, die der Host-Manual sollte auf e/a-Abschluss fest.</span><span class="sxs-lookup"><span data-stu-id="cfca4-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfca4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfca4-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cfca4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cfca4-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="cfca4-106">[in] Die minimale Anzahl von e/a-Abschlussthreads, die der Host erstellen soll.</span><span class="sxs-lookup"><span data-stu-id="cfca4-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfca4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cfca4-107">Return Value</span></span>  
  
|<span data-ttu-id="cfca4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cfca4-108">HRESULT</span></span>|<span data-ttu-id="cfca4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfca4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfca4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cfca4-110">S_OK</span></span>|<span data-ttu-id="cfca4-111">`SetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cfca4-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="cfca4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cfca4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cfca4-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cfca4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cfca4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cfca4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cfca4-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cfca4-115">The call timed out.</span></span>|  
|<span data-ttu-id="cfca4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cfca4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cfca4-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cfca4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cfca4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cfca4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cfca4-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="cfca4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cfca4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cfca4-120">E_FAIL</span></span>|<span data-ttu-id="cfca4-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cfca4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cfca4-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cfca4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cfca4-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cfca4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cfca4-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cfca4-124">E_NOTIMPL</span></span>|<span data-ttu-id="cfca4-125">Der Host stellt keine Implementierung von `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cfca4-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfca4-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfca4-126">Remarks</span></span>  
 <span data-ttu-id="cfca4-127">Ein Host sollten exklusive Kontrolle über die Anzahl der Threads, die zugewiesen werden kann, um e/a-Anforderungen, beispielsweise die Implementierung, Leistung und Skalierbarkeit zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cfca4-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="cfca4-128">Aus diesem Grund der Host ist nicht erforderlich, implementiert `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="cfca4-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="cfca4-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="cfca4-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfca4-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cfca4-130">Requirements</span></span>  
 <span data-ttu-id="cfca4-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfca4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfca4-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cfca4-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cfca4-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cfca4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfca4-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfca4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfca4-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfca4-135">See also</span></span>
- [<span data-ttu-id="cfca4-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfca4-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="cfca4-137">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="cfca4-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="cfca4-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cfca4-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
