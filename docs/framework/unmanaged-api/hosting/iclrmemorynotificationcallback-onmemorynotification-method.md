---
title: ICLRMemoryNotificationCallback::OnMemoryNotification-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 651dcd6380702a392d2dd06cf899ea567b004ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="ac6af-102">ICLRMemoryNotificationCallback::OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="ac6af-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="ac6af-103">Benachrichtigt die common Language Runtime (CLR) von der Auslastung des Arbeitsspeichers auf dem Computer an.</span><span class="sxs-lookup"><span data-stu-id="ac6af-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac6af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac6af-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac6af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac6af-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="ac6af-106">[in] Eines der [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) Werte, der angibt, die Auslastung des Arbeitsspeichers des Computers wird derzeit auftritt.</span><span class="sxs-lookup"><span data-stu-id="ac6af-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac6af-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac6af-107">Return Value</span></span>  
  
|<span data-ttu-id="ac6af-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac6af-108">HRESULT</span></span>|<span data-ttu-id="ac6af-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac6af-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac6af-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac6af-110">S_OK</span></span>|<span data-ttu-id="ac6af-111">`OnMemoryNotification`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ac6af-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="ac6af-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ac6af-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac6af-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ac6af-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac6af-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac6af-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac6af-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ac6af-115">The call timed out.</span></span>|  
|<span data-ttu-id="ac6af-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac6af-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac6af-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ac6af-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac6af-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac6af-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac6af-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ac6af-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac6af-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac6af-120">E_FAIL</span></span>|<span data-ttu-id="ac6af-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ac6af-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac6af-122">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ac6af-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac6af-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ac6af-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac6af-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac6af-124">Remarks</span></span>  
 <span data-ttu-id="ac6af-125">Die CLR registriert einen Rückruf zur `OnMemoryNotification` mithilfe eines Aufrufs an die [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="ac6af-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="ac6af-126">Die Laufzeit verwendet die Informationen in den Rückruf zurückgegeben, zusätzlichen Arbeitsspeicher frei, wenn der Host, dass der Arbeitsspeicher meldet, niedrige Ressourcen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ac6af-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac6af-127">Aufrufe von `OnMemoryNotification` nie blockiert.</span><span class="sxs-lookup"><span data-stu-id="ac6af-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="ac6af-128">Diese zurückgegeben immer sofort.</span><span class="sxs-lookup"><span data-stu-id="ac6af-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac6af-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac6af-129">Requirements</span></span>  
 <span data-ttu-id="ac6af-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac6af-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac6af-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac6af-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac6af-132">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ac6af-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac6af-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac6af-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6af-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac6af-134">See Also</span></span>  
 [<span data-ttu-id="ac6af-135">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac6af-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="ac6af-136">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="ac6af-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="ac6af-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ac6af-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
