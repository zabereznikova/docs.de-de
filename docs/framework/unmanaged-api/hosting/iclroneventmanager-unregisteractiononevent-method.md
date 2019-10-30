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
ms.openlocfilehash: 0f952978a2591c82b2ad3f5059070124b7873c94
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140813"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="8744d-102">ICLROnEventManager::UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="8744d-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>
<span data-ttu-id="8744d-103">Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="8744d-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8744d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8744d-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8744d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8744d-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="8744d-106">in Einer der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) -Werte, der das Ereignis angibt, für das die Registrierung des von `pAction`beschriebenen Rückruf Zeigers aufgehoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8744d-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="8744d-107">in Ein Zeiger auf ein [iaktiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Objekt, das als Parameter an die [registeraktiononevent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) -Methode übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8744d-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8744d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8744d-108">Return Value</span></span>  
  
|<span data-ttu-id="8744d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8744d-109">HRESULT</span></span>|<span data-ttu-id="8744d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8744d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8744d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8744d-111">S_OK</span></span>|<span data-ttu-id="8744d-112">`UnregisterActionOnEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8744d-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8744d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8744d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8744d-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8744d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8744d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8744d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8744d-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8744d-116">The call timed out.</span></span>|  
|<span data-ttu-id="8744d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8744d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8744d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8744d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8744d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8744d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8744d-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8744d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8744d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8744d-121">E_FAIL</span></span>|<span data-ttu-id="8744d-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8744d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8744d-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8744d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8744d-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8744d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8744d-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8744d-125">Requirements</span></span>  
 <span data-ttu-id="8744d-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8744d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8744d-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8744d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8744d-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8744d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8744d-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8744d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8744d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8744d-130">See also</span></span>

- [<span data-ttu-id="8744d-131">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="8744d-131">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="8744d-132">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8744d-132">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="8744d-133">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8744d-133">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8744d-134">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8744d-134">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
