---
title: IHostPolicyManager::OnDefaultAction-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: a22f16c14514b90ce888fafc0ea554bd9f90cb11
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684082"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="4a843-102">IHostPolicyManager::OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="4a843-102">IHostPolicyManager::OnDefaultAction Method</span></span>

<span data-ttu-id="4a843-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) im Begriff ist, die Standardaktion zu übernehmen, die durch einen Aufrufen der [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) -Methode als Reaktion auf einen Thread Abbruch oder Entladen festgelegt wurde <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="4a843-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a843-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a843-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a843-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a843-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="4a843-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der die Art des Ereignisses angibt, auf das die CLR antwortet.</span><span class="sxs-lookup"><span data-stu-id="4a843-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="4a843-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die von der CLR als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4a843-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a843-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4a843-108">Return Value</span></span>  
  
|<span data-ttu-id="4a843-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a843-109">HRESULT</span></span>|<span data-ttu-id="4a843-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4a843-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a843-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a843-111">S_OK</span></span>|<span data-ttu-id="4a843-112">`OnDefaultAction` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a843-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="4a843-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a843-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a843-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="4a843-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="4a843-115">erfolgrei</span><span class="sxs-lookup"><span data-stu-id="4a843-115">successfully</span></span>|  
|<span data-ttu-id="4a843-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a843-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a843-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="4a843-117">The call timed out.</span></span>|  
|<span data-ttu-id="4a843-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a843-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a843-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4a843-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a843-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a843-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a843-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="4a843-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a843-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a843-122">E_FAIL</span></span>|<span data-ttu-id="4a843-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4a843-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a843-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="4a843-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a843-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4a843-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a843-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a843-126">Requirements</span></span>  

 <span data-ttu-id="4a843-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a843-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a843-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4a843-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a843-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4a843-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a843-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a843-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a843-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a843-131">See also</span></span>

- [<span data-ttu-id="4a843-132">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4a843-132">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="4a843-133">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4a843-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="4a843-134">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a843-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="4a843-135">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a843-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
