---
title: IHostMemoryManager::RegisterMemoryNotificationCallback-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 4400fab27ed82e540230ce4196844285e8e37d16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128639"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="b6c62-102">IHostMemoryManager::RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="b6c62-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="b6c62-103">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um den Common Language Runtime (CLR) der aktuellen Arbeitsspeicher Auslastung auf dem Computer zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="b6c62-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6c62-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6c62-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="b6c62-106">in Ein Schnittstellen Zeiger auf eine [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) -Instanz, die von der CLR implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b6c62-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6c62-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b6c62-107">Return Value</span></span>  
  
|<span data-ttu-id="b6c62-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6c62-108">HRESULT</span></span>|<span data-ttu-id="b6c62-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6c62-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6c62-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6c62-110">S_OK</span></span>|<span data-ttu-id="b6c62-111">`RegisterMemoryNotificationCallback` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b6c62-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="b6c62-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6c62-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6c62-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b6c62-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6c62-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6c62-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6c62-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b6c62-115">The call timed out.</span></span>|  
|<span data-ttu-id="b6c62-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6c62-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6c62-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b6c62-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6c62-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6c62-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6c62-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b6c62-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6c62-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6c62-120">E_FAIL</span></span>|<span data-ttu-id="b6c62-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b6c62-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6c62-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b6c62-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6c62-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b6c62-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6c62-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6c62-124">Remarks</span></span>  
 <span data-ttu-id="b6c62-125">Da die `ICLRMemoryNotificationCallback`-Schnittstelle nur eine Methode definiert ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) und da `pCallback` ein Zeiger auf eine `ICLRMemoryNotificationCallback` Instanz ist, die von der CLR bereitgestellt wird, ist die Registrierung effektiv für den Rückruf. Funktion selbst.</span><span class="sxs-lookup"><span data-stu-id="b6c62-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="b6c62-126">Der Host ruft `OnMemoryNotification` auf, um Speichermangel Bedingungen zu melden, anstatt die standardmäßige Win32-`CreateMemoryResourceNotification` Funktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b6c62-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="b6c62-127">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="b6c62-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6c62-128">Aufrufe von `OnMemoryNotification` nie blockieren.</span><span class="sxs-lookup"><span data-stu-id="b6c62-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="b6c62-129">Sie werden immer sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b6c62-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c62-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6c62-130">Requirements</span></span>  
 <span data-ttu-id="b6c62-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c62-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c62-132">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b6c62-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6c62-133">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b6c62-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6c62-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c62-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c62-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6c62-135">See also</span></span>

- [<span data-ttu-id="b6c62-136">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6c62-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="b6c62-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b6c62-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
