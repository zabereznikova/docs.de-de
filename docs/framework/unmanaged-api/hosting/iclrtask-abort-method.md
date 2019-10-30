---
title: ICLRTask::Abort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.Abort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Abort
helpviewer_keywords:
- ICLRTask::Abort method [.NET Framework hosting]
- Abort method, ICLRTask interface [.NET Framework hosting]
ms.assetid: b3594b5f-2e41-4e36-9096-3586276a138c
topic_type:
- apiref
ms.openlocfilehash: 026d4c14abed030b80e8e1b3f8363fbd59ac05e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124918"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="2b7f8-102">ICLRTask::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="2b7f8-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="2b7f8-103">Fordert an, dass die Common Language Runtime (CLR) den Task abbrechen, den die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b7f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b7f8-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="2b7f8-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2b7f8-105">Return Value</span></span>  
  
|<span data-ttu-id="2b7f8-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b7f8-106">HRESULT</span></span>|<span data-ttu-id="2b7f8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b7f8-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b7f8-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b7f8-108">S_OK</span></span>|<span data-ttu-id="2b7f8-109">`Abort` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="2b7f8-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b7f8-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b7f8-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b7f8-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b7f8-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b7f8-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-113">The call timed out.</span></span>|  
|<span data-ttu-id="2b7f8-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b7f8-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b7f8-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b7f8-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b7f8-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b7f8-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b7f8-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b7f8-118">E_FAIL</span></span>|<span data-ttu-id="2b7f8-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b7f8-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b7f8-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b7f8-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b7f8-122">Remarks</span></span>  
 <span data-ttu-id="2b7f8-123">Die CLR löst eine <xref:System.Threading.ThreadAbortException> aus, wenn der Host `Abort`aufruft.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="2b7f8-124">Sie wird unmittelbar nach der Initialisierung der Ausnahme Informationen zurückgegeben, ohne darauf zu warten, dass Benutzercode (z. b. Finalizer oder Ausnahme Behandlungs Mechanismen) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="2b7f8-125">Aufrufe von `Abort` daher schnell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b7f8-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b7f8-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b7f8-126">Requirements</span></span>  
 <span data-ttu-id="2b7f8-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b7f8-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b7f8-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2b7f8-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b7f8-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2b7f8-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b7f8-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b7f8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7f8-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b7f8-131">See also</span></span>

- [<span data-ttu-id="2b7f8-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b7f8-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2b7f8-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b7f8-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2b7f8-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b7f8-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2b7f8-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b7f8-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
