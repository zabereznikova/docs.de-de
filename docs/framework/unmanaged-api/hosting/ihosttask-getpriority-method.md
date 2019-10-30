---
title: IHostTask::GetPriority-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
ms.openlocfilehash: 6c33fa6d2e6cb09f013c5334461e61235db549f7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121419"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="ab0d2-102">IHostTask::GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="ab0d2-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="ab0d2-103">Ruft die Thread Prioritäts Ebene der Aufgabe ab, die durch die aktuelle [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab0d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab0d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab0d2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab0d2-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="ab0d2-106">vorgenommen Ein Zeiger auf eine ganze Zahl, die die Thread Prioritäts Ebene der Aufgabe angibt, die durch die aktuelle `IHostTask`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab0d2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab0d2-107">Return Value</span></span>  
  
|<span data-ttu-id="ab0d2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab0d2-108">HRESULT</span></span>|<span data-ttu-id="ab0d2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab0d2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab0d2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab0d2-110">S_OK</span></span>|<span data-ttu-id="ab0d2-111">`GetPriority` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="ab0d2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab0d2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab0d2-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab0d2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab0d2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab0d2-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-115">The call timed out.</span></span>|  
|<span data-ttu-id="ab0d2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab0d2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab0d2-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab0d2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab0d2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab0d2-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab0d2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab0d2-120">E_FAIL</span></span>|<span data-ttu-id="ab0d2-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab0d2-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab0d2-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab0d2-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab0d2-124">Remarks</span></span>  
 <span data-ttu-id="ab0d2-125">Werte der Thread Prioritäts Ebene werden durch die Win32-`SetThreadPriority` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="ab0d2-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab0d2-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab0d2-126">Requirements</span></span>  
 <span data-ttu-id="ab0d2-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab0d2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab0d2-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ab0d2-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab0d2-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ab0d2-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab0d2-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab0d2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab0d2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab0d2-131">See also</span></span>

- [<span data-ttu-id="ab0d2-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab0d2-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ab0d2-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab0d2-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ab0d2-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab0d2-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ab0d2-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab0d2-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
