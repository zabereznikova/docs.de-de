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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77f0196e667e2d7bb148c07218a7e39f52a37809
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474314"
---
# <a name="ihosttaskmanagersetlocale-method"></a><span data-ttu-id="7a518-102">IHostTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="7a518-102">IHostTaskManager::SetLocale Method</span></span>
<span data-ttu-id="7a518-103">Benachrichtigt den Host, dass die common Language Runtime (CLR), Gebietsschema oder der Kultur, für die derzeit ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="7a518-103">Notifies the host that the common language runtime (CLR) has changed the locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a518-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a518-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a518-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a518-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="7a518-106">[in] Die Gebietsschema-ID-Wert, der die neu zugewiesene geografischen Kultur und Sprache zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7a518-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a518-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a518-107">Return Value</span></span>  
  
|<span data-ttu-id="7a518-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a518-108">HRESULT</span></span>|<span data-ttu-id="7a518-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a518-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7a518-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7a518-110">S_OK</span></span>|<span data-ttu-id="7a518-111">`SetLocale` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a518-111">`SetLocale` returned successfully.</span></span>|  
|<span data-ttu-id="7a518-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7a518-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7a518-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7a518-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7a518-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7a518-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7a518-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a518-115">The call timed out.</span></span>|  
|<span data-ttu-id="7a518-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a518-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7a518-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7a518-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7a518-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7a518-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7a518-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7a518-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7a518-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7a518-120">E_FAIL</span></span>|<span data-ttu-id="7a518-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7a518-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7a518-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a518-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7a518-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7a518-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7a518-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7a518-124">E_NOTIMPL</span></span>|<span data-ttu-id="7a518-125">Der Host lässt nicht verwalteter Benutzercode, der das Gebietsschema zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7a518-125">The host does not allow managed user code to modify the locale.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a518-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a518-126">Remarks</span></span>  
 <span data-ttu-id="7a518-127">Ruft die Laufzeit `SetLocale` Wenn der Wert des der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> -Eigenschaft von verwaltetem Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="7a518-127">The runtime calls `SetLocale` when the value of the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="7a518-128">Diese Methode bietet eine Möglichkeit für den Host für die Synchronisierung der Gebietsschemas, die sie möglicherweise Mechanismen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7a518-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="7a518-129">Wenn ein Host lässt sich nicht auf das Gebietsschema von verwaltetem Code geändert werden, oder einen Mechanismus zur Synchronisierung von Gebietsschemas nicht implementiert, sollten sie diese Methode E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7a518-129">If a host does not allow the locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a518-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a518-130">Requirements</span></span>  
 <span data-ttu-id="7a518-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a518-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a518-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7a518-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7a518-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7a518-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a518-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a518-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a518-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a518-135">See also</span></span>
- [<span data-ttu-id="7a518-136">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a518-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7a518-137">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a518-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7a518-138">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a518-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7a518-139">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a518-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="7a518-140">SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="7a518-140">SetUILocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)
