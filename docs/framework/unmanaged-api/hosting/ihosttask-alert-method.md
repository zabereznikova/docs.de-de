---
title: IHostTask::Alert-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75b3fc0b1dde35e743e699d22c5766cab4cf0faf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964719"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="d95fe-102">IHostTask::Alert-Methode</span><span class="sxs-lookup"><span data-stu-id="d95fe-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="d95fe-103">Fordert an, dass der Host die Aufgabe aktiviert, die von der aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz dargestellt wird, sodass der Task abgebrochen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d95fe-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d95fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d95fe-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d95fe-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d95fe-105">Return Value</span></span>  
  
|<span data-ttu-id="d95fe-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d95fe-106">HRESULT</span></span>|<span data-ttu-id="d95fe-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d95fe-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d95fe-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d95fe-108">S_OK</span></span>|<span data-ttu-id="d95fe-109">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d95fe-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="d95fe-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d95fe-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d95fe-111">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d95fe-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d95fe-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d95fe-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d95fe-113">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d95fe-113">The call timed out.</span></span>|  
|<span data-ttu-id="d95fe-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d95fe-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d95fe-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d95fe-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d95fe-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d95fe-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d95fe-117">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d95fe-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d95fe-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d95fe-118">E_FAIL</span></span>|<span data-ttu-id="d95fe-119">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d95fe-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d95fe-120">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d95fe-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d95fe-121">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d95fe-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d95fe-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d95fe-122">Remarks</span></span>  
 <span data-ttu-id="d95fe-123">Die CLR ruft die `Alert` -Methode <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> auf, wenn von Benutzercode aufgerufen wird, <xref:System.AppDomain> oder wenn der dem <xref:System.Threading.Thread> aktuellen zugeordnete heruntergefahren wird.</span><span class="sxs-lookup"><span data-stu-id="d95fe-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="d95fe-124">Der Host muss sofort zurückkehren, da der-Befehl asynchron erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d95fe-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="d95fe-125">Wenn der Host die Aufgabe nicht sofort benachrichtigen kann, muss Sie beim nächsten Eintritt in einen Zustand reaktiviert werden, in dem Sie benachrichtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d95fe-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d95fe-126">`Alert`wirkt sich nur auf die Tasks aus, an die die Laufzeit einen [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Wert von WAIT_ALERTABLE an Methoden wie [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)übermittelt hat.</span><span class="sxs-lookup"><span data-stu-id="d95fe-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d95fe-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d95fe-127">Requirements</span></span>  
 <span data-ttu-id="d95fe-128">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d95fe-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d95fe-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d95fe-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d95fe-130">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d95fe-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d95fe-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d95fe-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95fe-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d95fe-132">See also</span></span>

- [<span data-ttu-id="d95fe-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d95fe-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d95fe-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d95fe-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d95fe-135">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d95fe-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d95fe-136">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d95fe-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
