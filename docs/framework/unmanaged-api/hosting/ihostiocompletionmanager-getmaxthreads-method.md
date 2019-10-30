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
ms.openlocfilehash: d35fd91f2a28c392176a6dd87bd21baa964ee9a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133812"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="82d02-102">IHostIoCompletionManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="82d02-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="82d02-103">Ruft die maximale Anzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen in hohem Maß abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="82d02-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82d02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82d02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82d02-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="82d02-106">vorgenommen Ein Zeiger auf die maximale Anzahl von Threads im Thread Pool, die der Host für die e/a-Anforderungen des Diensts sehr viel haben kann.</span><span class="sxs-lookup"><span data-stu-id="82d02-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82d02-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82d02-107">Return Value</span></span>  
  
|<span data-ttu-id="82d02-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82d02-108">HRESULT</span></span>|<span data-ttu-id="82d02-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82d02-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82d02-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="82d02-110">S_OK</span></span>|<span data-ttu-id="82d02-111">`GetMaxThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="82d02-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="82d02-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82d02-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82d02-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="82d02-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82d02-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82d02-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82d02-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="82d02-115">The call timed out.</span></span>|  
|<span data-ttu-id="82d02-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82d02-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82d02-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="82d02-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82d02-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82d02-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82d02-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="82d02-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82d02-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82d02-120">E_FAIL</span></span>|<span data-ttu-id="82d02-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="82d02-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82d02-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82d02-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82d02-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="82d02-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="82d02-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="82d02-124">E_NOTIMPL</span></span>|<span data-ttu-id="82d02-125">Der Host stellt keine Implementierung von `GetMaxThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="82d02-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="82d02-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82d02-126">Remarks</span></span>  
 <span data-ttu-id="82d02-127">Ein Host möchte möglicherweise eine exklusive Kontrolle über die Anzahl der Threads, die für die Verarbeitung von e/a-Anforderungen zugewiesen werden können, z. b. die Implementierung, die Leistung oder die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="82d02-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="82d02-128">Aus diesem Grund ist es nicht erforderlich, dass der Host `GetMaxThreads`implementiert.</span><span class="sxs-lookup"><span data-stu-id="82d02-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="82d02-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="82d02-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82d02-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82d02-130">Requirements</span></span>  
 <span data-ttu-id="82d02-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82d02-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82d02-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="82d02-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82d02-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="82d02-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82d02-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82d02-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82d02-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82d02-135">See also</span></span>

- [<span data-ttu-id="82d02-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82d02-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="82d02-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82d02-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
