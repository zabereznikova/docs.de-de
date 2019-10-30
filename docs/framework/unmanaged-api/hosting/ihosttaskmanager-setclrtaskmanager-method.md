---
title: IHostTaskManager::SetCLRTaskManager-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141237"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="dc226-102">IHostTaskManager::SetCLRTaskManager-Methode</span><span class="sxs-lookup"><span data-stu-id="dc226-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="dc226-103">Stellt dem Host einen Schnittstellen Zeiger auf eine [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) -Instanz bereit, die vom Common Language Runtime (CLR) implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="dc226-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc226-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc226-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc226-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc226-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="dc226-106">in Ein Zeiger auf eine `ICLRTaskManager`-Instanz, die vom Common Language Runtime implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="dc226-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc226-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dc226-107">Return Value</span></span>  
  
|<span data-ttu-id="dc226-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dc226-108">HRESULT</span></span>|<span data-ttu-id="dc226-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc226-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dc226-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dc226-110">S_OK</span></span>|<span data-ttu-id="dc226-111">`SetCLRTaskManager` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dc226-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="dc226-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dc226-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dc226-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="dc226-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dc226-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dc226-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dc226-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="dc226-115">The call timed out.</span></span>|  
|<span data-ttu-id="dc226-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dc226-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dc226-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="dc226-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dc226-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dc226-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dc226-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="dc226-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dc226-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dc226-120">E_FAIL</span></span>|<span data-ttu-id="dc226-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="dc226-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dc226-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc226-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dc226-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="dc226-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc226-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc226-124">Remarks</span></span>  
 <span data-ttu-id="dc226-125">Die Laufzeit ruft `SetCLRTaskManager` auf, um dem Host einen Schnittstellen Zeiger auf eine `ICLRTaskManager` Instanz bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dc226-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc226-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc226-126">Requirements</span></span>  
 <span data-ttu-id="dc226-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc226-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc226-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dc226-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc226-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dc226-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc226-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc226-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc226-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc226-131">See also</span></span>

- [<span data-ttu-id="dc226-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc226-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="dc226-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc226-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dc226-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc226-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dc226-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc226-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
