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
ms.openlocfilehash: 84fc99f6a5feb7ec73ee16942ba2794fc082dc89
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133900"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="7acc1-102">IHostIoCompletionManager::Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="7acc1-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="7acc1-103">Bindet das angegebene Handle an einen e/a-Abschlussport, der durch einen früheren Aufrufen von " [kreateiocompletionport](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7acc1-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7acc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7acc1-104">Syntax</span></span>  
  
```cpp  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7acc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7acc1-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="7acc1-106">in Der e/a-Abschlussport, an den `hHandle`gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="7acc1-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="7acc1-107">Wenn der Wert von `hPort` NULL ist, wird `hHandle` an den Standard-e/a-Abschlussport gebunden.</span><span class="sxs-lookup"><span data-stu-id="7acc1-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="7acc1-108">in Das Betriebssystem handle, das an `hPort`gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="7acc1-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7acc1-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7acc1-109">Return Value</span></span>  
  
|<span data-ttu-id="7acc1-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7acc1-110">HRESULT</span></span>|<span data-ttu-id="7acc1-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7acc1-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7acc1-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7acc1-112">S_OK</span></span>|<span data-ttu-id="7acc1-113">`Bind` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7acc1-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="7acc1-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7acc1-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7acc1-115">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7acc1-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7acc1-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7acc1-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7acc1-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="7acc1-117">The call timed out.</span></span>|  
|<span data-ttu-id="7acc1-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7acc1-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7acc1-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7acc1-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7acc1-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7acc1-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7acc1-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="7acc1-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7acc1-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7acc1-122">E_FAIL</span></span>|<span data-ttu-id="7acc1-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7acc1-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7acc1-124">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7acc1-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7acc1-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7acc1-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7acc1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7acc1-126">Remarks</span></span>  
 <span data-ttu-id="7acc1-127">Ein e/a-Abschlussport wird erstellt, indem ein-`CreateIoCompletionPort`aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7acc1-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="7acc1-128">Die CLR ruft `Bind` auf, um ein Handle an diesen Port zu binden.</span><span class="sxs-lookup"><span data-stu-id="7acc1-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7acc1-129">Wenn eine e/a-Anforderung abgeschlossen ist, muss der Host die [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) -Methode abrufen.</span><span class="sxs-lookup"><span data-stu-id="7acc1-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7acc1-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7acc1-130">Requirements</span></span>  
 <span data-ttu-id="7acc1-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7acc1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7acc1-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7acc1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7acc1-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7acc1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7acc1-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7acc1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7acc1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7acc1-135">See also</span></span>

- [<span data-ttu-id="7acc1-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7acc1-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
