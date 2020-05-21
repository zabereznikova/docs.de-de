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
ms.openlocfilehash: e6ab7c7af1cf9f30f6708c4e970db619ca071343
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762772"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="ad750-102">ICLRTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="ad750-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="ad750-103">Benachrichtigt den Common Language Runtime (CLR), dass der Host das Gebiets Schema der Benutzeroberfläche (UI) für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="ad750-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad750-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad750-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad750-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad750-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ad750-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache für die Benutzeroberfläche zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ad750-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad750-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad750-107">Return Value</span></span>  
  
|<span data-ttu-id="ad750-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad750-108">HRESULT</span></span>|<span data-ttu-id="ad750-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ad750-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad750-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad750-110">S_OK</span></span>|<span data-ttu-id="ad750-111">`SetUILocale`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad750-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="ad750-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad750-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad750-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ad750-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad750-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad750-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad750-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ad750-115">The call timed out.</span></span>|  
|<span data-ttu-id="ad750-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad750-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad750-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ad750-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad750-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad750-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad750-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ad750-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad750-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad750-120">E_FAIL</span></span>|<span data-ttu-id="ad750-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ad750-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad750-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="ad750-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad750-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ad750-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad750-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad750-124">Remarks</span></span>  
 <span data-ttu-id="ad750-125">`SetUILocale`bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ad750-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad750-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ad750-126">Requirements</span></span>  
 <span data-ttu-id="ad750-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad750-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad750-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ad750-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad750-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ad750-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad750-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad750-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad750-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad750-131">See also</span></span>

- [<span data-ttu-id="ad750-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad750-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="ad750-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad750-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="ad750-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad750-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="ad750-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad750-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
