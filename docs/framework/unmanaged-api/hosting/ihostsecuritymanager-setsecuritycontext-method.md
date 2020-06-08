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
ms.openlocfilehash: 6a6b4d0351e22026dc873aad8281d0259d871a14
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501481"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="30960-102">IHostSecurityManager::SetSecurityContext-Methode</span><span class="sxs-lookup"><span data-stu-id="30960-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="30960-103">Legt den Sicherheitskontext des aktuell ausgeführten Threads fest.</span><span class="sxs-lookup"><span data-stu-id="30960-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30960-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30960-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30960-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30960-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="30960-106">in Einer der [EContextType](econtexttype-enumeration.md) -Werte, der angibt, welche Art von Kontext die Common Language Runtime (CLR) auf dem Host platziert.</span><span class="sxs-lookup"><span data-stu-id="30960-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="30960-107">vorgenommen Ein Zeiger auf die Adresse eines neuen [IHostSecurityContext](ihostsecuritycontext-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="30960-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30960-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30960-108">Return Value</span></span>  
  
|<span data-ttu-id="30960-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30960-109">HRESULT</span></span>|<span data-ttu-id="30960-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30960-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30960-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="30960-111">S_OK</span></span>|<span data-ttu-id="30960-112">`SetSecurityContext`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="30960-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="30960-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30960-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30960-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="30960-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30960-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30960-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30960-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="30960-116">The call timed out.</span></span>|  
|<span data-ttu-id="30960-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30960-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30960-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="30960-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30960-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30960-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30960-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="30960-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30960-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30960-121">E_FAIL</span></span>|<span data-ttu-id="30960-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="30960-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30960-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="30960-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30960-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="30960-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30960-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="30960-125">Remarks</span></span>  
 <span data-ttu-id="30960-126">Die CLR ruft `SetSecurityContext` in verschiedenen Szenarien auf.</span><span class="sxs-lookup"><span data-stu-id="30960-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="30960-127">Bevor Klassen-und Modulkonstruktoren und Finalizer ausgeführt werden, ruft die CLR `SetSecurityContext` auf, um den Host vor Ausführungsfehlern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="30960-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="30960-128">Anschließend wird der Sicherheitskontext nach der Ausführung des Konstruktors oder Finalizers mithilfe eines anderen Aufrufes wieder auf den ursprünglichen Zustand zurückgesetzt `SetSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="30960-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="30960-129">Ein ähnliches Muster tritt bei der e/a-Vervollständigung auf.</span><span class="sxs-lookup"><span data-stu-id="30960-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="30960-130">Wenn der Host [IHostIoCompletionManager](ihostiocompletionmanager-interface.md)implementiert, ruft die CLR auf, `SetSecurityContext` nachdem der Host [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="30960-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="30960-131">Bei asynchronen Punkten in Arbeitsthreads ruft die CLR `SetSecurityContext` innerhalb von <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> oder innerhalb von [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)auf, je nachdem, ob der Host oder die CLR den Thread Pool implementiert.</span><span class="sxs-lookup"><span data-stu-id="30960-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30960-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="30960-132">Requirements</span></span>  
 <span data-ttu-id="30960-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30960-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30960-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="30960-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30960-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="30960-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30960-136">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30960-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30960-137">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="30960-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="30960-138">EContextType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="30960-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="30960-139">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30960-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="30960-140">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30960-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="30960-141">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30960-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="30960-142">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30960-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="30960-143">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30960-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
