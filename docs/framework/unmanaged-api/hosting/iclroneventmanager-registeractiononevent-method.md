---
title: ICLROnEventManager::RegisterActionOnEvent-Methode
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: 4068166438c524ad1c0ed4efe455b1f66b6641d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140826"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="62a15-102">ICLROnEventManager::RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="62a15-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="62a15-103">Registriert einen Rückruf Zeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="62a15-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62a15-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62a15-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="62a15-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="62a15-106">in Einer der [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) -Werte, der das Ereignis angibt, für das der von `pAction`beschriebene Rückruf Zeiger registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="62a15-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="62a15-107">in Ein Zeiger auf ein [iaktiononclrevent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) -Objekt, das aufgerufen wird, wenn das registrierte Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="62a15-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62a15-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62a15-108">Return Value</span></span>  
  
|<span data-ttu-id="62a15-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="62a15-109">HRESULT</span></span>|<span data-ttu-id="62a15-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62a15-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="62a15-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="62a15-111">S_OK</span></span>|<span data-ttu-id="62a15-112">`RegisterActionOnEvent` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="62a15-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="62a15-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="62a15-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="62a15-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="62a15-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="62a15-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="62a15-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="62a15-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="62a15-116">The call timed out.</span></span>|  
|<span data-ttu-id="62a15-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="62a15-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="62a15-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="62a15-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="62a15-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="62a15-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="62a15-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="62a15-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="62a15-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="62a15-121">E_FAIL</span></span>|<span data-ttu-id="62a15-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62a15-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="62a15-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62a15-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="62a15-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="62a15-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62a15-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62a15-125">Remarks</span></span>  
 <span data-ttu-id="62a15-126">Der Host kann Rückrufe für einen oder beide der beiden Ereignis Typen registrieren, die durch `EClrEvent`beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="62a15-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="62a15-127">Der Host ruft die `ICLROnEventManager`-Schnittstelle durch Aufrufen der [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode ab.</span><span class="sxs-lookup"><span data-stu-id="62a15-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62a15-128">Die Ereignisse, die `RegisterActionOnEvent` Register, können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="62a15-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a15-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62a15-129">Requirements</span></span>  
 <span data-ttu-id="62a15-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62a15-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62a15-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="62a15-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62a15-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="62a15-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62a15-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62a15-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a15-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62a15-134">See also</span></span>

- [<span data-ttu-id="62a15-135">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="62a15-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="62a15-136">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62a15-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="62a15-137">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62a15-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="62a15-138">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="62a15-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
