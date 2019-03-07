---
title: ICLRMemoryNotificationCallback::OnMemoryNotification-Methode
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d395c7eed27893e407b1944523a2f879b56c795d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489305"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="0ae89-102">ICLRMemoryNotificationCallback::OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="0ae89-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="0ae89-103">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="0ae89-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ae89-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ae89-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="0ae89-106">[in] Eines der [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) -Werte, der angibt, die Auslastung des Arbeitsspeichers des Computers sind aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ae89-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ae89-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ae89-107">Return Value</span></span>  
  
|<span data-ttu-id="0ae89-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ae89-108">HRESULT</span></span>|<span data-ttu-id="0ae89-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ae89-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ae89-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ae89-110">S_OK</span></span>|<span data-ttu-id="0ae89-111">`OnMemoryNotification` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ae89-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="0ae89-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ae89-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ae89-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0ae89-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ae89-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ae89-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ae89-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ae89-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ae89-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ae89-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ae89-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0ae89-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ae89-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ae89-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ae89-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0ae89-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ae89-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ae89-120">E_FAIL</span></span>|<span data-ttu-id="0ae89-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ae89-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ae89-122">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ae89-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ae89-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0ae89-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ae89-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ae89-124">Remarks</span></span>  
 <span data-ttu-id="0ae89-125">Die CLR registriert einen Rückruf an `OnMemoryNotification` mithilfe eines Aufrufs an die [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0ae89-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="0ae89-126">Die Runtime verwendet die Informationen in der Rückruf zurückgegeben, der zusätzliche Speicherplatz freizugeben, sobald der Host, dass der Speicher meldet, die Ressourcen niedrig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0ae89-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ae89-127">Aufrufe von `OnMemoryNotification` nie blockiert.</span><span class="sxs-lookup"><span data-stu-id="0ae89-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="0ae89-128">Sie zurückgegeben immer sofort.</span><span class="sxs-lookup"><span data-stu-id="0ae89-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae89-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ae89-129">Requirements</span></span>  
 <span data-ttu-id="0ae89-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae89-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae89-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ae89-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ae89-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ae89-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ae89-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae89-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae89-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ae89-134">See also</span></span>
- [<span data-ttu-id="0ae89-135">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ae89-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="0ae89-136">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="0ae89-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="0ae89-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ae89-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
