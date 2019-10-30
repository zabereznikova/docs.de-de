---
title: IHostTaskManager::SetUILocale-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
ms.openlocfilehash: a929a125fc8c70744246f4f96d8a09a4605f537c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132944"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="b4ebb-102">IHostTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="b4ebb-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="b4ebb-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) das Gebiets Schema der Benutzeroberfläche (UI) für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ebb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4ebb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ebb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4ebb-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="b4ebb-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4ebb-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4ebb-107">Return Value</span></span>  
  
|<span data-ttu-id="b4ebb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4ebb-108">HRESULT</span></span>|<span data-ttu-id="b4ebb-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4ebb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4ebb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4ebb-110">S_OK</span></span>|<span data-ttu-id="b4ebb-111">`SetUILocale` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="b4ebb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4ebb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4ebb-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4ebb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4ebb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4ebb-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-115">The call timed out.</span></span>|  
|<span data-ttu-id="b4ebb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4ebb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4ebb-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4ebb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4ebb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4ebb-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4ebb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4ebb-120">E_FAIL</span></span>|<span data-ttu-id="b4ebb-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4ebb-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4ebb-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4ebb-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b4ebb-124">E_NOTIMPL</span></span>|<span data-ttu-id="b4ebb-125">Der Host lässt nicht zu, dass der verwaltete Benutzercode die Benutzeroberflächen Kultur ändert.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4ebb-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4ebb-126">Remarks</span></span>  
 <span data-ttu-id="b4ebb-127">Die Laufzeit ruft `SetUILocale` auf, wenn der Wert der <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft von verwaltetem Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="b4ebb-128">Diese Methode bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="b4ebb-129">Wenn ein Host nicht zulässt, dass das UI-Gebiets Schema aus verwaltetem Code geändert werden kann oder keinen Mechanismus zum Synchronisieren von Gebiets Schemas implementiert, sollte er E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b4ebb-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ebb-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4ebb-130">Requirements</span></span>  
 <span data-ttu-id="b4ebb-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ebb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ebb-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b4ebb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4ebb-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4ebb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4ebb-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ebb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ebb-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4ebb-135">See also</span></span>

- [<span data-ttu-id="b4ebb-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4ebb-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b4ebb-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4ebb-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b4ebb-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4ebb-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b4ebb-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4ebb-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b4ebb-140">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="b4ebb-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
