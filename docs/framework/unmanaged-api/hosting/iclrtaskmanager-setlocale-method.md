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
ms.openlocfilehash: 8f316d91aab4c3862a0ad45b41539a4b80791ab9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762790"
---
# <a name="iclrtaskmanagersetlocale-method"></a><span data-ttu-id="8806b-102">ICLRTaskManager::SetLocale-Methode</span><span class="sxs-lookup"><span data-stu-id="8806b-102">ICLRTaskManager::SetLocale Method</span></span>
<span data-ttu-id="8806b-103">Benachrichtigt den Common Language Runtime (CLR), dass der Host den Wert des Gebiets Schema Bezeichners (der der geografischen Kultur und Sprache zugeordnet ist) in der aktuell ausgeführten Aufgabe geändert hat.</span><span class="sxs-lookup"><span data-stu-id="8806b-103">Notifies the common language runtime (CLR) that the host has modified the value of the locale identifier (which maps to the geographical culture and language) on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8806b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8806b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetLocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8806b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8806b-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="8806b-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="8806b-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8806b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8806b-107">Return Value</span></span>  
  
|<span data-ttu-id="8806b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8806b-108">HRESULT</span></span>|<span data-ttu-id="8806b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8806b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8806b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8806b-110">S_OK</span></span>|<span data-ttu-id="8806b-111">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8806b-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="8806b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8806b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8806b-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8806b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8806b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8806b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8806b-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8806b-115">The call timed out.</span></span>|  
|<span data-ttu-id="8806b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8806b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8806b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8806b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8806b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8806b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8806b-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8806b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8806b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8806b-120">E_FAIL</span></span>|<span data-ttu-id="8806b-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8806b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8806b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8806b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8806b-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8806b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8806b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8806b-124">Remarks</span></span>  
 <span data-ttu-id="8806b-125">`SetLocale`bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8806b-125">`SetLocale` gives the host an opportunity to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8806b-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8806b-126">Requirements</span></span>  
 <span data-ttu-id="8806b-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8806b-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8806b-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8806b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8806b-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8806b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8806b-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8806b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8806b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8806b-131">See also</span></span>

- [<span data-ttu-id="8806b-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8806b-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8806b-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8806b-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8806b-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8806b-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8806b-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8806b-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
