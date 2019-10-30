---
title: ICLRTask::ExitTask-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: 3f6ccf2eb25e96e0f94c558fb642b153ae3472c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124895"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="ffe50-102">ICLRTask::ExitTask-Methode</span><span class="sxs-lookup"><span data-stu-id="ffe50-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="ffe50-103">Benachrichtigt den Common Language Runtime (CLR), dass die durch die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz dargestellte Aufgabe beendet wird, und versucht, die Aufgabe ordnungsgemäß zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ffe50-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffe50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ffe50-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ffe50-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ffe50-105">Return Value</span></span>  
  
|<span data-ttu-id="ffe50-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffe50-106">HRESULT</span></span>|<span data-ttu-id="ffe50-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ffe50-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffe50-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffe50-108">S_OK</span></span>|<span data-ttu-id="ffe50-109">`ExitTask` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ffe50-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="ffe50-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffe50-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffe50-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ffe50-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffe50-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffe50-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffe50-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ffe50-113">The call timed out.</span></span>|  
|<span data-ttu-id="ffe50-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffe50-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffe50-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ffe50-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffe50-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffe50-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffe50-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ffe50-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffe50-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffe50-118">E_FAIL</span></span>|<span data-ttu-id="ffe50-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ffe50-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffe50-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffe50-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffe50-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ffe50-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffe50-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ffe50-122">Remarks</span></span>  
 <span data-ttu-id="ffe50-123">`ExitTask` versucht, eine Aufgabe ordnungsgemäß herunterzufahren, analog zum Trennen eines Threads von einer nicht verwalteten Typbibliothek.</span><span class="sxs-lookup"><span data-stu-id="ffe50-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffe50-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ffe50-124">Requirements</span></span>  
 <span data-ttu-id="ffe50-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffe50-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffe50-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ffe50-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffe50-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ffe50-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffe50-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffe50-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe50-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffe50-129">See also</span></span>

- [<span data-ttu-id="ffe50-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe50-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ffe50-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe50-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ffe50-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe50-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ffe50-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ffe50-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
