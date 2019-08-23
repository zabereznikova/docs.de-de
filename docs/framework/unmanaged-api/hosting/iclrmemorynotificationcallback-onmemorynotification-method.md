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
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949706"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="c9ff6-102">ICLRMemoryNotificationCallback::OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="c9ff6-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="c9ff6-103">Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ff6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9ff6-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9ff6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9ff6-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="c9ff6-106">in Einer der [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) -Werte, der die Arbeitsspeicher Auslastung des Computers angibt.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9ff6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c9ff6-107">Return Value</span></span>  
  
|<span data-ttu-id="c9ff6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9ff6-108">HRESULT</span></span>|<span data-ttu-id="c9ff6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c9ff6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9ff6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9ff6-110">S_OK</span></span>|<span data-ttu-id="c9ff6-111">`OnMemoryNotification`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="c9ff6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9ff6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9ff6-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9ff6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9ff6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9ff6-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9ff6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9ff6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9ff6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9ff6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9ff6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9ff6-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9ff6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9ff6-120">E_FAIL</span></span>|<span data-ttu-id="c9ff6-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9ff6-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9ff6-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9ff6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9ff6-124">Remarks</span></span>  
 <span data-ttu-id="c9ff6-125">Die CLR registriert einen Rückruf bei `OnMemoryNotification` mithilfe eines Aufrufs der [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="c9ff6-126">Die Laufzeit verwendet die im Rückruf zurückgegebenen Informationen, um zusätzlichen Arbeitsspeicher freizugeben, wenn der Host meldet, dass die Arbeitsspeicher Ressourcen gering sind.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9ff6-127">Aufrufe von `OnMemoryNotification` niemals blockieren.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="c9ff6-128">Sie werden immer sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c9ff6-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ff6-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9ff6-129">Requirements</span></span>  
 <span data-ttu-id="c9ff6-130">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9ff6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9ff6-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9ff6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9ff6-132">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c9ff6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9ff6-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ff6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ff6-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9ff6-134">See also</span></span>

- [<span data-ttu-id="c9ff6-135">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9ff6-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="c9ff6-136">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="c9ff6-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="c9ff6-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9ff6-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
