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
ms.openlocfilehash: ae097320ad7cd6e7c840122bf3f315812e9b2acd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199205"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="50aa3-102">ICLRTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="50aa3-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="50aa3-103">Benachrichtigt, dass der Host den Wert des Gebietsschemabezeichners (die von der geografischen Kultur und Sprache zugeordnet wird) für die derzeit ausgeführte Aufgabe geändert hat der common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="50aa3-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50aa3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50aa3-104">Syntax</span></span>  
  
```  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50aa3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50aa3-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="50aa3-106">[in] Die Gebietsschema-ID-Wert, der die neu zugewiesene geografischen Kultur und Sprache zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="50aa3-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50aa3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50aa3-107">Return Value</span></span>  
  
|<span data-ttu-id="50aa3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50aa3-108">HRESULT</span></span>|<span data-ttu-id="50aa3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50aa3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="50aa3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="50aa3-110">S_OK</span></span>|<span data-ttu-id="50aa3-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50aa3-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="50aa3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="50aa3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="50aa3-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="50aa3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="50aa3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="50aa3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="50aa3-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50aa3-115">The call timed out.</span></span>|  
|<span data-ttu-id="50aa3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="50aa3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="50aa3-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="50aa3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="50aa3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="50aa3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="50aa3-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="50aa3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="50aa3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="50aa3-120">E_FAIL</span></span>|<span data-ttu-id="50aa3-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="50aa3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="50aa3-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50aa3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="50aa3-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="50aa3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50aa3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50aa3-124">Remarks</span></span>  
 `SetLocale` <span data-ttu-id="50aa3-125">ermöglicht dem Host ein, die sie möglicherweise Mechanismen für die Synchronisierung von Gebietsschemas auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50aa3-125">gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50aa3-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50aa3-126">Requirements</span></span>  
 <span data-ttu-id="50aa3-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50aa3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50aa3-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="50aa3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50aa3-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50aa3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="50aa3-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="50aa3-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50aa3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50aa3-131">See also</span></span>

- [<span data-ttu-id="50aa3-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50aa3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="50aa3-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50aa3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="50aa3-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50aa3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="50aa3-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50aa3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
