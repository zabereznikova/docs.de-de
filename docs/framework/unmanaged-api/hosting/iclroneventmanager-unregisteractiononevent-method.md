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
ms.openlocfilehash: ca3c7fe813f22d3beab3087414100b3d8e5814ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725598"
---
# <a name="iclroneventmanagerunregisteractiononevent-method"></a><span data-ttu-id="973c5-102">ICLROnEventManager::UnregisterActionOnEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="973c5-102">ICLROnEventManager::UnregisterActionOnEvent Method</span></span>

<span data-ttu-id="973c5-103">Hebt die Registrierung eines zuvor registrierten Rückruf Zeigers für das angegebene Ereignis auf.</span><span class="sxs-lookup"><span data-stu-id="973c5-103">Unregisters a previously registered callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="973c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="973c5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnregisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="973c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="973c5-105">Parameters</span></span>  

 `event`  
 <span data-ttu-id="973c5-106">in Einer der [EClrEvent](eclrevent-enumeration.md) -Werte, der das Ereignis angibt, für das die Registrierung des von beschriebenen Rückruf Zeigers aufgehoben werden soll `pAction` .</span><span class="sxs-lookup"><span data-stu-id="973c5-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, indicating the event for which to unregister the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="973c5-107">in Ein Zeiger auf ein [iaktiononclrevent](iactiononclrevent-interface.md) -Objekt, das als Parameter an die [registeraktiononevent](iclroneventmanager-registeractiononevent-method.md) -Methode übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="973c5-107">[in] A pointer to an [IActionOnCLREvent](iactiononclrevent-interface.md) object that was passed as a parameter to the [RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="973c5-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="973c5-108">Return Value</span></span>  
  
|<span data-ttu-id="973c5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="973c5-109">HRESULT</span></span>|<span data-ttu-id="973c5-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="973c5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="973c5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="973c5-111">S_OK</span></span>|<span data-ttu-id="973c5-112">`UnregisterActionOnEvent` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="973c5-112">`UnregisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="973c5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="973c5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="973c5-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="973c5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="973c5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="973c5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="973c5-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="973c5-116">The call timed out.</span></span>|  
|<span data-ttu-id="973c5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="973c5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="973c5-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="973c5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="973c5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="973c5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="973c5-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="973c5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="973c5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="973c5-121">E_FAIL</span></span>|<span data-ttu-id="973c5-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="973c5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="973c5-123">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="973c5-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="973c5-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="973c5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="973c5-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="973c5-125">Requirements</span></span>  

 <span data-ttu-id="973c5-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="973c5-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="973c5-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="973c5-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="973c5-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="973c5-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="973c5-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="973c5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="973c5-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="973c5-130">See also</span></span>

- [<span data-ttu-id="973c5-131">EClrEvent-Enumeration</span><span class="sxs-lookup"><span data-stu-id="973c5-131">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="973c5-132">IActionOnCLREvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="973c5-132">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="973c5-133">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="973c5-133">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="973c5-134">ICLROnEventManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="973c5-134">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
