---
title: IHostCrst::TryEnter-Methode
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9c463b055f5bd7d965e2df9428ee7c4a1e612dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675233"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="9a591-102">IHostCrst::TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="9a591-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="9a591-103">Versucht, Sie geben den kritischen Abschnitt, der vom aktuellen [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="9a591-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a591-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a591-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a591-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a591-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="9a591-106">[in] Eines der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) Werte, der angibt, welche Aktion, die der Host ausführen soll, wenn der Vorgang blockiert.</span><span class="sxs-lookup"><span data-stu-id="9a591-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="9a591-107">[out] `true` Wenn der kritische Abschnitt, andernfalls werden kann `false`.</span><span class="sxs-lookup"><span data-stu-id="9a591-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a591-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a591-108">Return Value</span></span>  
  
|<span data-ttu-id="9a591-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a591-109">HRESULT</span></span>|<span data-ttu-id="9a591-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a591-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a591-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a591-111">S_OK</span></span>|<span data-ttu-id="9a591-112">`TryEnter` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9a591-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="9a591-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9a591-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9a591-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9a591-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9a591-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9a591-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9a591-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9a591-116">The call timed out.</span></span>|  
|<span data-ttu-id="9a591-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9a591-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9a591-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9a591-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9a591-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9a591-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9a591-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9a591-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9a591-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a591-121">E_FAIL</span></span>|<span data-ttu-id="9a591-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9a591-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a591-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a591-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9a591-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9a591-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a591-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a591-125">Remarks</span></span>  
 <span data-ttu-id="9a591-126">`TryEnter` kehrt sofort zurück und gibt an, ob der aufrufende Thread den kritischen Abschnitt hat.</span><span class="sxs-lookup"><span data-stu-id="9a591-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="9a591-127">Diese Methode spiegelt die Win32 `TryEnterCriticalSection` Funktion.</span><span class="sxs-lookup"><span data-stu-id="9a591-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a591-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a591-128">Requirements</span></span>  
 <span data-ttu-id="9a591-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a591-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a591-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9a591-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a591-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9a591-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a591-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a591-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a591-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a591-133">See also</span></span>
- [<span data-ttu-id="9a591-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a591-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9a591-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a591-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="9a591-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a591-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
