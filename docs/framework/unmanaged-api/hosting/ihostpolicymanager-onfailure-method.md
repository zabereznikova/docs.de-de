---
title: IHostPolicyManager::OnFailure-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: efa7b9d49ea9807af2164bb6ee54422dd72b14e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730421"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="2a239-102">IHostPolicyManager::OnFailure-Methode</span><span class="sxs-lookup"><span data-stu-id="2a239-102">IHostPolicyManager::OnFailure Method</span></span>

<span data-ttu-id="2a239-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) die Aktion durchführen soll, die durch einen Aufrufe der [ICLRPolicyManager:: abtationonfailure](iclrpolicymanager-setactiononfailure-method.md) -Methode als Reaktion auf einen Ressourcen Zuordnungs-oder-Fehler bei der Wiederherstellung angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2a239-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a239-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a239-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a239-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a239-105">Parameters</span></span>  

 `failure`  
 <span data-ttu-id="2a239-106">in Einer der [EClrFailure](eclrfailure-enumeration.md) -Werte, der die Art des Fehlers angibt, auf den die CLR antwortet.</span><span class="sxs-lookup"><span data-stu-id="2a239-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="2a239-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die von der CLR als Reaktion auf ausgeführt wird `failure` .</span><span class="sxs-lookup"><span data-stu-id="2a239-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a239-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a239-108">Return Value</span></span>  
  
|<span data-ttu-id="2a239-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a239-109">HRESULT</span></span>|<span data-ttu-id="2a239-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2a239-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a239-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a239-111">S_OK</span></span>|<span data-ttu-id="2a239-112">`OnFailure` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a239-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="2a239-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a239-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a239-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="2a239-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a239-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a239-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a239-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="2a239-116">The call timed out.</span></span>|  
|<span data-ttu-id="2a239-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a239-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a239-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2a239-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a239-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a239-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a239-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="2a239-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a239-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a239-121">E_FAIL</span></span>|<span data-ttu-id="2a239-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2a239-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a239-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="2a239-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a239-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2a239-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a239-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a239-125">Requirements</span></span>  

 <span data-ttu-id="2a239-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a239-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a239-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2a239-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a239-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2a239-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a239-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a239-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a239-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2a239-130">See also</span></span>

- [<span data-ttu-id="2a239-131">EClrFailure-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2a239-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="2a239-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2a239-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="2a239-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a239-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="2a239-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a239-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
