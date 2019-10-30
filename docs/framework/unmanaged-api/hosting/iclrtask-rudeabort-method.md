---
title: ICLRTask::RudeAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
ms.openlocfilehash: 69e3ecfc82985d52bd5b14e9faf2566e395b622b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124660"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="91058-102">ICLRTask::RudeAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="91058-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="91058-103">Weist den Common Language Runtime (CLR) an, die Aufgabe, die von der aktuellen [ICLRTask-Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz dargestellt wird, sofort und bedingungslos abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="91058-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91058-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91058-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="91058-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91058-105">Return Value</span></span>  
  
|<span data-ttu-id="91058-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91058-106">HRESULT</span></span>|<span data-ttu-id="91058-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91058-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91058-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="91058-108">S_OK</span></span>|<span data-ttu-id="91058-109">`RudeAbort` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91058-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="91058-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91058-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91058-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="91058-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91058-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91058-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91058-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="91058-113">The call timed out.</span></span>|  
|<span data-ttu-id="91058-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91058-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91058-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="91058-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91058-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91058-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91058-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="91058-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91058-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91058-118">E_FAIL</span></span>|<span data-ttu-id="91058-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="91058-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91058-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="91058-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91058-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="91058-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91058-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91058-122">Remarks</span></span>  
 <span data-ttu-id="91058-123">Ein Host ruft `RudeAbort` auf, um eine Aufgabe sofort abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="91058-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="91058-124">Die Ausführung von Finalizern und Ausnahme Behandlungs Routinen ist nicht garantiert.</span><span class="sxs-lookup"><span data-stu-id="91058-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91058-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91058-125">Requirements</span></span>  
 <span data-ttu-id="91058-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91058-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91058-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="91058-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91058-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91058-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91058-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91058-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91058-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91058-130">See also</span></span>

- [<span data-ttu-id="91058-131">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91058-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="91058-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91058-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="91058-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91058-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="91058-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91058-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
