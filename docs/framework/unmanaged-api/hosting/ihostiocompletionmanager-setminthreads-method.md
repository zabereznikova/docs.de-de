---
title: IHostIoCompletionManager::SetMinThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1bd64554278fe3c684fadf95f66ce15920827908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="a476f-102">IHostIoCompletionManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a476f-102">IHostIoCompletionManager::SetMinThreads Method</span></span>
<span data-ttu-id="a476f-103">Legt die Mindestanzahl von Threads, die der Host reserviert werden soll, sollte auf e/a-Abschluss fest.</span><span class="sxs-lookup"><span data-stu-id="a476f-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a476f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a476f-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a476f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a476f-105">Parameters</span></span>  
 `dwMinIoCompletionThreads`  
 <span data-ttu-id="a476f-106">[in] Die minimale Anzahl von e/a-Abschlussthreads, die der Host erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a476f-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a476f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a476f-107">Return Value</span></span>  
  
|<span data-ttu-id="a476f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a476f-108">HRESULT</span></span>|<span data-ttu-id="a476f-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a476f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a476f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a476f-110">S_OK</span></span>|<span data-ttu-id="a476f-111">`SetMinThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a476f-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="a476f-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="a476f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a476f-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a476f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a476f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a476f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a476f-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a476f-115">The call timed out.</span></span>|  
|<span data-ttu-id="a476f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a476f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a476f-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a476f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a476f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a476f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a476f-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a476f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a476f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a476f-120">E_FAIL</span></span>|<span data-ttu-id="a476f-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a476f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a476f-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a476f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a476f-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a476f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a476f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="a476f-124">E_NOTIMPL</span></span>|<span data-ttu-id="a476f-125">Der Host bietet keine Implementierung von `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a476f-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a476f-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a476f-126">Remarks</span></span>  
 <span data-ttu-id="a476f-127">Ein Host sollten exklusive Kontrolle über die Anzahl der Threads, die zum Verarbeiten von e/a-Anforderungen, z. B. Implementierung, Leistung oder Skalierbarkeit Gründen zugeteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="a476f-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="a476f-128">Aus diesem Grund ist der Host nicht implementieren erforderlich `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="a476f-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="a476f-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a476f-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a476f-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a476f-130">Requirements</span></span>  
 <span data-ttu-id="a476f-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a476f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a476f-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a476f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a476f-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a476f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a476f-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a476f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a476f-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a476f-135">See Also</span></span>  
 [<span data-ttu-id="a476f-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a476f-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="a476f-137">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="a476f-137">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="a476f-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a476f-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
