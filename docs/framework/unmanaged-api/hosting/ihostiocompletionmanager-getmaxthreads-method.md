---
title: IHostIoCompletionManager::GetMaxThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8544466edcaca1198d7a7ca92a3f9b9a16847193
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442482"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="71655-102">IHostIoCompletionManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="71655-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="71655-103">Ruft die maximale Anzahl von Threads, die der Host reserviert werden soll, kann e/a-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="71655-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71655-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71655-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71655-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71655-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="71655-106">[out] Ein Zeiger auf die maximale Anzahl von Threads im Threadpool, den der Host für e/a-Anforderungen zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="71655-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71655-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="71655-107">Return Value</span></span>  
  
|<span data-ttu-id="71655-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71655-108">HRESULT</span></span>|<span data-ttu-id="71655-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71655-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71655-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="71655-110">S_OK</span></span>|<span data-ttu-id="71655-111">`GetMaxThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="71655-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="71655-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="71655-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71655-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="71655-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71655-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71655-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71655-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="71655-115">The call timed out.</span></span>|  
|<span data-ttu-id="71655-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71655-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71655-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="71655-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71655-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71655-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71655-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="71655-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71655-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71655-120">E_FAIL</span></span>|<span data-ttu-id="71655-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="71655-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71655-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="71655-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71655-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="71655-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71655-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="71655-124">E_NOTIMPL</span></span>|<span data-ttu-id="71655-125">Der Host bietet keine Implementierung von `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="71655-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71655-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71655-126">Remarks</span></span>  
 <span data-ttu-id="71655-127">Ein Host sollten exklusive Kontrolle über die Anzahl der Threads, die zum Verarbeiten von e/a-Anforderungen, z. B. Implementierung, Leistung oder Skalierbarkeit Gründen zugeteilt werden können.</span><span class="sxs-lookup"><span data-stu-id="71655-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="71655-128">Aus diesem Grund ist der Host nicht implementieren erforderlich `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="71655-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="71655-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="71655-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71655-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71655-130">Requirements</span></span>  
 <span data-ttu-id="71655-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71655-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71655-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71655-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71655-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71655-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71655-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71655-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71655-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71655-135">See Also</span></span>  
 [<span data-ttu-id="71655-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71655-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="71655-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71655-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
