---
title: ICLRTask::SetTaskIdentifier-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SetTaskIdentifier
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 916f4638ad8206352f3b5973bb6c8b5dab39cda4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="c2a8d-102">ICLRTask::SetTaskIdentifier-Methode</span><span class="sxs-lookup"><span data-stu-id="c2a8d-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="c2a8d-103">Weist die common Language Runtime (CLR), die der Aufgabe, die vom aktuellen Wert des angegebenen Bezeichners zuordnen [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a8d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2a8d-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2a8d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2a8d-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="c2a8d-106">[in] Der eindeutige Bezeichner für die common Language Runtime, die vom aktuellen Task zugeordnet werden soll `ICLRTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2a8d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2a8d-107">Return Value</span></span>  
  
|<span data-ttu-id="c2a8d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2a8d-108">HRESULT</span></span>|<span data-ttu-id="c2a8d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2a8d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2a8d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2a8d-110">S_OK</span></span>|<span data-ttu-id="c2a8d-111">`SetTaskIdentifier`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="c2a8d-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="c2a8d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2a8d-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2a8d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2a8d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2a8d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-115">The call timed out.</span></span>|  
|<span data-ttu-id="c2a8d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2a8d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2a8d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2a8d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2a8d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2a8d-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2a8d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2a8d-120">E_FAIL</span></span>|<span data-ttu-id="c2a8d-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2a8d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2a8d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2a8d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2a8d-124">Remarks</span></span>  
 <span data-ttu-id="c2a8d-125">Der Host kann ein Vorgang, um die CLR und dem Host in einer Debugumgebung integrieren ein Bezeichners zuordnen.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="c2a8d-126">Der Bezeichner hat keine Bedeutung für die CLR.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="c2a8d-127">Die CLR übergibt ihn an einen Debuggeranwendung.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="c2a8d-128">Der Debugger kann verwenden diesen Bezeichner einer Host-Aufrufliste eine CLR-Aufrufliste zugeordnet werden soll, und ihre jeweiligen Ablaufverfolgungsinformationen an unified werden bei der Anzeige in der Debugger-Benutzeroberfläche zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c2a8d-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a8d-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2a8d-129">Requirements</span></span>  
 <span data-ttu-id="c2a8d-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a8d-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a8d-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2a8d-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2a8d-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2a8d-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a8d-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a8d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a8d-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2a8d-134">See Also</span></span>  
 [<span data-ttu-id="c2a8d-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a8d-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c2a8d-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a8d-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c2a8d-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a8d-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c2a8d-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2a8d-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
