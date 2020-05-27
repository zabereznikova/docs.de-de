---
title: IHostTaskManager::SetLocale-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: 747ee407-ee8c-484d-9583-25089236d2d1
topic_type:
- apiref
ms.openlocfilehash: 841827017262b731fd5e6f6bd0b5862fecaf2744
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841723"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="91f12-102">IHostTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="91f12-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="91f12-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) das Gebiets Schema oder die Kultur für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="91f12-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91f12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91f12-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91f12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91f12-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="91f12-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="91f12-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91f12-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91f12-107">Return Value</span></span>  
  
|<span data-ttu-id="91f12-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91f12-108">HRESULT</span></span>|<span data-ttu-id="91f12-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91f12-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="91f12-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="91f12-110">S_OK</span></span>|<span data-ttu-id="91f12-111">`SetLocale`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="91f12-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="91f12-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="91f12-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="91f12-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="91f12-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="91f12-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="91f12-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="91f12-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="91f12-115">The call timed out.</span></span>|  
|<span data-ttu-id="91f12-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="91f12-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="91f12-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="91f12-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="91f12-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="91f12-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="91f12-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="91f12-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="91f12-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="91f12-120">E_FAIL</span></span>|<span data-ttu-id="91f12-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="91f12-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="91f12-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="91f12-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="91f12-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="91f12-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="91f12-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="91f12-124">E_NOTIMPL</span></span>|<span data-ttu-id="91f12-125">Der Host lässt nicht zu, dass das Gebiets Schema von verwaltetem Benutzercode geändert wird.</span><span class="sxs-lookup"><span data-stu-id="91f12-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91f12-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91f12-126">Remarks</span></span>  
 <span data-ttu-id="91f12-127">Die Laufzeit wird aufgerufen, `SetLocale` Wenn der Wert der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> Eigenschaft von verwaltetem Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="91f12-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="91f12-128">Diese Methode bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="91f12-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="91f12-129">Wenn ein Host nicht zulässt, dass das Gebiets Schema aus verwaltetem Code geändert wird, oder keinen Mechanismus zum Synchronisieren von Gebiets Schemas implementiert, sollte er E_NOTIMPL aus dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="91f12-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91f12-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91f12-130">Requirements</span></span>  
 <span data-ttu-id="91f12-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91f12-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91f12-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="91f12-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91f12-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91f12-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91f12-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91f12-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f12-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91f12-135">See also</span></span>

- [<span data-ttu-id="91f12-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91f12-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="91f12-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91f12-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="91f12-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91f12-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="91f12-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91f12-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="91f12-140">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="91f12-140">SetUILocale Method</span></span>](ihosttaskmanager-setuilocale-method.md)
