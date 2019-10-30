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
ms.openlocfilehash: 79f24b3ccacd84037042a883d3a034bb7b4d200a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092090"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="e13a9-102">ICLRTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="e13a9-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="e13a9-103">Benachrichtigt den Common Language Runtime (CLR), dass der Host den Wert des Gebiets Schema Bezeichners (der der geografischen Kultur und Sprache zugeordnet ist) in der aktuell ausgeführten Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="e13a9-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e13a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e13a9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e13a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e13a9-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="e13a9-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e13a9-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e13a9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e13a9-107">Return Value</span></span>  
  
|<span data-ttu-id="e13a9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e13a9-108">HRESULT</span></span>|<span data-ttu-id="e13a9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e13a9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e13a9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e13a9-110">S_OK</span></span>|<span data-ttu-id="e13a9-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e13a9-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="e13a9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e13a9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e13a9-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e13a9-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e13a9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e13a9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e13a9-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e13a9-115">The call timed out.</span></span>|  
|<span data-ttu-id="e13a9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e13a9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e13a9-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e13a9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e13a9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e13a9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e13a9-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e13a9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e13a9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e13a9-120">E_FAIL</span></span>|<span data-ttu-id="e13a9-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e13a9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e13a9-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e13a9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e13a9-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e13a9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e13a9-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e13a9-124">Remarks</span></span>  
 <span data-ttu-id="e13a9-125">`SetLocale` bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e13a9-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e13a9-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e13a9-126">Requirements</span></span>  
 <span data-ttu-id="e13a9-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e13a9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e13a9-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e13a9-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e13a9-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e13a9-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e13a9-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e13a9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e13a9-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e13a9-131">See also</span></span>

- [<span data-ttu-id="e13a9-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e13a9-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e13a9-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e13a9-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e13a9-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e13a9-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e13a9-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e13a9-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
