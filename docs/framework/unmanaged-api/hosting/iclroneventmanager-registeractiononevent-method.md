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
ms.openlocfilehash: e634b3876d51d461446ed3f5ae537ac1db1545bd
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703502"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="b4630-102">ICLROnEventManager::RegisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="b4630-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="b4630-103">Registriert einen Rückruf Zeiger für das angegebene Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b4630-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4630-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4630-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4630-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4630-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="b4630-106">in Einer der [EClrEvent](eclrevent-enumeration.md) -Werte, der das Ereignis angibt, für das der von beschriebene Rückruf Zeiger registriert werden soll `pAction` .</span><span class="sxs-lookup"><span data-stu-id="b4630-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="b4630-107">in Ein Zeiger auf ein [iaktiononclrevent](iactiononclrevent-interface.md) -Objekt, das aufgerufen wird, wenn das registrierte Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b4630-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4630-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4630-108">Return Value</span></span>  
  
|<span data-ttu-id="b4630-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4630-109">HRESULT</span></span>|<span data-ttu-id="b4630-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b4630-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4630-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4630-111">S_OK</span></span>|<span data-ttu-id="b4630-112">`RegisterActionOnEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4630-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b4630-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4630-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4630-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b4630-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4630-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4630-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4630-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b4630-116">The call timed out.</span></span>|  
|<span data-ttu-id="b4630-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4630-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4630-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b4630-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4630-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4630-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4630-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b4630-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4630-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4630-121">E_FAIL</span></span>|<span data-ttu-id="b4630-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b4630-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4630-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4630-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4630-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b4630-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4630-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4630-125">Remarks</span></span>  
 <span data-ttu-id="b4630-126">Der Host kann Rückrufe für einen oder beide der beiden Ereignis Typen registrieren, die von beschrieben werden `EClrEvent` .</span><span class="sxs-lookup"><span data-stu-id="b4630-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="b4630-127">Der Host ruft die- `ICLROnEventManager` Schnittstelle durch Aufrufen der [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) -Methode ab.</span><span class="sxs-lookup"><span data-stu-id="b4630-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4630-128">Die Ereignisse, die `RegisterActionOnEvent` registriert werden, können mehrmals und aus unterschiedlichen Threads ausgelöst werden, um ein Entladen oder das Deaktivieren der CLR zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="b4630-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4630-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4630-129">Requirements</span></span>  
 <span data-ttu-id="b4630-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4630-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4630-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b4630-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4630-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4630-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4630-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4630-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4630-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4630-134">See also</span></span>

- [<span data-ttu-id="b4630-135">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b4630-135">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="b4630-136">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4630-136">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="b4630-137">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4630-137">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="b4630-138">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4630-138">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
