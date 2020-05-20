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
ms.openlocfilehash: d88abcc523eca06c8ec50cac2d2984b26099174a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703788"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="02fdd-102">ICLRMemoryNotificationCallback::OnMemoryNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="02fdd-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="02fdd-103">Benachrichtigt den Common Language Runtime (CLR) über die Arbeitsspeicher Auslastung auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="02fdd-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02fdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="02fdd-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02fdd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="02fdd-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="02fdd-106">in Einer der [EMemoryAvailable](ememoryavailable-enumeration.md) -Werte, der die Arbeitsspeicher Auslastung des Computers angibt.</span><span class="sxs-lookup"><span data-stu-id="02fdd-106">[in] One of the [EMemoryAvailable](ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02fdd-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02fdd-107">Return Value</span></span>  
  
|<span data-ttu-id="02fdd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02fdd-108">HRESULT</span></span>|<span data-ttu-id="02fdd-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="02fdd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02fdd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="02fdd-110">S_OK</span></span>|<span data-ttu-id="02fdd-111">`OnMemoryNotification`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02fdd-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="02fdd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02fdd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02fdd-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="02fdd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="02fdd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02fdd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02fdd-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="02fdd-115">The call timed out.</span></span>|  
|<span data-ttu-id="02fdd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02fdd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02fdd-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="02fdd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02fdd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02fdd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02fdd-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="02fdd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02fdd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02fdd-120">E_FAIL</span></span>|<span data-ttu-id="02fdd-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="02fdd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02fdd-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="02fdd-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02fdd-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="02fdd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02fdd-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02fdd-124">Remarks</span></span>  
 <span data-ttu-id="02fdd-125">Die CLR registriert einen Rückruf bei `OnMemoryNotification` mithilfe eines Aufrufs der [IHostMemoryManager:: RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="02fdd-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="02fdd-126">Die Laufzeit verwendet die im Rückruf zurückgegebenen Informationen, um zusätzlichen Arbeitsspeicher freizugeben, wenn der Host meldet, dass die Arbeitsspeicher Ressourcen gering sind.</span><span class="sxs-lookup"><span data-stu-id="02fdd-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02fdd-127">Aufrufe von `OnMemoryNotification` niemals blockieren.</span><span class="sxs-lookup"><span data-stu-id="02fdd-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="02fdd-128">Sie werden immer sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="02fdd-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02fdd-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02fdd-129">Requirements</span></span>  
 <span data-ttu-id="02fdd-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02fdd-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02fdd-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="02fdd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02fdd-132">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="02fdd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02fdd-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02fdd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02fdd-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02fdd-134">See also</span></span>

- [<span data-ttu-id="02fdd-135">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02fdd-135">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="02fdd-136">RegisterMemoryNotificationCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="02fdd-136">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="02fdd-137">ICLRMemoryNotificationCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="02fdd-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
