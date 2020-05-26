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
ms.openlocfilehash: e6aa8cb814e509d310c2f5b5524e0fd6727fc43f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804283"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="e0906-102">IHostPolicyManager::OnDefaultAction-Methode</span><span class="sxs-lookup"><span data-stu-id="e0906-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="e0906-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) im Begriff ist, die Standardaktion zu übernehmen, die durch einen Aufrufen der [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) -Methode als Reaktion auf einen Thread Abbruch oder Entladen festgelegt wurde <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="e0906-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0906-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0906-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0906-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0906-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="e0906-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der die Art des Ereignisses angibt, auf das die CLR antwortet.</span><span class="sxs-lookup"><span data-stu-id="e0906-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="e0906-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die von der CLR als Reaktion auf das Ereignis ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0906-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0906-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e0906-108">Return Value</span></span>  
  
|<span data-ttu-id="e0906-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0906-109">HRESULT</span></span>|<span data-ttu-id="e0906-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e0906-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0906-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0906-111">S_OK</span></span>|<span data-ttu-id="e0906-112">`OnDefaultAction`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e0906-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="e0906-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0906-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0906-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e0906-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="e0906-115">erfolgrei</span><span class="sxs-lookup"><span data-stu-id="e0906-115">successfully</span></span>|  
|<span data-ttu-id="e0906-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0906-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0906-117">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e0906-117">The call timed out.</span></span>|  
|<span data-ttu-id="e0906-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0906-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0906-119">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e0906-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0906-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0906-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0906-121">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e0906-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0906-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0906-122">E_FAIL</span></span>|<span data-ttu-id="e0906-123">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e0906-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0906-124">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="e0906-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0906-125">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e0906-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0906-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0906-126">Requirements</span></span>  
 <span data-ttu-id="e0906-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0906-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0906-128">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e0906-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0906-129">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e0906-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0906-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0906-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0906-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0906-131">See also</span></span>

- [<span data-ttu-id="e0906-132">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e0906-132">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="e0906-133">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e0906-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="e0906-134">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0906-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="e0906-135">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0906-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
