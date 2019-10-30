---
title: IHostSecurityManager::SetSecurityContext-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121443"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="dd82e-102">IHostSecurityManager::SetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="dd82e-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="dd82e-103">Legt den Sicherheitskontext des aktuell ausgeführten Threads fest.</span><span class="sxs-lookup"><span data-stu-id="dd82e-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd82e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd82e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd82e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd82e-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="dd82e-106">in Einer der [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) -Werte, der angibt, welche Art von Kontext die Common Language Runtime (CLR) auf dem Host platziert.</span><span class="sxs-lookup"><span data-stu-id="dd82e-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="dd82e-107">vorgenommen Ein Zeiger auf die Adresse eines neuen [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="dd82e-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd82e-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd82e-108">Return Value</span></span>  
  
|<span data-ttu-id="dd82e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd82e-109">HRESULT</span></span>|<span data-ttu-id="dd82e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd82e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd82e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd82e-111">S_OK</span></span>|<span data-ttu-id="dd82e-112">`SetSecurityContext` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dd82e-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="dd82e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd82e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd82e-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dd82e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd82e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd82e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd82e-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dd82e-116">The call timed out.</span></span>|  
|<span data-ttu-id="dd82e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd82e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd82e-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dd82e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd82e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd82e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd82e-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dd82e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd82e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd82e-121">E_FAIL</span></span>|<span data-ttu-id="dd82e-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dd82e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd82e-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dd82e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd82e-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dd82e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd82e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd82e-125">Remarks</span></span>  
 <span data-ttu-id="dd82e-126">Die CLR ruft `SetSecurityContext` in verschiedenen Szenarien auf.</span><span class="sxs-lookup"><span data-stu-id="dd82e-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="dd82e-127">Bevor Klassen-und Modulkonstruktoren und Finalizer ausgeführt werden, ruft die CLR `SetSecurityContext` auf, um den Host vor Ausführungsfehlern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="dd82e-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="dd82e-128">Anschließend wird der Sicherheitskontext nach der Ausführung des Konstruktors oder Finalizers auf seinen ursprünglichen Zustand zurückgesetzt, indem ein anderer `SetSecurityContext`aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dd82e-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="dd82e-129">Ein ähnliches Muster tritt bei der e/a-Vervollständigung auf.</span><span class="sxs-lookup"><span data-stu-id="dd82e-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="dd82e-130">Wenn der Host [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)implementiert, ruft die CLR `SetSecurityContext` auf, nachdem der Host [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="dd82e-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="dd82e-131">Bei asynchronen Punkten in Arbeitsthreads ruft die CLR `SetSecurityContext` in <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> oder innerhalb von [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)auf, je nachdem, ob der Host oder die CLR den Thread Pool implementiert.</span><span class="sxs-lookup"><span data-stu-id="dd82e-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd82e-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd82e-132">Requirements</span></span>  
 <span data-ttu-id="dd82e-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd82e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd82e-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dd82e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd82e-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dd82e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd82e-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd82e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd82e-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd82e-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="dd82e-138">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dd82e-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="dd82e-139">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd82e-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="dd82e-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd82e-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="dd82e-141">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd82e-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="dd82e-142">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd82e-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="dd82e-143">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd82e-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
