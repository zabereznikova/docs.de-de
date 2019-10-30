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
ms.openlocfilehash: 2fa429979faa04518397cf58aaa62d3e45230a76
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133832"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="3c5bb-102">IHostIoCompletionManager::GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="3c5bb-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="3c5bb-103">Ruft die Anzahl der e/a-abschlusthreads von der Gesamtanzahl der vom Host verwalteten Threads ab, die zurzeit keine Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c5bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c5bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c5bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c5bb-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="3c5bb-106">vorgenommen Ein Zeiger auf die Anzahl der e/a-abschlusthreads, die vom Host verwaltet werden und für die Service Requests zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c5bb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c5bb-107">Return Value</span></span>  
  
|<span data-ttu-id="3c5bb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c5bb-108">HRESULT</span></span>|<span data-ttu-id="3c5bb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c5bb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c5bb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c5bb-110">S_OK</span></span>|<span data-ttu-id="3c5bb-111">`GetAvailableThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="3c5bb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c5bb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c5bb-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c5bb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c5bb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c5bb-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-115">The call timed out.</span></span>|  
|<span data-ttu-id="3c5bb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c5bb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c5bb-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c5bb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c5bb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c5bb-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c5bb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c5bb-120">E_FAIL</span></span>|<span data-ttu-id="3c5bb-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c5bb-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c5bb-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3c5bb-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="3c5bb-124">E_NOTIMPL</span></span>|<span data-ttu-id="3c5bb-125">Der Host stellt keine Implementierung von `GetAvailableThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c5bb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c5bb-126">Remarks</span></span>  
 <span data-ttu-id="3c5bb-127">Ein Host möchte möglicherweise eine exklusive Kontrolle über die Größe des e/a-Abschluss Thread Pools, wie z. b. Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="3c5bb-128">Daher ist es nicht erforderlich, dass der Host `GetAvailableThreads`implementiert.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="3c5bb-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3c5bb-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c5bb-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c5bb-130">Requirements</span></span>  
 <span data-ttu-id="3c5bb-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c5bb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c5bb-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3c5bb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c5bb-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c5bb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c5bb-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c5bb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5bb-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c5bb-135">See also</span></span>

- [<span data-ttu-id="3c5bb-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c5bb-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="3c5bb-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c5bb-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
