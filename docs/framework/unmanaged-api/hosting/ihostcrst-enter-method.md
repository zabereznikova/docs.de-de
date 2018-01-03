---
title: IHostCrst::Enter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.Enter
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 390f30c85dac494451af1ff82328c913dd9438ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="7ee3b-102">IHostCrst::Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="7ee3b-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="7ee3b-103">Wechselt in den kritischen Abschnitt die von der aktuellen dargestellte [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ee3b-104">Syntax</span></span>  
  
```  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ee3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ee3b-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="7ee3b-106">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der angibt, welche Aktion der Host ausführen soll, wenn der Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ee3b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ee3b-107">Return Value</span></span>  
  
|<span data-ttu-id="7ee3b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ee3b-108">HRESULT</span></span>|<span data-ttu-id="7ee3b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ee3b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ee3b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ee3b-110">S_OK</span></span>|<span data-ttu-id="7ee3b-111">`Enter`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="7ee3b-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="7ee3b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ee3b-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ee3b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ee3b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ee3b-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-115">The call timed out.</span></span>|  
|<span data-ttu-id="7ee3b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ee3b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ee3b-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ee3b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ee3b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ee3b-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ee3b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ee3b-120">E_FAIL</span></span>|<span data-ttu-id="7ee3b-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ee3b-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ee3b-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ee3b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ee3b-124">Remarks</span></span>  
 <span data-ttu-id="7ee3b-125">`Enter`spiegelt die Win32- `EnterCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ee3b-126">Diese Methode gibt keinen zurück, bis der kritische Abschnitt eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee3b-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ee3b-127">Requirements</span></span>  
 <span data-ttu-id="7ee3b-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ee3b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee3b-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ee3b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ee3b-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7ee3b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ee3b-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee3b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee3b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ee3b-132">See Also</span></span>  
 [<span data-ttu-id="7ee3b-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ee3b-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="7ee3b-134">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ee3b-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="7ee3b-135">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ee3b-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
