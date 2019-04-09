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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088521"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="8088b-102">IHostMemoryManager::RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="8088b-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="8088b-103">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, um die common Language Runtime (CLR) Benachrichtigen des die aktuelle Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="8088b-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8088b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8088b-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8088b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8088b-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="8088b-106">[in] Einen Schnittstellenzeiger auf ein [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) -Instanz, die von der CLR implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8088b-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8088b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8088b-107">Return Value</span></span>  
  
|<span data-ttu-id="8088b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8088b-108">HRESULT</span></span>|<span data-ttu-id="8088b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8088b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8088b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8088b-110">S_OK</span></span>|`RegisterMemoryNotificationCallback` <span data-ttu-id="8088b-111">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8088b-111">returned successfully.</span></span>|  
|<span data-ttu-id="8088b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8088b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8088b-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="8088b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8088b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8088b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8088b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8088b-115">The call timed out.</span></span>|  
|<span data-ttu-id="8088b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8088b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8088b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8088b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8088b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8088b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8088b-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="8088b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8088b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8088b-120">E_FAIL</span></span>|<span data-ttu-id="8088b-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8088b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8088b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8088b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8088b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8088b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8088b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8088b-124">Remarks</span></span>  
 <span data-ttu-id="8088b-125">Da die `ICLRMemoryNotificationCallback` Schnittstelle definiert nur eine Methode ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), und da `pCallback` ist ein Zeiger auf ein `ICLRMemoryNotificationCallback` von der CLR bereitgestellte Instanz der die Registrierung ist effektiv für die Callback-Funktion selbst.</span><span class="sxs-lookup"><span data-stu-id="8088b-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="8088b-126">Der Host ruft `OnMemoryNotification` Bericht der speicherauslastung, statt die standardmäßige Win32 `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="8088b-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="8088b-127">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="8088b-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8088b-128">Aufrufe von `OnMemoryNotification` nie blockiert.</span><span class="sxs-lookup"><span data-stu-id="8088b-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="8088b-129">Sie zurückgegeben immer sofort.</span><span class="sxs-lookup"><span data-stu-id="8088b-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8088b-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8088b-130">Requirements</span></span>  
 <span data-ttu-id="8088b-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8088b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8088b-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8088b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8088b-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8088b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8088b-134">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8088b-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8088b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8088b-135">See also</span></span>

- [<span data-ttu-id="8088b-136">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8088b-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="8088b-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8088b-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
