---
title: IHostThreadPoolManager::GetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
ms.openlocfilehash: ce1abb75c5135a9bb23f1ad2d2acbd40d9111b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122071"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="8897e-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="8897e-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="8897e-103">Ruft die Mindestanzahl von Leerlaufthreads ab, die der Host im Thread Pool in Erwartung von Anforderungen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8897e-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8897e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8897e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8897e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8897e-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="8897e-106">vorgenommen Ein Zeiger auf die Mindestanzahl von Arbeitsthreads im Leerlauf, die zurzeit vom Host verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8897e-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8897e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8897e-107">Return Value</span></span>  
  
|<span data-ttu-id="8897e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8897e-108">HRESULT</span></span>|<span data-ttu-id="8897e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8897e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8897e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8897e-110">S_OK</span></span>|<span data-ttu-id="8897e-111">`GetMinThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8897e-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8897e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8897e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8897e-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8897e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8897e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8897e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8897e-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8897e-115">The call timed out.</span></span>|  
|<span data-ttu-id="8897e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8897e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8897e-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8897e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8897e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8897e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8897e-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8897e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8897e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8897e-120">E_FAIL</span></span>|<span data-ttu-id="8897e-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8897e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8897e-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8897e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8897e-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8897e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8897e-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8897e-124">E_NOTIMPL</span></span>|<span data-ttu-id="8897e-125">Der Host stellt keine Implementierung von `GetMinThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="8897e-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8897e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8897e-126">Remarks</span></span>  
 <span data-ttu-id="8897e-127">Der Host muss keine Implementierung von `GetMinThreads`bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8897e-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="8897e-128">In diesem Fall sollte ein HRESULT-Wert von E_NOTIMPL zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8897e-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8897e-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8897e-129">Requirements</span></span>  
 <span data-ttu-id="8897e-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8897e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8897e-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8897e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8897e-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8897e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8897e-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8897e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8897e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8897e-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="8897e-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="8897e-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="8897e-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="8897e-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="8897e-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8897e-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
