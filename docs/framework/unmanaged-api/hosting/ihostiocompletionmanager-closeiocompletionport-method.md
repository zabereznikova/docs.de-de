---
title: IHostIoCompletionManager::CloseIoCompletionPort-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e74803cad610d5550ce8b52ce04295247617d907
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="ed50b-102">IHostIoCompletionManager::CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="ed50b-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="ed50b-103">Fordert an, dass der Host über einen Port schließen, die durch einen früheren Aufruf geöffnet wurde [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="ed50b-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed50b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed50b-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed50b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed50b-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="ed50b-106">[in] Das Handle des Ports zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ed50b-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed50b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ed50b-107">Return Value</span></span>  
  
|<span data-ttu-id="ed50b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed50b-108">HRESULT</span></span>|<span data-ttu-id="ed50b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed50b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed50b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed50b-110">S_OK</span></span>|<span data-ttu-id="ed50b-111">`CloseIoCompletionPort`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ed50b-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="ed50b-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ed50b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed50b-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ed50b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed50b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed50b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed50b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ed50b-115">The call timed out.</span></span>|  
|<span data-ttu-id="ed50b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed50b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed50b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ed50b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed50b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed50b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed50b-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ed50b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed50b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed50b-120">E_FAIL</span></span>|<span data-ttu-id="ed50b-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ed50b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed50b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ed50b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed50b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ed50b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed50b-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ed50b-124">E_INVALIDARG</span></span>|<span data-ttu-id="ed50b-125">Es wurde ein ungültiger Porthandle übergeben.</span><span class="sxs-lookup"><span data-stu-id="ed50b-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed50b-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed50b-126">Remarks</span></span>  
 <span data-ttu-id="ed50b-127">`hPort`muss ein Handle für einen Port, der durch einen früheren Aufruf erstellt wurde `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="ed50b-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed50b-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed50b-128">Requirements</span></span>  
 <span data-ttu-id="ed50b-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed50b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed50b-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ed50b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed50b-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ed50b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed50b-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed50b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed50b-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed50b-133">See Also</span></span>  
 [<span data-ttu-id="ed50b-134">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed50b-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="ed50b-135">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed50b-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
