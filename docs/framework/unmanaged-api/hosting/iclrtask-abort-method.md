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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e48292d1b0bfaa990cca1b290f769d96938d433
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759025"
---
# <a name="iclrtaskabort-method"></a><span data-ttu-id="a25ac-102">ICLRTask::Abort-Methode</span><span class="sxs-lookup"><span data-stu-id="a25ac-102">ICLRTask::Abort Method</span></span>
<span data-ttu-id="a25ac-103">Fordert an, dass die common Language Runtime (CLR) die Aufgabe abzubrechen, die die aktuelle [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) -Instanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="a25ac-103">Requests that the common language runtime (CLR) abort the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a25ac-104">Syntax</span></span>  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a25ac-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a25ac-105">Return Value</span></span>  
  
|<span data-ttu-id="a25ac-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a25ac-106">HRESULT</span></span>|<span data-ttu-id="a25ac-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a25ac-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a25ac-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a25ac-108">S_OK</span></span>|<span data-ttu-id="a25ac-109">`Abort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a25ac-109">`Abort` returned successfully.</span></span>|  
|<span data-ttu-id="a25ac-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a25ac-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a25ac-111">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a25ac-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a25ac-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a25ac-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a25ac-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a25ac-113">The call timed out.</span></span>|  
|<span data-ttu-id="a25ac-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a25ac-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a25ac-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a25ac-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a25ac-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a25ac-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a25ac-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a25ac-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a25ac-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a25ac-118">E_FAIL</span></span>|<span data-ttu-id="a25ac-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a25ac-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a25ac-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a25ac-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a25ac-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a25ac-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a25ac-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a25ac-122">Remarks</span></span>  
 <span data-ttu-id="a25ac-123">Die CLR löst eine <xref:System.Threading.ThreadAbortException> Wenn der Host ruft `Abort`.</span><span class="sxs-lookup"><span data-stu-id="a25ac-123">The CLR raises a <xref:System.Threading.ThreadAbortException> when the host calls `Abort`.</span></span> <span data-ttu-id="a25ac-124">Sofort, nachdem die Ausnahmeinformationen initialisiert wird, ohne Wartezeiten für Benutzercode, z. B. Finalizer oder Ausnahmebehandlungsmechanismen, auszuführen, zurück.</span><span class="sxs-lookup"><span data-stu-id="a25ac-124">It returns immediately after the exception information is initialized, without waiting for user code, such as finalizers or exception handling mechanisms, to execute.</span></span> <span data-ttu-id="a25ac-125">Aufrufe von `Abort` so schnell zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a25ac-125">Calls to `Abort` thus return quickly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a25ac-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a25ac-126">Requirements</span></span>  
 <span data-ttu-id="a25ac-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a25ac-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a25ac-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a25ac-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a25ac-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a25ac-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a25ac-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a25ac-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a25ac-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a25ac-131">See also</span></span>

- [<span data-ttu-id="a25ac-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a25ac-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a25ac-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a25ac-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a25ac-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a25ac-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a25ac-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a25ac-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
