---
title: IHostIoCompletionManager::GetMaxThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e7df4acd435c767a1d0c3ae4484a236359cfb38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="65f05-102">IHostIoCompletionManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="65f05-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="65f05-103">Ruft die maximale Anzahl von Threads, die der Host reserviert werden soll, kann e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="65f05-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65f05-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65f05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65f05-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="65f05-106">[out] Ein Zeiger auf die maximale Anzahl von Threads im Threadpool, den der Host für e/a-Anforderungen zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="65f05-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65f05-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="65f05-107">Return Value</span></span>  
  
|<span data-ttu-id="65f05-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65f05-108">HRESULT</span></span>|<span data-ttu-id="65f05-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65f05-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65f05-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="65f05-110">S_OK</span></span>|<span data-ttu-id="65f05-111">`GetMaxThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="65f05-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="65f05-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="65f05-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65f05-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="65f05-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65f05-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65f05-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65f05-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="65f05-115">The call timed out.</span></span>|  
|<span data-ttu-id="65f05-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65f05-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65f05-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="65f05-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65f05-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65f05-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65f05-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="65f05-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65f05-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65f05-120">E_FAIL</span></span>|<span data-ttu-id="65f05-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="65f05-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65f05-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="65f05-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65f05-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="65f05-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="65f05-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="65f05-124">E_NOTIMPL</span></span>|<span data-ttu-id="65f05-125">Der Host bietet keine Implementierung von `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="65f05-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65f05-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65f05-126">Remarks</span></span>  
 <span data-ttu-id="65f05-127">Ein Host sollten exklusive Kontrolle über die Anzahl der Threads, die zum Verarbeiten von e/a-Anforderungen, z. B. Implementierung, Leistung oder Skalierbarkeit Gründen zugeteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="65f05-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="65f05-128">Aus diesem Grund ist der Host nicht implementieren erforderlich `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="65f05-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="65f05-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="65f05-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65f05-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65f05-130">Requirements</span></span>  
 <span data-ttu-id="65f05-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f05-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f05-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65f05-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65f05-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="65f05-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65f05-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65f05-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f05-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65f05-135">See Also</span></span>  
 [<span data-ttu-id="65f05-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65f05-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="65f05-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65f05-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
