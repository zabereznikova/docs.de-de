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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87dfbe85d279aa191253857887c1d9b5b5f8c7cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951741"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="7ae81-102">IHostMemoryManager::RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="7ae81-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="7ae81-103">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die common Language Runtime (CLR) Benachrichtigen des die aktuelle Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="7ae81-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae81-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ae81-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae81-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ae81-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="7ae81-106">[in] Einen Schnittstellenzeiger auf ein [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) -Instanz, die von der CLR implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="7ae81-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ae81-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ae81-107">Return Value</span></span>  
  
|<span data-ttu-id="7ae81-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ae81-108">HRESULT</span></span>|<span data-ttu-id="7ae81-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ae81-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ae81-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ae81-110">S_OK</span></span>|<span data-ttu-id="7ae81-111">`RegisterMemoryNotificationCallback` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7ae81-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="7ae81-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ae81-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ae81-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ae81-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ae81-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ae81-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ae81-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7ae81-115">The call timed out.</span></span>|  
|<span data-ttu-id="7ae81-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ae81-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ae81-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7ae81-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ae81-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ae81-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ae81-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7ae81-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ae81-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ae81-120">E_FAIL</span></span>|<span data-ttu-id="7ae81-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7ae81-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ae81-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ae81-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ae81-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7ae81-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ae81-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ae81-124">Remarks</span></span>  
 <span data-ttu-id="7ae81-125">Da die `ICLRMemoryNotificationCallback` Schnittstelle definiert nur eine Methode ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), und da `pCallback` ist ein Zeiger auf ein `ICLRMemoryNotificationCallback` von der CLR bereitgestellte Instanz der die Registrierung ist effektiv für die Callback-Funktion selbst.</span><span class="sxs-lookup"><span data-stu-id="7ae81-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="7ae81-126">Der Host ruft `OnMemoryNotification` Bericht der speicherauslastung, statt die standardmäßige Win32 `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="7ae81-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="7ae81-127">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="7ae81-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ae81-128">Aufrufe von `OnMemoryNotification` nie blockiert.</span><span class="sxs-lookup"><span data-stu-id="7ae81-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="7ae81-129">Sie zurückgegeben immer sofort.</span><span class="sxs-lookup"><span data-stu-id="7ae81-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae81-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ae81-130">Requirements</span></span>  
 <span data-ttu-id="7ae81-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae81-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae81-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ae81-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ae81-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7ae81-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ae81-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae81-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae81-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ae81-135">See also</span></span>

- [<span data-ttu-id="7ae81-136">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ae81-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="7ae81-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ae81-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
