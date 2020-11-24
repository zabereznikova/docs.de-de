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
ms.openlocfilehash: a5c2646d7c9dbf8a7aea4a7fb9bd0a6b8c1d5d66
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680547"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="9b1f6-102">IHostCrst::Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="9b1f6-102">IHostCrst::Enter Method</span></span>

<span data-ttu-id="9b1f6-103">Gibt den kritischen Abschnitt ein, der durch die aktuelle [IHostCrst](ihostcrst-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-103">Enters the critical section that is represented by the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b1f6-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b1f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b1f6-105">Parameters</span></span>  

 `option`  
 <span data-ttu-id="9b1f6-106">in Einer der [WAIT_OPTION](wait-option-enumeration.md) -Werte, der angibt, welche Aktion der Host ausführen soll, wenn der Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-106">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b1f6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b1f6-107">Return Value</span></span>  
  
|<span data-ttu-id="9b1f6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9b1f6-108">HRESULT</span></span>|<span data-ttu-id="9b1f6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b1f6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9b1f6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b1f6-110">S_OK</span></span>|<span data-ttu-id="9b1f6-111">`Enter` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="9b1f6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9b1f6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9b1f6-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9b1f6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9b1f6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9b1f6-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-115">The call timed out.</span></span>|  
|<span data-ttu-id="9b1f6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9b1f6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9b1f6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9b1f6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9b1f6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9b1f6-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9b1f6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9b1f6-120">E_FAIL</span></span>|<span data-ttu-id="9b1f6-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9b1f6-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9b1f6-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b1f6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b1f6-124">Remarks</span></span>  

 <span data-ttu-id="9b1f6-125">`Enter` spiegelt die Win32- `EnterCriticalSection` Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b1f6-126">Diese Methode wird erst zurückgegeben, wenn der kritische Abschnitt eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="9b1f6-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b1f6-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b1f6-127">Requirements</span></span>  

 <span data-ttu-id="9b1f6-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b1f6-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b1f6-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9b1f6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b1f6-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b1f6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b1f6-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b1f6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1f6-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b1f6-132">See also</span></span>

- [<span data-ttu-id="9b1f6-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b1f6-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="9b1f6-134">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b1f6-134">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="9b1f6-135">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b1f6-135">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
