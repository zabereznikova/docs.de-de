---
title: IHostIoCompletionManager::GetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
ms.openlocfilehash: 2506de5f04840f130fab28518f9db7b58eb6e9ff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133822"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="2f858-102">IHostIoCompletionManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="2f858-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="2f858-103">Ruft die Mindestanzahl von Threads ab, die der Host für die Verarbeitung von e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2f858-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f858-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f858-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f858-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f858-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="2f858-106">vorgenommen Ein Zeiger auf die Mindestanzahl von Threads, die der Host für die Verarbeitung von e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2f858-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f858-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2f858-107">Return Value</span></span>  
  
|<span data-ttu-id="2f858-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f858-108">HRESULT</span></span>|<span data-ttu-id="2f858-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f858-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f858-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f858-110">S_OK</span></span>|<span data-ttu-id="2f858-111">`GetMinThreads` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f858-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="2f858-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f858-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f858-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2f858-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2f858-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2f858-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2f858-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2f858-115">The call timed out.</span></span>|  
|<span data-ttu-id="2f858-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2f858-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2f858-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2f858-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2f858-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2f858-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2f858-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2f858-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2f858-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f858-120">E_FAIL</span></span>|<span data-ttu-id="2f858-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2f858-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2f858-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f858-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2f858-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2f858-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2f858-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="2f858-124">E_NOTIMPL</span></span>|<span data-ttu-id="2f858-125">Der Host stellt keine Implementierung von `GetMinThreads`bereit.</span><span class="sxs-lookup"><span data-stu-id="2f858-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f858-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2f858-126">Remarks</span></span>  
 <span data-ttu-id="2f858-127">Ein Host möchte möglicherweise die exklusive Kontrolle über die Anzahl von Threads, die für e/a-Anforderungen des Diensts zugewiesen sind, aus Gründen wie Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="2f858-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="2f858-128">Aus diesem Grund ist es nicht erforderlich, dass der Host `GetMinThreads`implementiert.</span><span class="sxs-lookup"><span data-stu-id="2f858-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="2f858-129">In diesem Fall sollte der Host E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2f858-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f858-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f858-130">Requirements</span></span>  
 <span data-ttu-id="2f858-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f858-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f858-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2f858-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f858-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2f858-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f858-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f858-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f858-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f858-135">See also</span></span>

- [<span data-ttu-id="2f858-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f858-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2f858-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f858-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
