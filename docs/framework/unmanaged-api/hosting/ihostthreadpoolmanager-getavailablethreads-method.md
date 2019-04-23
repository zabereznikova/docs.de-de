---
title: IHostThreadPoolManager::GetAvailableThreads-Methoden
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4f16db1d35f8a0de1c755566e27b07bf9067dfe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129193"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="edc14-102">IHostThreadPoolManager::GetAvailableThreads-Methoden</span><span class="sxs-lookup"><span data-stu-id="edc14-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="edc14-103">Ruft die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="edc14-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edc14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edc14-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edc14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edc14-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="edc14-106">[out] Zeiger auf die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="edc14-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edc14-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="edc14-107">Return Value</span></span>  
  
|<span data-ttu-id="edc14-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="edc14-108">HRESULT</span></span>|<span data-ttu-id="edc14-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edc14-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="edc14-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="edc14-110">S_OK</span></span>|<span data-ttu-id="edc14-111">`GetAvailableThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="edc14-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="edc14-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="edc14-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="edc14-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="edc14-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="edc14-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="edc14-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="edc14-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="edc14-115">The call timed out.</span></span>|  
|<span data-ttu-id="edc14-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="edc14-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="edc14-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="edc14-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="edc14-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="edc14-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="edc14-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="edc14-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="edc14-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="edc14-120">E_FAIL</span></span>|<span data-ttu-id="edc14-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="edc14-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="edc14-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="edc14-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="edc14-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="edc14-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="edc14-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="edc14-124">E_NOTIMPL</span></span>|<span data-ttu-id="edc14-125">Der Host stellt keine Implementierung von `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="edc14-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edc14-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edc14-126">Remarks</span></span>  
 <span data-ttu-id="edc14-127">Wenn der Host nicht über eine Implementierung der bietet `GetAvailableThreads`, es sollte einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="edc14-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edc14-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edc14-128">Requirements</span></span>  
 <span data-ttu-id="edc14-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edc14-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edc14-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="edc14-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="edc14-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="edc14-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edc14-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edc14-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edc14-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edc14-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="edc14-134">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edc14-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
