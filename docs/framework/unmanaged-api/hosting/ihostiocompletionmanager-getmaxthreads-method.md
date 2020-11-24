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
ms.openlocfilehash: 0b16305bc88854f1ab2ab89ab6b0d4d3e6881cf1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689470"
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="36d12-102">IHostIoCompletionManager::GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="36d12-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>

<span data-ttu-id="36d12-103">Ruft die maximale Anzahl von Threads ab, die der Host für Dienst-e/a-Anforderungen in hohem Maß abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="36d12-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36d12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36d12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36d12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36d12-105">Parameters</span></span>  

 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="36d12-106">vorgenommen Ein Zeiger auf die maximale Anzahl von Threads im Thread Pool, die der Host für die e/a-Anforderungen des Diensts sehr viel haben kann.</span><span class="sxs-lookup"><span data-stu-id="36d12-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36d12-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36d12-107">Return Value</span></span>  
  
|<span data-ttu-id="36d12-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36d12-108">HRESULT</span></span>|<span data-ttu-id="36d12-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="36d12-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36d12-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36d12-110">S_OK</span></span>|<span data-ttu-id="36d12-111">`GetMaxThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="36d12-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="36d12-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36d12-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36d12-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="36d12-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36d12-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36d12-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36d12-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="36d12-115">The call timed out.</span></span>|  
|<span data-ttu-id="36d12-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36d12-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36d12-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="36d12-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36d12-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36d12-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36d12-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="36d12-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36d12-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36d12-120">E_FAIL</span></span>|<span data-ttu-id="36d12-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="36d12-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36d12-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="36d12-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36d12-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="36d12-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36d12-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="36d12-124">E_NOTIMPL</span></span>|<span data-ttu-id="36d12-125">Der Host stellt keine Implementierung von bereit `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="36d12-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d12-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36d12-126">Remarks</span></span>  

 <span data-ttu-id="36d12-127">Ein Host möchte möglicherweise eine exklusive Kontrolle über die Anzahl der Threads, die für die Verarbeitung von e/a-Anforderungen zugewiesen werden können, z. b. die Implementierung, die Leistung oder die Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="36d12-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="36d12-128">Aus diesem Grund ist es nicht erforderlich, dass der Host implementiert `GetMaxThreads` .</span><span class="sxs-lookup"><span data-stu-id="36d12-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="36d12-129">In diesem Fall sollte der Host E_NOTIMPL aus dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="36d12-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36d12-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="36d12-130">Requirements</span></span>  

 <span data-ttu-id="36d12-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36d12-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36d12-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="36d12-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36d12-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="36d12-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36d12-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36d12-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36d12-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="36d12-135">See also</span></span>

- [<span data-ttu-id="36d12-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36d12-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="36d12-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36d12-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
