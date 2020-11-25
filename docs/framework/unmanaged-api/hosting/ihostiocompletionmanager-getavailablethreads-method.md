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
ms.openlocfilehash: 3e9f4e98962532efe4b2e2a779add841b7b3a835
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724259"
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="306c8-102">IHostIoCompletionManager::GetAvailableThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="306c8-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>

<span data-ttu-id="306c8-103">Ruft die Anzahl der e/a-abschlusthreads von der Gesamtanzahl der vom Host verwalteten Threads ab, die zurzeit keine Anforderungen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="306c8-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="306c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="306c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="306c8-105">Parameters</span></span>  

 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="306c8-106">vorgenommen Ein Zeiger auf die Anzahl der e/a-abschlusthreads, die vom Host verwaltet werden und für die Service Requests zurzeit verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="306c8-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="306c8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="306c8-107">Return Value</span></span>  
  
|<span data-ttu-id="306c8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="306c8-108">HRESULT</span></span>|<span data-ttu-id="306c8-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="306c8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="306c8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="306c8-110">S_OK</span></span>|<span data-ttu-id="306c8-111">`GetAvailableThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="306c8-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="306c8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="306c8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="306c8-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="306c8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="306c8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="306c8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="306c8-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="306c8-115">The call timed out.</span></span>|  
|<span data-ttu-id="306c8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="306c8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="306c8-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="306c8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="306c8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="306c8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="306c8-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="306c8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="306c8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="306c8-120">E_FAIL</span></span>|<span data-ttu-id="306c8-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="306c8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="306c8-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="306c8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="306c8-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="306c8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="306c8-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="306c8-124">E_NOTIMPL</span></span>|<span data-ttu-id="306c8-125">Der Host stellt keine Implementierung von bereit `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="306c8-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306c8-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="306c8-126">Remarks</span></span>  

 <span data-ttu-id="306c8-127">Ein Host möchte möglicherweise eine exklusive Kontrolle über die Größe des e/a-Abschluss Thread Pools, wie z. b. Implementierung, Leistung oder Skalierbarkeit.</span><span class="sxs-lookup"><span data-stu-id="306c8-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="306c8-128">Daher ist es nicht erforderlich, dass der Host implementiert `GetAvailableThreads` .</span><span class="sxs-lookup"><span data-stu-id="306c8-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="306c8-129">In diesem Fall sollte der Host E_NOTIMPL aus dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="306c8-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306c8-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="306c8-130">Requirements</span></span>  

 <span data-ttu-id="306c8-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306c8-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306c8-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="306c8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="306c8-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="306c8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="306c8-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306c8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306c8-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="306c8-135">See also</span></span>

- [<span data-ttu-id="306c8-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="306c8-136">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="306c8-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="306c8-137">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
