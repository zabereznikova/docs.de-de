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
ms.openlocfilehash: f4b40a595bbdea4dd390a42af6a0d4b1a5efa2f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130495"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="48922-102">IHostCrst::TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="48922-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="48922-103">Versucht, den kritischen Abschnitt einzugeben, der durch die aktuelle [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="48922-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48922-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48922-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48922-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48922-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="48922-106">in Einer der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Werte, der angibt, welche Aktion der Host ausführen soll, wenn der Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="48922-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="48922-107">[out] `true`, wenn der kritische Abschnitt eingegeben werden kann. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="48922-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48922-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48922-108">Return Value</span></span>  
  
|<span data-ttu-id="48922-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48922-109">HRESULT</span></span>|<span data-ttu-id="48922-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48922-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48922-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48922-111">S_OK</span></span>|<span data-ttu-id="48922-112">`TryEnter` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48922-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="48922-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48922-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48922-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="48922-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48922-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48922-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48922-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="48922-116">The call timed out.</span></span>|  
|<span data-ttu-id="48922-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48922-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48922-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="48922-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48922-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48922-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48922-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="48922-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48922-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48922-121">E_FAIL</span></span>|<span data-ttu-id="48922-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48922-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48922-123">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="48922-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48922-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="48922-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48922-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48922-125">Remarks</span></span>  
 <span data-ttu-id="48922-126">`TryEnter` wird sofort zurückgegeben und gibt an, ob der aufrufenden Thread den kritischen Abschnitt eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="48922-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="48922-127">Diese Methode spiegelt die Wind32 `TryEnterCriticalSection`-Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="48922-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48922-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48922-128">Requirements</span></span>  
 <span data-ttu-id="48922-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48922-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48922-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="48922-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48922-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48922-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48922-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48922-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48922-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48922-133">See also</span></span>

- [<span data-ttu-id="48922-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48922-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="48922-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48922-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="48922-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48922-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
