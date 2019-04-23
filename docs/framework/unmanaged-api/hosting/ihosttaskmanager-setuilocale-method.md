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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e110f1f5ea326c232c7c96bb05913080e950083d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158898"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="06b08-102">IHostTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="06b08-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="06b08-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) das Gebietsschema der Benutzeroberfläche (UI) oder die Kultur, für die derzeit ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="06b08-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06b08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06b08-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06b08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06b08-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="06b08-106">[in] Die Gebietsschema-ID-Wert, der die neu zugewiesene geografischen Kultur und Sprache zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="06b08-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06b08-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06b08-107">Return Value</span></span>  
  
|<span data-ttu-id="06b08-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06b08-108">HRESULT</span></span>|<span data-ttu-id="06b08-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="06b08-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06b08-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="06b08-110">S_OK</span></span>|<span data-ttu-id="06b08-111">`SetUILocale` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06b08-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="06b08-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="06b08-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="06b08-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="06b08-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="06b08-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="06b08-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="06b08-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="06b08-115">The call timed out.</span></span>|  
|<span data-ttu-id="06b08-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="06b08-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="06b08-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="06b08-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="06b08-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="06b08-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="06b08-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="06b08-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="06b08-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="06b08-120">E_FAIL</span></span>|<span data-ttu-id="06b08-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="06b08-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="06b08-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06b08-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="06b08-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="06b08-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="06b08-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="06b08-124">E_NOTIMPL</span></span>|<span data-ttu-id="06b08-125">Der Host lässt nicht verwalteter Benutzercode, der die Kultur der Benutzeroberfläche zu ändern.</span><span class="sxs-lookup"><span data-stu-id="06b08-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b08-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06b08-126">Remarks</span></span>  
 <span data-ttu-id="06b08-127">Ruft die Laufzeit `SetUILocale` Wenn der Wert des der <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> -Eigenschaft von verwaltetem Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="06b08-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="06b08-128">Diese Methode bietet eine Möglichkeit für den Host für die Synchronisierung der Gebietsschemas, die sie möglicherweise Mechanismen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="06b08-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="06b08-129">Wenn ein Host lässt sich nicht auf die UI-Gebietsschemas aus verwaltetem Code geändert werden, oder einen Mechanismus zur Synchronisierung von Gebietsschemas nicht implementiert, sollten sie diese Methode E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="06b08-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06b08-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="06b08-130">Requirements</span></span>  
 <span data-ttu-id="06b08-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06b08-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06b08-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06b08-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06b08-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="06b08-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06b08-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06b08-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b08-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b08-135">See also</span></span>

- [<span data-ttu-id="06b08-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b08-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="06b08-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b08-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="06b08-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b08-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="06b08-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06b08-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="06b08-140">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="06b08-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
