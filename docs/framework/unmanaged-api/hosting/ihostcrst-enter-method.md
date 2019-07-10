---
title: IHostCrst::Enter-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.Enter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::Enter
helpviewer_keywords:
- Enter method [.NET Framework hosting]
- IHostCrst::Enter method [.NET Framework hosting]
ms.assetid: 100dd7eb-7053-4295-9bb3-32ba47f6ec79
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a54135a0daff3f207d1365d2c27335440f7f1fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763778"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="36599-102">IHostCrst::Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="36599-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="36599-103">Gibt den kritischen Abschnitt, die von der aktuellen dargestellt wird [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="36599-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36599-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36599-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36599-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36599-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="36599-106">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der angibt, welche Aktion, die der Host ausführen soll, wenn der Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="36599-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36599-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36599-107">Return Value</span></span>  
  
|<span data-ttu-id="36599-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36599-108">HRESULT</span></span>|<span data-ttu-id="36599-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36599-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36599-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="36599-110">S_OK</span></span>|<span data-ttu-id="36599-111">`Enter` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="36599-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="36599-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36599-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36599-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="36599-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36599-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36599-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36599-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="36599-115">The call timed out.</span></span>|  
|<span data-ttu-id="36599-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36599-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36599-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="36599-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36599-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36599-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36599-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="36599-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36599-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36599-120">E_FAIL</span></span>|<span data-ttu-id="36599-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="36599-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36599-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36599-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36599-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="36599-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36599-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36599-124">Remarks</span></span>  
 <span data-ttu-id="36599-125">`Enter` spiegelt die Win32- `EnterCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="36599-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36599-126">Diese Methode gibt keine zurück, bis der kritische Abschnitt eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="36599-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36599-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36599-127">Requirements</span></span>  
 <span data-ttu-id="36599-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36599-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36599-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36599-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36599-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="36599-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36599-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36599-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36599-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36599-132">See also</span></span>

- [<span data-ttu-id="36599-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36599-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="36599-134">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36599-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="36599-135">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36599-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
