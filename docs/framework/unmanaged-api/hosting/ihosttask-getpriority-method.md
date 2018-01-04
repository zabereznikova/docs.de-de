---
title: IHostTask::GetPriority-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.GetPriority
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 468a2e29ed3c031889fdc5df3d4defa6506d8fcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="bda59-102">IHostTask::GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="bda59-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="bda59-103">Ruft die Prioritätsebene der Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="bda59-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bda59-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bda59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bda59-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="bda59-106">[out] Ein Zeiger auf eine ganze Zahl, die die Prioritätsebene der Aufgabe, die vom aktuellen `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="bda59-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bda59-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bda59-107">Return Value</span></span>  
  
|<span data-ttu-id="bda59-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bda59-108">HRESULT</span></span>|<span data-ttu-id="bda59-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bda59-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bda59-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bda59-110">S_OK</span></span>|<span data-ttu-id="bda59-111">`GetPriority`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bda59-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="bda59-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="bda59-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bda59-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="bda59-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bda59-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bda59-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bda59-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="bda59-115">The call timed out.</span></span>|  
|<span data-ttu-id="bda59-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bda59-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bda59-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="bda59-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bda59-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bda59-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bda59-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="bda59-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bda59-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bda59-120">E_FAIL</span></span>|<span data-ttu-id="bda59-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="bda59-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bda59-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="bda59-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bda59-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="bda59-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bda59-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bda59-124">Remarks</span></span>  
 <span data-ttu-id="bda59-125">Ebene Thread Priority-Werte werden definiert, durch die Win32- `SetThreadPriority` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bda59-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda59-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bda59-126">Requirements</span></span>  
 <span data-ttu-id="bda59-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda59-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda59-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bda59-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bda59-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bda59-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bda59-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda59-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda59-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bda59-131">See Also</span></span>  
 [<span data-ttu-id="bda59-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda59-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="bda59-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda59-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="bda59-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda59-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="bda59-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bda59-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
