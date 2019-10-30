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
ms.openlocfilehash: 757fb996b268892818a54a3f80a54edfd89c7630
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124428"
---
# <a name="ihostcrstenter-method"></a><span data-ttu-id="8e700-102">IHostCrst::Enter-Methode</span><span class="sxs-lookup"><span data-stu-id="8e700-102">IHostCrst::Enter Method</span></span>
<span data-ttu-id="8e700-103">Gibt den kritischen Abschnitt ein, der durch die aktuelle [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) -Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8e700-103">Enters the critical section that is represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e700-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e700-104">Syntax</span></span>  
  
```cpp  
HRESULT Enter (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e700-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e700-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="8e700-106">in Einer der [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) -Werte, der angibt, welche Aktion der Host ausführen soll, wenn der Vorgang blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="8e700-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e700-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8e700-107">Return Value</span></span>  
  
|<span data-ttu-id="8e700-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e700-108">HRESULT</span></span>|<span data-ttu-id="8e700-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e700-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e700-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e700-110">S_OK</span></span>|<span data-ttu-id="8e700-111">`Enter` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e700-111">`Enter` returned successfully.</span></span>|  
|<span data-ttu-id="8e700-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e700-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e700-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8e700-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e700-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e700-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e700-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8e700-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e700-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e700-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e700-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8e700-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e700-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e700-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e700-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8e700-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e700-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e700-120">E_FAIL</span></span>|<span data-ttu-id="8e700-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8e700-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e700-122">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e700-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e700-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8e700-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e700-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e700-124">Remarks</span></span>  
 <span data-ttu-id="8e700-125">`Enter` spiegelt die Win32-`EnterCriticalSection`-Funktion wider.</span><span class="sxs-lookup"><span data-stu-id="8e700-125">`Enter` mirrors the Win32 `EnterCriticalSection` function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e700-126">Diese Methode wird erst zurückgegeben, wenn der kritische Abschnitt eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="8e700-126">This method does not return until the critical section is entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e700-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e700-127">Requirements</span></span>  
 <span data-ttu-id="8e700-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e700-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e700-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8e700-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e700-130">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8e700-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e700-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e700-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e700-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e700-132">See also</span></span>

- [<span data-ttu-id="8e700-133">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e700-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="8e700-134">IHostCrst-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e700-134">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="8e700-135">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e700-135">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
