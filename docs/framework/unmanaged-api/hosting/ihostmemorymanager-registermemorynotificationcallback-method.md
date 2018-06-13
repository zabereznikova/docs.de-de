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
ms.openlocfilehash: d68790cdb671efdd0761ceef59196e8646654d5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439600"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="53491-102">IHostMemoryManager::RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="53491-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="53491-103">Registriert einen Zeiger auf eine Rückruffunktion, die der Host aufruft, damit die common Language Runtime (CLR) benachrichtigt werden, von der aktuellen Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="53491-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53491-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53491-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53491-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53491-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="53491-106">[in] Einen Schnittstellenzeiger auf eine [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) Instanz, die von der CLR implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="53491-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53491-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="53491-107">Return Value</span></span>  
  
|<span data-ttu-id="53491-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53491-108">HRESULT</span></span>|<span data-ttu-id="53491-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53491-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53491-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53491-110">S_OK</span></span>|<span data-ttu-id="53491-111">`RegisterMemoryNotificationCallback` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53491-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="53491-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="53491-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53491-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="53491-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53491-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53491-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53491-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="53491-115">The call timed out.</span></span>|  
|<span data-ttu-id="53491-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53491-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53491-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="53491-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53491-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53491-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53491-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="53491-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53491-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53491-120">E_FAIL</span></span>|<span data-ttu-id="53491-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="53491-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53491-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="53491-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53491-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="53491-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53491-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53491-124">Remarks</span></span>  
 <span data-ttu-id="53491-125">Da die `ICLRMemoryNotificationCallback` Schnittstelle definiert nur eine Methode ([ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), und da `pCallback` ist ein Zeiger auf eine `ICLRMemoryNotificationCallback` Instanz, die von der CLR bereitgestellte der Registrierung ist für die Rückruffunktion selbst wirksam.</span><span class="sxs-lookup"><span data-stu-id="53491-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="53491-126">Der Host ruft `OnMemoryNotification` Bericht speicherauslastung, statt der standardmäßigen Win32 `CreateMemoryResourceNotification` Funktion.</span><span class="sxs-lookup"><span data-stu-id="53491-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="53491-127">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="53491-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53491-128">Aufrufe von `OnMemoryNotification` nie blockiert.</span><span class="sxs-lookup"><span data-stu-id="53491-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="53491-129">Diese zurückgegeben immer sofort.</span><span class="sxs-lookup"><span data-stu-id="53491-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53491-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53491-130">Requirements</span></span>  
 <span data-ttu-id="53491-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53491-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53491-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53491-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53491-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="53491-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53491-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53491-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53491-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53491-135">See Also</span></span>  
 [<span data-ttu-id="53491-136">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53491-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="53491-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53491-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
