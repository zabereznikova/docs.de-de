---
title: IHostIoCompletionManager::SetCLRIoCompletionManager-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetCLRIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fde1045fd0f15e7255a163c1f1b041800e85921
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="07769-102">IHostIoCompletionManager::SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="07769-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="07769-103">Bietet einen Schnittstellenzeiger auf den Host die [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) Instanz, die von der common Language Runtime (CLR) implementiert.</span><span class="sxs-lookup"><span data-stu-id="07769-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07769-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07769-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07769-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07769-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="07769-106">[in] Einen Schnittstellenzeiger auf eine `ICLRIoCompletionManager` -Instanz, von der CLR bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="07769-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07769-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07769-107">Return Value</span></span>  
  
|<span data-ttu-id="07769-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07769-108">HRESULT</span></span>|<span data-ttu-id="07769-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07769-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07769-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="07769-110">S_OK</span></span>|<span data-ttu-id="07769-111">`SetCLRIoCompletionManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="07769-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="07769-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="07769-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="07769-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="07769-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="07769-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="07769-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="07769-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="07769-115">The call timed out.</span></span>|  
|<span data-ttu-id="07769-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="07769-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="07769-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="07769-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="07769-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="07769-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="07769-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="07769-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="07769-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="07769-120">E_FAIL</span></span>|<span data-ttu-id="07769-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="07769-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="07769-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="07769-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="07769-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="07769-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07769-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07769-124">Remarks</span></span>  
 <span data-ttu-id="07769-125">Nachdem die CLR aufgerufen hat `SetCLRIoCompletionManager`, muss der Host Aufrufen [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) um CLR zu benachrichtigen, wenn eine e/a-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="07769-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07769-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07769-126">Requirements</span></span>  
 <span data-ttu-id="07769-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07769-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07769-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="07769-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07769-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="07769-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07769-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07769-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07769-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07769-131">See Also</span></span>  
 [<span data-ttu-id="07769-132">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07769-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="07769-133">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07769-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
