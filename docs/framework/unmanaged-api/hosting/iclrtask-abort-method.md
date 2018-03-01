---
title: ICLRTask::Abort-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e417e329b38c8f57dedf2926c0d6ff02a0170f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="a00c4-102">ICLRTask::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="a00c4-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="a00c4-103">Fordert an, dass die common Language Runtime (CLR) über den Task abzubrechen, die das aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="a00c4-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a00c4-104">Syntax</span></span>  
  
```  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a00c4-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a00c4-105">Return Value</span></span>  
  
|<span data-ttu-id="a00c4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a00c4-106">HRESULT</span></span>|<span data-ttu-id="a00c4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a00c4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a00c4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a00c4-108">S_OK</span></span>|<span data-ttu-id="a00c4-109">`Abort`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a00c4-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="a00c4-110">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="a00c4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a00c4-111">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a00c4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a00c4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a00c4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a00c4-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a00c4-113">The call timed out.</span></span>|  
|<span data-ttu-id="a00c4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a00c4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a00c4-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a00c4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a00c4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a00c4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a00c4-117">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a00c4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a00c4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a00c4-118">E_FAIL</span></span>|<span data-ttu-id="a00c4-119">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a00c4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a00c4-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a00c4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a00c4-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a00c4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a00c4-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a00c4-122">Remarks</span></span>  
 <span data-ttu-id="a00c4-123">Löst die CLR eine <xref:System.Threading.ThreadAbortException> Wenn der Host ruft `Abort`.</span><span class="sxs-lookup"><span data-stu-id="a00c4-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="a00c4-124">Sofort, nachdem die Ausnahmeinformationen initialisiert wird, ohne zu warten, die für Benutzercode, z. B. Finalizer oder Ausnahmebehandlungsmechanismen, führen Sie, zurück.</span><span class="sxs-lookup"><span data-stu-id="a00c4-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="a00c4-125">Aufrufe von `Abort` daher schnell zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a00c4-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00c4-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a00c4-126">Requirements</span></span>  
 <span data-ttu-id="a00c4-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a00c4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00c4-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a00c4-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a00c4-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a00c4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a00c4-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00c4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00c4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a00c4-131">See Also</span></span>  
 [<span data-ttu-id="a00c4-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a00c4-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a00c4-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a00c4-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a00c4-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a00c4-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a00c4-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a00c4-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
