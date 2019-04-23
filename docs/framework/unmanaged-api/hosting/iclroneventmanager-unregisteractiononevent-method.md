---
title: ICLROnEventManager::UnregisterActionOnEvent-Methode
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.UnregisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::UnregisterActionOnEvent
helpviewer_keywords:
- UnRegisterActionOnEvent method [.NET Framework hosting]
- ICLROnEventManager::UnRegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: 4c02ec37-cdf0-46b2-890e-235092741236
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54abd54662d4e99881dddf15876b596a4a705f70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108900"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="81993-102">ICLROnEventManager::UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="81993-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="81993-103">Hebt die Registrierung eines bereits registrierten Rückrufzeigers für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="81993-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81993-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81993-104">Syntax</span></span>  
  
```  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81993-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81993-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="81993-106">[in] Eines der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) Werte, der das Ereignis für das Aufheben der Registrierung des Rückrufzeigers beschriebenen `pAction`.</span><span class="sxs-lookup"><span data-stu-id="81993-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="81993-107">[in] Ein Zeiger auf ein [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Objekt, das als Parameter übergeben wurde die [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="81993-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81993-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81993-108">Return Value</span></span>  
  
|<span data-ttu-id="81993-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81993-109">HRESULT</span></span>|<span data-ttu-id="81993-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81993-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="81993-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="81993-111">S_OK</span></span>|<span data-ttu-id="81993-112">`UnregisterActionOnEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81993-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="81993-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="81993-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="81993-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="81993-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="81993-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="81993-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="81993-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="81993-116">The call timed out.</span></span>|  
|<span data-ttu-id="81993-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="81993-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="81993-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="81993-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="81993-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="81993-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="81993-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="81993-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="81993-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="81993-121">E_FAIL</span></span>|<span data-ttu-id="81993-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="81993-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="81993-123">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="81993-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="81993-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="81993-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81993-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81993-125">Requirements</span></span>  
 <span data-ttu-id="81993-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81993-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81993-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="81993-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81993-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="81993-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81993-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81993-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81993-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81993-130">See also</span></span>

- [<span data-ttu-id="81993-131">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="81993-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="81993-132">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81993-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="81993-133">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81993-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="81993-134">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81993-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
