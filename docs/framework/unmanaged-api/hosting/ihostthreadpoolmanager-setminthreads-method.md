---
title: IHostThreadPoolManager::SetMinThreads-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fccfeb616b7a1c6d797ad9d91f47e696c4f3599
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="af759-102">IHostThreadPoolManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="af759-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="af759-103">Legt die Mindestanzahl von Threads im Leerlauf, die der Host zu verwalten, muss in der Erwartung Anforderungen fest.</span><span class="sxs-lookup"><span data-stu-id="af759-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af759-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af759-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af759-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af759-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="af759-106">[in] Die neue Mindestanzahl von Threads, die der Host verwaltet werden muss.</span><span class="sxs-lookup"><span data-stu-id="af759-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af759-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af759-107">Return Value</span></span>  
  
|<span data-ttu-id="af759-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af759-108">HRESULT</span></span>|<span data-ttu-id="af759-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af759-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af759-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="af759-110">S_OK</span></span>|<span data-ttu-id="af759-111">`SetMinThreads`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="af759-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="af759-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="af759-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="af759-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="af759-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="af759-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="af759-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="af759-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="af759-115">The call timed out.</span></span>|  
|<span data-ttu-id="af759-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="af759-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="af759-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="af759-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="af759-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="af759-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="af759-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="af759-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="af759-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="af759-120">E_FAIL</span></span>|<span data-ttu-id="af759-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="af759-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="af759-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="af759-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="af759-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="af759-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="af759-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="af759-124">E_NOTIMPL</span></span>|<span data-ttu-id="af759-125">Der Host bietet keine Implementierung von `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="af759-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af759-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af759-126">Remarks</span></span>  
 <span data-ttu-id="af759-127">Ein Host ist nicht erforderlich, um eine Implementierung bereitstellen `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="af759-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="af759-128">In diesem Fall sollte er einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="af759-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af759-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af759-129">Requirements</span></span>  
 <span data-ttu-id="af759-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af759-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af759-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af759-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af759-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="af759-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af759-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af759-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af759-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af759-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="af759-135">GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="af759-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="af759-136">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="af759-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="af759-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af759-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
