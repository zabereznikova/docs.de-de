---
title: ICLRTaskManager::SetUILocale-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ef939f915062368d74a0c48bdaee47cbec7b56f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491463"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="1eb19-102">ICLRTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="1eb19-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="1eb19-103">Benachrichtigt die common Language Runtime (CLR), dass der Host, das Gebietsschema der Benutzeroberfläche (UI) oder die Kultur geändert hat, in der aktuell ausgeführten Aufgabe an.</span><span class="sxs-lookup"><span data-stu-id="1eb19-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eb19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eb19-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eb19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1eb19-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="1eb19-106">[in] Die Gebietsschema-ID-Wert, der neu zugewiesenen geografischen-Kultur und Sprache für die Benutzeroberfläche ist.</span><span class="sxs-lookup"><span data-stu-id="1eb19-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1eb19-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1eb19-107">Return Value</span></span>  
  
|<span data-ttu-id="1eb19-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1eb19-108">HRESULT</span></span>|<span data-ttu-id="1eb19-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1eb19-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1eb19-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1eb19-110">S_OK</span></span>|<span data-ttu-id="1eb19-111">`SetUILocale` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1eb19-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="1eb19-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1eb19-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1eb19-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1eb19-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1eb19-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1eb19-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1eb19-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1eb19-115">The call timed out.</span></span>|  
|<span data-ttu-id="1eb19-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1eb19-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1eb19-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1eb19-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1eb19-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1eb19-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1eb19-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1eb19-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1eb19-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1eb19-120">E_FAIL</span></span>|<span data-ttu-id="1eb19-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1eb19-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1eb19-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1eb19-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1eb19-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1eb19-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1eb19-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1eb19-124">Remarks</span></span>  
 <span data-ttu-id="1eb19-125">`SetUILocale` bietet die Möglichkeit für den Host möglicherweise die Mechanismen für die Synchronisierung von Gebietsschemas auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1eb19-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eb19-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1eb19-126">Requirements</span></span>  
 <span data-ttu-id="1eb19-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eb19-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eb19-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1eb19-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1eb19-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1eb19-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1eb19-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eb19-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb19-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb19-131">See also</span></span>
- [<span data-ttu-id="1eb19-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1eb19-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1eb19-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1eb19-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1eb19-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1eb19-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1eb19-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1eb19-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
