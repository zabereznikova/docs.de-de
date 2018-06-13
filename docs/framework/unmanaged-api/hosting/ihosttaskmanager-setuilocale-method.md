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
ms.openlocfilehash: f929dceafc72af89cfd85b1617de7bbd0bc0dfff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442745"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="8728c-102">IHostTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="8728c-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="8728c-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) das Gebietsschema der Benutzeroberfläche (UI) oder die Kultur, auf die gerade ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="8728c-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8728c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8728c-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8728c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8728c-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="8728c-106">[in] Der Wert der Gebietsschema-Bezeichner, der die neu zugewiesene geografische Kultur und Sprache zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="8728c-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8728c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8728c-107">Return Value</span></span>  
  
|<span data-ttu-id="8728c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8728c-108">HRESULT</span></span>|<span data-ttu-id="8728c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8728c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8728c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8728c-110">S_OK</span></span>|<span data-ttu-id="8728c-111">`SetUILocale` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8728c-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="8728c-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="8728c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8728c-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="8728c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8728c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8728c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8728c-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8728c-115">The call timed out.</span></span>|  
|<span data-ttu-id="8728c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8728c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8728c-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8728c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8728c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8728c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8728c-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8728c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8728c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8728c-120">E_FAIL</span></span>|<span data-ttu-id="8728c-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="8728c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8728c-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="8728c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8728c-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8728c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8728c-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8728c-124">E_NOTIMPL</span></span>|<span data-ttu-id="8728c-125">Der Host lässt nicht verwalteter Benutzercode, der die Kultur der Benutzeroberfläche ändern.</span><span class="sxs-lookup"><span data-stu-id="8728c-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8728c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8728c-126">Remarks</span></span>  
 <span data-ttu-id="8728c-127">Ruft die Laufzeit `SetUILocale` Wenn der Wert von der <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> -Eigenschaft von verwaltetem Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="8728c-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="8728c-128">Diese Methode bietet die Möglichkeit für den Host Mechanismen, die sie möglicherweise für die Synchronisierung von Gebietsschemas auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8728c-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="8728c-129">Wenn ein Host lässt sich nicht auf das Gebietsschema der Benutzeroberfläche von verwaltetem Code geändert werden oder einen Mechanismus zum Synchronisieren von Gebietsschemas nicht implementiert, sollte es E_NOTIMPL von dieser Methode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="8728c-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8728c-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8728c-130">Requirements</span></span>  
 <span data-ttu-id="8728c-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8728c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8728c-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8728c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8728c-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8728c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8728c-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8728c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8728c-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8728c-135">See Also</span></span>  
 [<span data-ttu-id="8728c-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8728c-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="8728c-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8728c-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="8728c-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8728c-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="8728c-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8728c-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="8728c-140">SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="8728c-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
