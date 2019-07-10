---
title: IHostTaskManager::GetCurrentTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3044927e0d9975ed9347cd4f4896b3b75d3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749625"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="24ce0-102">IHostTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="24ce0-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="24ce0-103">Ruft einen Schnittstellenzeiger auf die Aufgabe, die derzeit für den Betriebssystem-Thread ausgeführt wird, von dem dieser Aufruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="24ce0-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ce0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24ce0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ce0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24ce0-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="24ce0-106">[out] Ein Zeiger auf die Adresse einer [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, der aktuell ausgeführten Aufgabe oder Null, darstellt, wenn keine Aufgabe derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24ce0-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24ce0-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="24ce0-107">Return Value</span></span>  
  
|<span data-ttu-id="24ce0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24ce0-108">HRESULT</span></span>|<span data-ttu-id="24ce0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24ce0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="24ce0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="24ce0-110">S_OK</span></span>|<span data-ttu-id="24ce0-111">`GetCurrentTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24ce0-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="24ce0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="24ce0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="24ce0-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="24ce0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="24ce0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="24ce0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="24ce0-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="24ce0-115">The call timed out.</span></span>|  
|<span data-ttu-id="24ce0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="24ce0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="24ce0-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="24ce0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="24ce0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="24ce0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="24ce0-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="24ce0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="24ce0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="24ce0-120">E_FAIL</span></span>|<span data-ttu-id="24ce0-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="24ce0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="24ce0-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="24ce0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="24ce0-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="24ce0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="24ce0-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="24ce0-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="24ce0-125">`GetCurrentTask` wurde ein Betriebssystemthread außerhalb der Kontrolle des Hosts aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="24ce0-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24ce0-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24ce0-126">Remarks</span></span>  
 <span data-ttu-id="24ce0-127">Der Host kann auch festlegen, die `pTask` Parameter auf null, um zu verhindern, dass eine Aufgabe, die sie nicht initiiert haben in der CLR.</span><span class="sxs-lookup"><span data-stu-id="24ce0-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ce0-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24ce0-128">Requirements</span></span>  
 <span data-ttu-id="24ce0-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ce0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ce0-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="24ce0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24ce0-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24ce0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24ce0-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ce0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ce0-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24ce0-133">See also</span></span>

- [<span data-ttu-id="24ce0-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24ce0-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="24ce0-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24ce0-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="24ce0-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24ce0-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="24ce0-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24ce0-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
