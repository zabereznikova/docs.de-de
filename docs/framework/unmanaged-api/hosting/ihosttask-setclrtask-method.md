---
title: IHostTask::SetCLRTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121368"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="52d68-102">IHostTask::SetCLRTask-Methode</span><span class="sxs-lookup"><span data-stu-id="52d68-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="52d68-103">Ordnet der aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz eine `ICLRTask` Instanz zu.</span><span class="sxs-lookup"><span data-stu-id="52d68-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52d68-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d68-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="52d68-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="52d68-106">in Ein Schnittstellen Zeiger auf die `ICLRTask`-Instanz, die der aktuellen `IHostTask` Instanz zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52d68-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52d68-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52d68-107">Return Value</span></span>  
  
|<span data-ttu-id="52d68-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52d68-108">HRESULT</span></span>|<span data-ttu-id="52d68-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52d68-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52d68-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="52d68-110">S_OK</span></span>|<span data-ttu-id="52d68-111">`SetCLRTask` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="52d68-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="52d68-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52d68-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52d68-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="52d68-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52d68-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52d68-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52d68-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="52d68-115">The call timed out.</span></span>|  
|<span data-ttu-id="52d68-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52d68-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52d68-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="52d68-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52d68-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52d68-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52d68-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="52d68-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52d68-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52d68-120">E_FAIL</span></span>|<span data-ttu-id="52d68-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="52d68-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52d68-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52d68-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52d68-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="52d68-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52d68-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52d68-124">Remarks</span></span>  
 <span data-ttu-id="52d68-125">Die CLR ruft `SetCLRTask` auf, um der aktuellen `IHostTask` Instanz eine `ICLRTask` Instanz zuzuordnen, die durch einen Aufruf von [IHostTaskManager:: kreatetask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="52d68-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d68-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52d68-126">Requirements</span></span>  
 <span data-ttu-id="52d68-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d68-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d68-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="52d68-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52d68-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52d68-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52d68-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d68-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d68-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52d68-131">See also</span></span>

- [<span data-ttu-id="52d68-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52d68-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="52d68-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52d68-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="52d68-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52d68-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="52d68-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52d68-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
