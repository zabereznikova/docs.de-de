---
title: IHostIoCompletionManager::CloseIoCompletionPort-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CloseIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 32a7c8b1c1c61eddb18ade1e77af5ea973fbaadc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59107561"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="0069a-102">IHostIoCompletionManager::CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="0069a-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="0069a-103">Fordert an, dass der Host einen Port schließen, die durch einen früheren Aufruf von geöffnet wurde [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span><span class="sxs-lookup"><span data-stu-id="0069a-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0069a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0069a-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0069a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0069a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="0069a-106">[in] Das Handle des Ports zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0069a-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0069a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0069a-107">Return Value</span></span>  
  
|<span data-ttu-id="0069a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0069a-108">HRESULT</span></span>|<span data-ttu-id="0069a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0069a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0069a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0069a-110">S_OK</span></span>|<span data-ttu-id="0069a-111">`CloseIoCompletionPort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0069a-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="0069a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0069a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0069a-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0069a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0069a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0069a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0069a-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0069a-115">The call timed out.</span></span>|  
|<span data-ttu-id="0069a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0069a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0069a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0069a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0069a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0069a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0069a-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0069a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0069a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0069a-120">E_FAIL</span></span>|<span data-ttu-id="0069a-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0069a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0069a-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0069a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0069a-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0069a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0069a-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0069a-124">E_INVALIDARG</span></span>|<span data-ttu-id="0069a-125">Es wurde ein ungültiger Porthandle übergeben.</span><span class="sxs-lookup"><span data-stu-id="0069a-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0069a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0069a-126">Remarks</span></span>  
 <span data-ttu-id="0069a-127">`hPort` muss ein Handle für einen Port, der durch einen früheren Aufruf von erstelltes `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="0069a-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0069a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0069a-128">Requirements</span></span>  
 <span data-ttu-id="0069a-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0069a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0069a-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0069a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0069a-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0069a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0069a-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0069a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0069a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0069a-133">See also</span></span>

- [<span data-ttu-id="0069a-134">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0069a-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="0069a-135">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0069a-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
