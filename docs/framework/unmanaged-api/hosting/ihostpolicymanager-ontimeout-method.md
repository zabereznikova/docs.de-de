---
title: IHostPolicyManager::OnTimeout-Methode
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
ms.openlocfilehash: e3f2dc7ff9beaf417184f3d09db76e611982118a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690667"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="c4dcd-102">IHostPolicyManager::OnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="c4dcd-102">IHostPolicyManager::OnTimeout Method</span></span>

<span data-ttu-id="c4dcd-103">Benachrichtigt den Host, dass der Common Language Runtime (CLR) im Begriff ist, die durch einen Aufrufe der Methode [ICLRPolicyManager:: abtationontimeout](iclrpolicymanager-setactionontimeout-method.md) angegebene Aktion als Antwort auf ein Timeout auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4dcd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4dcd-104">Syntax</span></span>  
  
```cpp  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4dcd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4dcd-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="c4dcd-106">in Einer der [eclroperations](eclroperation-enumeration.md) -Werte, der die Art des Vorgangs angibt, bei dem ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="c4dcd-107">in Einer der [EPolicyAction](epolicyaction-enumeration.md) -Werte, der die Aktion angibt, die von der CLR als Reaktion auf das Timeout ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4dcd-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4dcd-108">Return Value</span></span>  
  
|<span data-ttu-id="c4dcd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4dcd-109">HRESULT</span></span>|<span data-ttu-id="c4dcd-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4dcd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4dcd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4dcd-111">S_OK</span></span>|<span data-ttu-id="c4dcd-112">`OnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="c4dcd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4dcd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4dcd-114">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4dcd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4dcd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4dcd-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-116">The call timed out.</span></span>|  
|<span data-ttu-id="c4dcd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4dcd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4dcd-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4dcd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4dcd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4dcd-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4dcd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4dcd-121">E_FAIL</span></span>|<span data-ttu-id="c4dcd-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4dcd-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4dcd-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c4dcd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4dcd-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4dcd-125">Requirements</span></span>  

 <span data-ttu-id="c4dcd-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4dcd-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4dcd-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c4dcd-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4dcd-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4dcd-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4dcd-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4dcd-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4dcd-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4dcd-130">See also</span></span>

- [<span data-ttu-id="c4dcd-131">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c4dcd-131">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="c4dcd-132">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c4dcd-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="c4dcd-133">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4dcd-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="c4dcd-134">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4dcd-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
