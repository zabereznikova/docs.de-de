---
title: ICLRIoCompletionManager::OnComplete-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="e54e0-102">ICLRIoCompletionManager::OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="e54e0-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="e54e0-103">Benachrichtigt die common Language Runtime (CLR) über den Status einer e/a-Anforderung, die erstellt wurde, mithilfe eines Aufrufs an die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e54e0-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e54e0-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e54e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e54e0-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="e54e0-106">[in] Ein HRESULT-Wert, der den Status des Bindungsvorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="e54e0-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="e54e0-107">S_OK gibt an, dass der Vorgang erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e54e0-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="e54e0-108">HOST_E_INTERRUPTED gibt an, dass der Aufruf verfrüht beendet.</span><span class="sxs-lookup"><span data-stu-id="e54e0-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="e54e0-109">E_FAIL gibt an, dass ein Unbekannter, nicht mehr wiederherstellbar, schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e54e0-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="e54e0-110">[in] Die Anzahl der Bytes während der Verarbeitung der e/a-Anforderung übertragen.</span><span class="sxs-lookup"><span data-stu-id="e54e0-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="e54e0-111">[in] Ein Zeiger auf die `OVERLAPPED` -Struktur, die für den Aufruf übergeben wurde die `IHostIoCompletionManager::Bind` Methode.</span><span class="sxs-lookup"><span data-stu-id="e54e0-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e54e0-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e54e0-112">Return Value</span></span>  
  
|<span data-ttu-id="e54e0-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e54e0-113">HRESULT</span></span>|<span data-ttu-id="e54e0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e54e0-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e54e0-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e54e0-115">S_OK</span></span>|<span data-ttu-id="e54e0-116">`OnComplete`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e54e0-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="e54e0-117">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="e54e0-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e54e0-118">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e54e0-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e54e0-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e54e0-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e54e0-120">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e54e0-120">The call timed out.</span></span>|  
|<span data-ttu-id="e54e0-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e54e0-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e54e0-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e54e0-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e54e0-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e54e0-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e54e0-124">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e54e0-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e54e0-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e54e0-125">E_FAIL</span></span>|<span data-ttu-id="e54e0-126">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e54e0-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e54e0-127">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="e54e0-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e54e0-128">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e54e0-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e54e0-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e54e0-129">Remarks</span></span>  
 <span data-ttu-id="e54e0-130">Wenn der Host eine e/a-Abschluss-Abstraktion implementiert, macht die CLR e/a-Anforderungen über den Host mithilfe der Methoden der [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e54e0-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="e54e0-131">Der Host ruft dann die `OnComplete` Methode, um die Laufzeit über das Ergebnis des solche Anforderungen darüber zu informieren.</span><span class="sxs-lookup"><span data-stu-id="e54e0-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54e0-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e54e0-132">Requirements</span></span>  
 <span data-ttu-id="e54e0-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e54e0-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e54e0-134">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e54e0-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e54e0-135">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e54e0-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e54e0-136">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e54e0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54e0-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e54e0-137">See Also</span></span>  
 [<span data-ttu-id="e54e0-138">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e54e0-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="e54e0-139">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e54e0-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="e54e0-140">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e54e0-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
