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
ms.openlocfilehash: 02f36068f12bf0a40e5f0ac477803abfb84c72a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729533"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="b252c-102">IHostCrst::TryEnter-Methode</span><span class="sxs-lookup"><span data-stu-id="b252c-102">IHostCrst::TryEnter Method</span></span>

<span data-ttu-id="b252c-103">Versucht, den kritischen Abschnitt einzugeben, der durch die aktuelle [IHostCrst](ihostcrst-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b252c-103">Attempts to enter the critical section represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b252c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b252c-104">Syntax</span></span>  
  
```cpp  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b252c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b252c-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="b252c-106">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der angibt, welche Aktion der Host ausführen soll, wenn der Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="b252c-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="b252c-107">[out] `true` , wenn der kritische Abschnitt eingegeben werden kann. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="b252c-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b252c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b252c-108">Return Value</span></span>  
  
|<span data-ttu-id="b252c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b252c-109">HRESULT</span></span>|<span data-ttu-id="b252c-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b252c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b252c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b252c-111">S_OK</span></span>|<span data-ttu-id="b252c-112">`TryEnter` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b252c-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="b252c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b252c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b252c-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b252c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b252c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b252c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b252c-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b252c-116">The call timed out.</span></span>|  
|<span data-ttu-id="b252c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b252c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b252c-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b252c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b252c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b252c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b252c-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b252c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b252c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b252c-121">E_FAIL</span></span>|<span data-ttu-id="b252c-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b252c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b252c-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="b252c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b252c-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b252c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b252c-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b252c-125">Remarks</span></span>  

 <span data-ttu-id="b252c-126">`TryEnter` gibt sofort zurück und gibt an, ob der aufrufenden Thread den kritischen Abschnitt eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="b252c-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="b252c-127">Diese Methode spiegelt die Wind32- `TryEnterCriticalSection` Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="b252c-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b252c-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b252c-128">Requirements</span></span>  

 <span data-ttu-id="b252c-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b252c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b252c-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b252c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b252c-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b252c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b252c-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b252c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b252c-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b252c-133">See also</span></span>

- [<span data-ttu-id="b252c-134">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b252c-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="b252c-135">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b252c-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="b252c-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b252c-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
