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
ms.openlocfilehash: d321ce08edf4780fc5f26ac627849b9129c2f283
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673220"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="491c3-102">IHostIoCompletionManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="491c3-102">IHostIoCompletionManager::GetMinThreads Method</span></span>

<span data-ttu-id="491c3-103">Ruft die Mindestanzahl von Threads ab, die der Host für die Verarbeitung von e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="491c3-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="491c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="491c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="491c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="491c3-105">Parameters</span></span>  

 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="491c3-106">vorgenommen Ein Zeiger auf die Mindestanzahl von Threads, die der Host für die Verarbeitung von e/a-Anforderungen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="491c3-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="491c3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="491c3-107">Return Value</span></span>  
  
|<span data-ttu-id="491c3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="491c3-108">HRESULT</span></span>|<span data-ttu-id="491c3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="491c3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="491c3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="491c3-110">S_OK</span></span>|<span data-ttu-id="491c3-111">`GetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="491c3-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="491c3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="491c3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="491c3-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="491c3-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="491c3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="491c3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="491c3-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="491c3-115">The call timed out.</span></span>|  
|<span data-ttu-id="491c3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="491c3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="491c3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="491c3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="491c3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="491c3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="491c3-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="491c3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="491c3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="491c3-120">E_FAIL</span></span>|<span data-ttu-id="491c3-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="491c3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="491c3-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="491c3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="491c3-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="491c3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="491c3-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="491c3-124">E_NOTIMPL</span></span>|<span data-ttu-id="491c3-125">Der Host stellt keine Implementierung von bereit `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="491c3-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="491c3-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="491c3-126">Remarks</span></span>  

 <span data-ttu-id="491c3-127">Ein Host möchte möglicherweise die exklusive Kontrolle über die Anzahl von Threads, die für e/a-Anforderungen des Diensts zugewiesen sind, aus Gründen wie Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="491c3-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="491c3-128">Aus diesem Grund ist es nicht erforderlich, dass der Host implementiert `GetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="491c3-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="491c3-129">In diesem Fall sollte der Host E_NOTIMPL aus dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="491c3-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="491c3-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="491c3-130">Requirements</span></span>  

 <span data-ttu-id="491c3-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="491c3-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="491c3-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="491c3-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="491c3-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="491c3-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="491c3-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="491c3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="491c3-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="491c3-135">See also</span></span>

- [<span data-ttu-id="491c3-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="491c3-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="491c3-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="491c3-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
