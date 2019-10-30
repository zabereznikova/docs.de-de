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
ms.openlocfilehash: 254254af705f93793b030882e0ac79d0372ca55f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133892"
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="d6876-102">IHostIoCompletionManager::CloseIoCompletionPort-Methode</span><span class="sxs-lookup"><span data-stu-id="d6876-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="d6876-103">Fordert an, dass der Host einen Port schließt, der durch einen früheren Aufrufen von " [feateiocompletionport](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)" geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="d6876-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6876-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6876-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6876-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6876-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="d6876-106">in Das Handle des zu schließenden Ports.</span><span class="sxs-lookup"><span data-stu-id="d6876-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6876-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6876-107">Return Value</span></span>  
  
|<span data-ttu-id="d6876-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6876-108">HRESULT</span></span>|<span data-ttu-id="d6876-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6876-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6876-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6876-110">S_OK</span></span>|<span data-ttu-id="d6876-111">`CloseIoCompletionPort` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6876-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="d6876-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d6876-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d6876-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d6876-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d6876-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d6876-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d6876-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d6876-115">The call timed out.</span></span>|  
|<span data-ttu-id="d6876-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d6876-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d6876-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d6876-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d6876-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d6876-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d6876-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d6876-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d6876-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d6876-120">E_FAIL</span></span>|<span data-ttu-id="d6876-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d6876-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d6876-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6876-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d6876-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d6876-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d6876-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d6876-124">E_INVALIDARG</span></span>|<span data-ttu-id="d6876-125">Es wurde ein ungültiges Port handle übermittelt.</span><span class="sxs-lookup"><span data-stu-id="d6876-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6876-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6876-126">Remarks</span></span>  
 <span data-ttu-id="d6876-127">`hPort` muss ein Handle für einen Port sein, der von einem früheren `CreateIoCompletionPort`-Auflistungstyp erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6876-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6876-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6876-128">Requirements</span></span>  
 <span data-ttu-id="d6876-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6876-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6876-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d6876-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6876-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d6876-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6876-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6876-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6876-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6876-133">See also</span></span>

- [<span data-ttu-id="d6876-134">ICLRIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6876-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d6876-135">IHostIoCompletionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d6876-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
