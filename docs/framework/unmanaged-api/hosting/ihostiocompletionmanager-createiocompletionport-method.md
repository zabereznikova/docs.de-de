---
title: IHostIoCompletionManager::CreateIoCompletionPort-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cf7978af4081b84a361e0a96a6c9da7180cb217
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194044"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="5a557-102">IHostIoCompletionManager::CreateIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="5a557-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="5a557-103">Fordert an, dass der Host eine neue e/a-Abschlussport zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a557-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a557-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a557-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a557-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a557-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="5a557-106">[out] Ein Zeiger auf ein Handle für den neu erstellten e/a-Abschlussport, oder 0 (null), wenn der Port nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="5a557-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a557-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5a557-107">Return Value</span></span>  
  
|<span data-ttu-id="5a557-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a557-108">HRESULT</span></span>|<span data-ttu-id="5a557-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a557-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a557-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a557-110">S_OK</span></span>|<span data-ttu-id="5a557-111">`CreateIoCompletionPort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5a557-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="5a557-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a557-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a557-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a557-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a557-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a557-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a557-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a557-115">The call timed out.</span></span>|  
|<span data-ttu-id="5a557-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a557-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a557-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5a557-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a557-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a557-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a557-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="5a557-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a557-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a557-120">E_FAIL</span></span>|<span data-ttu-id="5a557-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a557-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a557-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a557-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a557-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5a557-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5a557-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5a557-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5a557-125">Es war nicht genügend Arbeitsspeicher verfügbar, um die angeforderte Ressource zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="5a557-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a557-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a557-126">Remarks</span></span>  
 <span data-ttu-id="5a557-127">Die CLR ruft die `CreateIoCompletionPort` Methode, um anzufordern, dass der Host eine neue e/a-Abschlussport zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5a557-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="5a557-128">E/a-Vorgänge auf diesen Port durch einen Aufruf bindet die [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="5a557-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="5a557-129">Der Host meldet den Status zurück an die CLR durch Aufrufen von [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a557-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a557-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a557-130">Requirements</span></span>  
 <span data-ttu-id="5a557-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a557-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a557-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a557-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a557-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5a557-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a557-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a557-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a557-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a557-135">See also</span></span>

- [<span data-ttu-id="5a557-136">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a557-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="5a557-137">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a557-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
