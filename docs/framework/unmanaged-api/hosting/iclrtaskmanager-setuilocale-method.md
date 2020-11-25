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
ms.openlocfilehash: a426fca1b7ca4bfb9cbb30a221859f7c114db682
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732423"
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="f8699-102">ICLRTaskManager::SetUILocale-Methode</span><span class="sxs-lookup"><span data-stu-id="f8699-102">ICLRTaskManager::SetUILocale Method</span></span>

<span data-ttu-id="f8699-103">Benachrichtigt den Common Language Runtime (CLR), dass der Host das Gebiets Schema der Benutzeroberfläche (UI) für den aktuell ausgeführten Task geändert hat.</span><span class="sxs-lookup"><span data-stu-id="f8699-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8699-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8699-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8699-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8699-105">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="f8699-106">in Der Wert für den Gebiets Schema Bezeichner, der der neu zugewiesenen geografischen Kultur und Sprache für die Benutzeroberfläche zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f8699-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8699-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8699-107">Return Value</span></span>  
  
|<span data-ttu-id="f8699-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8699-108">HRESULT</span></span>|<span data-ttu-id="f8699-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8699-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8699-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8699-110">S_OK</span></span>|<span data-ttu-id="f8699-111">`SetUILocale` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f8699-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="f8699-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8699-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8699-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f8699-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8699-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8699-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8699-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f8699-115">The call timed out.</span></span>|  
|<span data-ttu-id="f8699-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8699-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8699-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f8699-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8699-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8699-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8699-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f8699-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8699-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8699-120">E_FAIL</span></span>|<span data-ttu-id="f8699-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f8699-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8699-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="f8699-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8699-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f8699-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8699-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f8699-124">Remarks</span></span>  

 <span data-ttu-id="f8699-125">`SetUILocale` bietet dem Host die Möglichkeit, alle Mechanismen auszuführen, die möglicherweise für die Synchronisierung von Gebiets Schemas vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f8699-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8699-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8699-126">Requirements</span></span>  

 <span data-ttu-id="f8699-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8699-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8699-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f8699-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8699-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f8699-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8699-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8699-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8699-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8699-131">See also</span></span>

- [<span data-ttu-id="f8699-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8699-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f8699-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8699-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f8699-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8699-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f8699-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8699-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
