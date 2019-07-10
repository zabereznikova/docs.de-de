---
title: IHostTaskManager::SetCLRTaskManager-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5008461acc3b0653c53cee70cbfe89c90a440b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749393"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="d5e6c-102">IHostTaskManager::SetCLRTaskManager-Methode</span><span class="sxs-lookup"><span data-stu-id="d5e6c-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="d5e6c-103">Bietet einen Schnittstellenzeiger auf den Host ein [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) -Instanz, von der common Language Runtime (CLR) implementiert.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5e6c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5e6c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5e6c-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="d5e6c-106">[in] Ein Zeiger auf ein `ICLRTaskManager` Instanz, die von der common Language Runtime implementiert.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5e6c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d5e6c-107">Return Value</span></span>  
  
|<span data-ttu-id="d5e6c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5e6c-108">HRESULT</span></span>|<span data-ttu-id="d5e6c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5e6c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d5e6c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d5e6c-110">S_OK</span></span>|<span data-ttu-id="d5e6c-111">`SetCLRTaskManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="d5e6c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d5e6c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d5e6c-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d5e6c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d5e6c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d5e6c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-115">The call timed out.</span></span>|  
|<span data-ttu-id="d5e6c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d5e6c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d5e6c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d5e6c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d5e6c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d5e6c-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d5e6c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d5e6c-120">E_FAIL</span></span>|<span data-ttu-id="d5e6c-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d5e6c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d5e6c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5e6c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5e6c-124">Remarks</span></span>  
 <span data-ttu-id="d5e6c-125">Ruft die Laufzeit `SetCLRTaskManager` für einen Schnittstellenzeiger auf den Host bereit ein `ICLRTaskManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="d5e6c-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5e6c-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5e6c-126">Requirements</span></span>  
 <span data-ttu-id="d5e6c-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e6c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e6c-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5e6c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5e6c-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5e6c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5e6c-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e6c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e6c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5e6c-131">See also</span></span>

- [<span data-ttu-id="d5e6c-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e6c-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d5e6c-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e6c-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d5e6c-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e6c-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d5e6c-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5e6c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
