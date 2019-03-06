---
title: IHostIoCompletionManager::SetCLRIoCompletionManager-Methode
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a190041cacb635f1ad6703a634923e0bb9ddb3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484263"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="9848b-102">IHostIoCompletionManager::SetCLRIoCompletionManager-Methode</span><span class="sxs-lookup"><span data-stu-id="9848b-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="9848b-103">Bietet einen Schnittstellenzeiger auf den Host die [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) -Instanz, von der common Language Runtime (CLR) implementiert.</span><span class="sxs-lookup"><span data-stu-id="9848b-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9848b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9848b-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9848b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9848b-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="9848b-106">[in] Einen Schnittstellenzeiger auf ein `ICLRIoCompletionManager` -Instanz, von der CLR bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9848b-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9848b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9848b-107">Return Value</span></span>  
  
|<span data-ttu-id="9848b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9848b-108">HRESULT</span></span>|<span data-ttu-id="9848b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9848b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9848b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9848b-110">S_OK</span></span>|<span data-ttu-id="9848b-111">`SetCLRIoCompletionManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9848b-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="9848b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9848b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9848b-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9848b-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9848b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9848b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9848b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9848b-115">The call timed out.</span></span>|  
|<span data-ttu-id="9848b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9848b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9848b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9848b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9848b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9848b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9848b-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9848b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9848b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9848b-120">E_FAIL</span></span>|<span data-ttu-id="9848b-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9848b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9848b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9848b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9848b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9848b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9848b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9848b-124">Remarks</span></span>  
 <span data-ttu-id="9848b-125">Nachdem der CLR aufgerufen hat `SetCLRIoCompletionManager`, muss der Host Aufrufen [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) auf die CLR darüber zu benachrichtigen, wenn eine e/a-Anforderung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="9848b-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9848b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9848b-126">Requirements</span></span>  
 <span data-ttu-id="9848b-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9848b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9848b-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9848b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9848b-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9848b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9848b-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9848b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9848b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9848b-131">See also</span></span>
- [<span data-ttu-id="9848b-132">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9848b-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9848b-133">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9848b-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
