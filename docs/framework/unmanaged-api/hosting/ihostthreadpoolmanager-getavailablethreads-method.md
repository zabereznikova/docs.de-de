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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129193"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="64dee-102">IHostThreadPoolManager::GetAvailableThreads-Methoden</span><span class="sxs-lookup"><span data-stu-id="64dee-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="64dee-103">Ruft die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="64dee-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64dee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64dee-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64dee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64dee-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="64dee-106">[out] Zeiger auf die Anzahl der Threads im Threadpool der Warteschleife hinzu, die derzeit keine Arbeitsaufgabe verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="64dee-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64dee-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="64dee-107">Return Value</span></span>  
  
|<span data-ttu-id="64dee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64dee-108">HRESULT</span></span>|<span data-ttu-id="64dee-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64dee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64dee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="64dee-110">S_OK</span></span>|`GetAvailableThreads` <span data-ttu-id="64dee-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="64dee-111">returned successfully.</span></span>|  
|<span data-ttu-id="64dee-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64dee-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64dee-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="64dee-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64dee-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64dee-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64dee-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="64dee-115">The call timed out.</span></span>|  
|<span data-ttu-id="64dee-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64dee-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64dee-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="64dee-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64dee-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64dee-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64dee-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="64dee-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64dee-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64dee-120">E_FAIL</span></span>|<span data-ttu-id="64dee-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="64dee-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64dee-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64dee-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64dee-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="64dee-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="64dee-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="64dee-124">E_NOTIMPL</span></span>|<span data-ttu-id="64dee-125">Der Host stellt keine Implementierung von `GetAvailableThreads`.</span><span class="sxs-lookup"><span data-stu-id="64dee-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64dee-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64dee-126">Remarks</span></span>  
 <span data-ttu-id="64dee-127">Wenn der Host nicht über eine Implementierung der bietet `GetAvailableThreads`, es sollte einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="64dee-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64dee-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64dee-128">Requirements</span></span>  
 <span data-ttu-id="64dee-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64dee-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64dee-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64dee-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64dee-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="64dee-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="64dee-132">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="64dee-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="64dee-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64dee-133">See also</span></span>

- <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="64dee-134">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64dee-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
