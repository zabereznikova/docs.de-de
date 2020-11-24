---
title: IHostIoCompletionManager::SetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: dea34b81-8d2b-4cc3-8696-0ad4291d8a92
topic_type:
- apiref
ms.openlocfilehash: 64ea9fdd477ec005b089f451101b742278ab4266
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672408"
---
# <a name="ihostiocompletionmanagersetminthreads-method"></a><span data-ttu-id="1ab51-102">IHostIoCompletionManager::SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1ab51-102">IHostIoCompletionManager::SetMinThreads Method</span></span>

<span data-ttu-id="1ab51-103">Legt die Mindestanzahl von Threads fest, die der Host für die e/a-Vervollständigung in hohem Maß beachten soll.</span><span class="sxs-lookup"><span data-stu-id="1ab51-103">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ab51-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMinThreads (  
    [in] DWORD dwMinIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ab51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ab51-105">Parameters</span></span>  

 `dwMinIoCompletionThreads`  
 <span data-ttu-id="1ab51-106">in Die Mindestanzahl von e/a-Abschluss-Threads, die der Host erstellen soll.</span><span class="sxs-lookup"><span data-stu-id="1ab51-106">[in] The minimum number of I/O completion threads that the host should create.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ab51-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ab51-107">Return Value</span></span>  
  
|<span data-ttu-id="1ab51-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ab51-108">HRESULT</span></span>|<span data-ttu-id="1ab51-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ab51-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ab51-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ab51-110">S_OK</span></span>|<span data-ttu-id="1ab51-111">`SetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1ab51-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1ab51-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ab51-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ab51-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1ab51-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ab51-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ab51-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ab51-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1ab51-115">The call timed out.</span></span>|  
|<span data-ttu-id="1ab51-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ab51-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ab51-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1ab51-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ab51-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ab51-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ab51-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1ab51-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ab51-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ab51-120">E_FAIL</span></span>|<span data-ttu-id="1ab51-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1ab51-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ab51-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1ab51-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ab51-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1ab51-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1ab51-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1ab51-124">E_NOTIMPL</span></span>|<span data-ttu-id="1ab51-125">Der Host stellt keine Implementierung von bereit `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="1ab51-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ab51-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ab51-126">Remarks</span></span>  

 <span data-ttu-id="1ab51-127">Ein Host möchte möglicherweise eine exklusive Kontrolle über die Anzahl der Threads, die für die Verarbeitung von e/a-Anforderungen zugewiesen werden können, z. b. die Implementierung, die Leistung oder die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="1ab51-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="1ab51-128">Aus diesem Grund ist es nicht erforderlich, dass der Host implementiert `SetMinThreads` .</span><span class="sxs-lookup"><span data-stu-id="1ab51-128">For this reason, the host is not required to implement `SetMinThreads`.</span></span> <span data-ttu-id="1ab51-129">In diesem Fall sollte der Host E_NOTIMPL aus dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1ab51-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab51-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1ab51-130">Requirements</span></span>  

 <span data-ttu-id="1ab51-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ab51-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab51-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1ab51-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ab51-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ab51-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ab51-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab51-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab51-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ab51-135">See also</span></span>

- [<span data-ttu-id="1ab51-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ab51-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="1ab51-137">SetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="1ab51-137">SetMaxThreads Method</span></span>](ihostiocompletionmanager-setmaxthreads-method.md)
- [<span data-ttu-id="1ab51-138">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ab51-138">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
