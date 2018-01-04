---
title: IHostTaskManager::SetCLRTaskManager-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetCLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f009fee3f9bc439ce61d859759870f9cbb54f09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="0f627-102">IHostTaskManager::SetCLRTaskManager-Methode</span><span class="sxs-lookup"><span data-stu-id="0f627-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="0f627-103">Ermöglicht den Host einen Schnittstellenzeiger auf eine [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) Instanz, die von der common Language Runtime (CLR) implementiert.</span><span class="sxs-lookup"><span data-stu-id="0f627-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f627-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f627-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f627-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f627-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="0f627-106">[in] Ein Zeiger auf eine `ICLRTaskManager` -Instanz, von der common Language Runtime implementiert.</span><span class="sxs-lookup"><span data-stu-id="0f627-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f627-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f627-107">Return Value</span></span>  
  
|<span data-ttu-id="0f627-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f627-108">HRESULT</span></span>|<span data-ttu-id="0f627-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f627-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f627-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f627-110">S_OK</span></span>|<span data-ttu-id="0f627-111">`SetCLRTaskManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0f627-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="0f627-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0f627-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f627-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0f627-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f627-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f627-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f627-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0f627-115">The call timed out.</span></span>|  
|<span data-ttu-id="0f627-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f627-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f627-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0f627-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f627-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f627-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f627-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0f627-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f627-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f627-120">E_FAIL</span></span>|<span data-ttu-id="0f627-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0f627-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f627-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0f627-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f627-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0f627-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f627-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f627-124">Remarks</span></span>  
 <span data-ttu-id="0f627-125">Ruft die Laufzeit `SetCLRTaskManager` einen Schnittstellenzeiger auf den Host Bereitstellen einer `ICLRTaskManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="0f627-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f627-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f627-126">Requirements</span></span>  
 <span data-ttu-id="0f627-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f627-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f627-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0f627-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f627-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f627-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f627-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f627-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f627-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f627-131">See Also</span></span>  
 [<span data-ttu-id="0f627-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f627-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0f627-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f627-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0f627-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f627-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0f627-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f627-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
