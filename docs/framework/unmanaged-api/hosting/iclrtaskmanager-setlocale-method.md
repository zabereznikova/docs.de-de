---
title: ICLRTaskManager::SetLocale-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetLocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetLocale
helpviewer_keywords:
- SetLocale method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::SetLocale method [.NET Framework hosting]
ms.assetid: ed16bb7f-4206-43a8-b9e9-c5737b69e3af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ab6b13c6b7dba34f5ea82d05f483b36bf96aab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437325"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="2986d-102">ICLRTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="2986d-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="2986d-103">Benachrichtigt der common Language Runtime (CLR), dass der Host den Wert der Gebietsschema-ID (die die geografischen Kultur und Sprache zugeordnet) auf die gerade ausgeführte Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="2986d-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2986d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2986d-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2986d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2986d-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="2986d-106">[in] Der Wert der Gebietsschema-Bezeichner, der die neu zugewiesene geografische Kultur und Sprache zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2986d-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2986d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2986d-107">Return Value</span></span>  
  
|<span data-ttu-id="2986d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2986d-108">HRESULT</span></span>|<span data-ttu-id="2986d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2986d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2986d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2986d-110">S_OK</span></span>|<span data-ttu-id="2986d-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2986d-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="2986d-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="2986d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2986d-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2986d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2986d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2986d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2986d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2986d-115">The call timed out.</span></span>|  
|<span data-ttu-id="2986d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2986d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2986d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2986d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2986d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2986d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2986d-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="2986d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2986d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2986d-120">E_FAIL</span></span>|<span data-ttu-id="2986d-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2986d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2986d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="2986d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2986d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2986d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2986d-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2986d-124">Remarks</span></span>  
 <span data-ttu-id="2986d-125">`SetLocale` ermöglicht dem Host ein Mechanismen, die sie möglicherweise für die Synchronisierung von Gebietsschemas auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2986d-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2986d-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2986d-126">Requirements</span></span>  
 <span data-ttu-id="2986d-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2986d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2986d-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2986d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2986d-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2986d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2986d-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2986d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2986d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2986d-131">See Also</span></span>  
 [<span data-ttu-id="2986d-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2986d-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="2986d-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2986d-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="2986d-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2986d-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="2986d-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2986d-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
