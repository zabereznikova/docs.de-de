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
ms.openlocfilehash: c03cdb9f9205676d17d6e18b9b2e074132ee26f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54594771"
---
# <a name="ihostiocompletionmanagerbind-method"></a><span data-ttu-id="3c623-102">IHostIoCompletionManager::Bind-Methode</span><span class="sxs-lookup"><span data-stu-id="3c623-102">IHostIoCompletionManager::Bind Method</span></span>
<span data-ttu-id="3c623-103">Bindet das angegebene Handle an ein e/a-Abschlussport, der durch einen früheren Aufruf von erstellt wurde [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="3c623-103">Binds the specified handle to an I/O completion port that has been created by an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c623-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c623-104">Syntax</span></span>  
  
```  
HRESULT Bind (  
    [in] HANDLE hPort,  
    [in] HANDLE hHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c623-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c623-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="3c623-106">[in] Der e/a-Abschlussport für die Bindung `hHandle`.</span><span class="sxs-lookup"><span data-stu-id="3c623-106">[in] The I/O completion port to which to bind `hHandle`.</span></span> <span data-ttu-id="3c623-107">Wenn der Wert des `hPort` null ist, `hHandle` an der Standard-e/a-Abschlussport gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="3c623-107">If the value of `hPort` is null, `hHandle` is bound to the default I/O completion port.</span></span>  
  
 `hHandle`  
 <span data-ttu-id="3c623-108">[in] Das Betriebssystemhandle zum Binden an `hPort`.</span><span class="sxs-lookup"><span data-stu-id="3c623-108">[in] The operating system handle to bind to `hPort`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c623-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c623-109">Return Value</span></span>  
  
|<span data-ttu-id="3c623-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c623-110">HRESULT</span></span>|<span data-ttu-id="3c623-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c623-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c623-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c623-112">S_OK</span></span>|<span data-ttu-id="3c623-113">`Bind` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c623-113">`Bind` returned successfully.</span></span>|  
|<span data-ttu-id="3c623-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c623-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c623-115">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c623-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c623-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c623-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c623-117">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c623-117">The call timed out.</span></span>|  
|<span data-ttu-id="3c623-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c623-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c623-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="3c623-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c623-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c623-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c623-121">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="3c623-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c623-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c623-122">E_FAIL</span></span>|<span data-ttu-id="3c623-123">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c623-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c623-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c623-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c623-125">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3c623-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c623-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c623-126">Remarks</span></span>  
 <span data-ttu-id="3c623-127">Ein e/a-Abschlussport wird erstellt, indem Sie über einen Aufruf an `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="3c623-127">An I/O completion port is created by using a call to `CreateIoCompletionPort`.</span></span> <span data-ttu-id="3c623-128">Die CLR ruft `Bind` ein Handle an diesen Port gebunden.</span><span class="sxs-lookup"><span data-stu-id="3c623-128">The CLR calls `Bind` to bind a handle to that port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c623-129">Wenn eine e/a-Anforderung abgeschlossen ist, muss der Host Aufrufen der [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="3c623-129">When an I/O request completes, the host must call the [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c623-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c623-130">Requirements</span></span>  
 <span data-ttu-id="3c623-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c623-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c623-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3c623-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c623-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c623-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c623-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c623-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c623-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c623-135">See also</span></span>
- [<span data-ttu-id="3c623-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c623-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
