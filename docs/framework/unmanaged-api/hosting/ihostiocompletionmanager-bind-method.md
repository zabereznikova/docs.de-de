---
title: IHostIoCompletionManager::Bind-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.Bind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::Bind
helpviewer_keywords:
- IHostIoCompletionManager::Bind method [.NET Framework hosting]
- Bind method [.NET Framework hosting]
ms.assetid: acd74cb5-7e22-4a07-83c3-82288e1abd9f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de39de96cd7c7ba0be2dc1bea78f79cfe996575c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937563"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="d458a-102">IHostIoCompletionManager::Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="d458a-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="d458a-103">Bindet das angegebene Handle an einen e/a-Abschlussport, der durch einen früheren Aufrufen von " [kreateiocompletionport](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d458a-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d458a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d458a-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d458a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d458a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="d458a-106">in Der e/a-Abschlussport, `hHandle`an den gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="d458a-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="d458a-107">Wenn der Wert von `hPort` NULL ist, `hHandle` wird an den Standard-e/a-Abschlussport gebunden.</span><span class="sxs-lookup"><span data-stu-id="d458a-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="d458a-108">in Das Betriebssystem handle, an `hPort`das die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="d458a-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d458a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d458a-109">Return Value</span></span>  
  
|<span data-ttu-id="d458a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d458a-110">HRESULT</span></span>|<span data-ttu-id="d458a-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d458a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d458a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d458a-112">S_OK</span></span>|<span data-ttu-id="d458a-113">`Bind`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d458a-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="d458a-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d458a-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d458a-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d458a-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d458a-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d458a-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d458a-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d458a-117">The call timed out.</span></span>|  
|<span data-ttu-id="d458a-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d458a-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d458a-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d458a-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d458a-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d458a-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d458a-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d458a-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d458a-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d458a-122">E_FAIL</span></span>|<span data-ttu-id="d458a-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d458a-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d458a-124">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d458a-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d458a-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d458a-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d458a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d458a-126">Remarks</span></span>  
 <span data-ttu-id="d458a-127">Ein e/a-Abschlussport wird mithilfe eines Aufrufes `CreateIoCompletionPort`erstellt.</span><span class="sxs-lookup"><span data-stu-id="d458a-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="d458a-128">Die CLR ruft `Bind` auf, um ein Handle an diesen Port zu binden.</span><span class="sxs-lookup"><span data-stu-id="d458a-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d458a-129">Wenn eine e/a-Anforderung abgeschlossen ist, muss der Host die [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) -Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="d458a-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d458a-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d458a-130">Requirements</span></span>  
 <span data-ttu-id="d458a-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d458a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d458a-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d458a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d458a-133">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d458a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d458a-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d458a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d458a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d458a-135">See also</span></span>

- [<span data-ttu-id="d458a-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d458a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
