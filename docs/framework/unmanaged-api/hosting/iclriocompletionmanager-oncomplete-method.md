---
title: ICLRIoCompletionManager::OnComplete-Methode
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager.OnComplete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type:
- apiref
ms.openlocfilehash: b44a71137e39130bb0fe4c303fdff62c76d38cbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141010"
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="983cf-102">ICLRIoCompletionManager::OnComplete-Methode</span><span class="sxs-lookup"><span data-stu-id="983cf-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="983cf-103">Benachrichtigt den Common Language Runtime (CLR) über den Status einer e/a-Anforderung, die mithilfe eines Aufrufes der [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) -Methode durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="983cf-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="983cf-104">Syntax</span></span>  
  
```cpp  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="983cf-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="983cf-106">in Ein HRESULT-Wert, der den Status des Bindungs Vorgangs angibt.</span><span class="sxs-lookup"><span data-stu-id="983cf-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
- <span data-ttu-id="983cf-107">S_OK gibt an, dass der Vorgang erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="983cf-107">S_OK indicates that the operation completed successfully.</span></span>  
  
- <span data-ttu-id="983cf-108">HOST_E_INTERRUPTED gibt an, dass der-Rückruf vor dem Abschluss beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="983cf-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
- <span data-ttu-id="983cf-109">E_FAIL gibt an, dass ein unbekannter, nicht BEHEB barer, schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="983cf-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="983cf-110">in Die Anzahl von Bytes, die während der Verarbeitung der e/a-Anforderung übertragen wurden.</span><span class="sxs-lookup"><span data-stu-id="983cf-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="983cf-111">in Ein Zeiger auf die `OVERLAPPED`-Struktur, die an den-Befehl der `IHostIoCompletionManager::Bind`-Methode übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="983cf-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="983cf-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="983cf-112">Return Value</span></span>  
  
|<span data-ttu-id="983cf-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="983cf-113">HRESULT</span></span>|<span data-ttu-id="983cf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="983cf-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="983cf-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="983cf-115">S_OK</span></span>|<span data-ttu-id="983cf-116">`OnComplete` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="983cf-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="983cf-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="983cf-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="983cf-118">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="983cf-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="983cf-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="983cf-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="983cf-120">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="983cf-120">The call timed out.</span></span>|  
|<span data-ttu-id="983cf-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="983cf-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="983cf-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="983cf-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="983cf-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="983cf-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="983cf-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="983cf-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="983cf-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="983cf-125">E_FAIL</span></span>|<span data-ttu-id="983cf-126">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="983cf-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="983cf-127">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="983cf-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="983cf-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="983cf-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="983cf-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="983cf-129">Remarks</span></span>  
 <span data-ttu-id="983cf-130">Wenn der Host eine e/a-Abschluss Abstraktion implementiert, stellt die CLR e/a-Anforderungen über den Host mithilfe von [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)-Methoden her.</span><span class="sxs-lookup"><span data-stu-id="983cf-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="983cf-131">Der Host ruft dann die `OnComplete`-Methode auf, um die Laufzeit über das Ergebnis solcher Anforderungen zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="983cf-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983cf-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="983cf-132">Requirements</span></span>  
 <span data-ttu-id="983cf-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="983cf-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983cf-134">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="983cf-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="983cf-135">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="983cf-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="983cf-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983cf-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983cf-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="983cf-137">See also</span></span>

- [<span data-ttu-id="983cf-138">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="983cf-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="983cf-139">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="983cf-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="983cf-140">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="983cf-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
