---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7b6a4be94e526e7b464b336d221eff936808635a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120570"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="0ebaf-102">ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="0ebaf-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="0ebaf-103">Gibt das Verhalten der Common Language Runtime (CLR) an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ebaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ebaf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ebaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ebaf-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="0ebaf-106">in Einer der [eclrunlenker dexception](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) -Werte, der angibt, ob das Verhalten durch die CLR oder den Host festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ebaf-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0ebaf-107">Return Value</span></span>  
  
|<span data-ttu-id="0ebaf-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ebaf-108">HRESULT</span></span>|<span data-ttu-id="0ebaf-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ebaf-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ebaf-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ebaf-110">S_OK</span></span>|<span data-ttu-id="0ebaf-111">`SetUnhandledExceptionPolicy` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="0ebaf-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ebaf-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ebaf-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ebaf-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ebaf-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ebaf-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-115">The call timed out.</span></span>|  
|<span data-ttu-id="0ebaf-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ebaf-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ebaf-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ebaf-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ebaf-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ebaf-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ebaf-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ebaf-120">E_FAIL</span></span>|<span data-ttu-id="0ebaf-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ebaf-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ebaf-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ebaf-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ebaf-124">Remarks</span></span>  
 <span data-ttu-id="0ebaf-125">Standardmäßig ist die CLR der letzte Handler für alle nicht behandelten Ausnahmen, und Ihr Standardverhalten besteht darin, den Prozess zu beenden.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="0ebaf-126">Der Host kann dieses Verhalten ändern, indem der `policy` Wert auf eHostDeterminedPolicy festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="0ebaf-127">Dieser Wert ermöglicht es dem Host, sein eigenes Standardverhalten zu implementieren, wie bei früheren Versionen der CLR.</span><span class="sxs-lookup"><span data-stu-id="0ebaf-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ebaf-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0ebaf-128">Requirements</span></span>  
 <span data-ttu-id="0ebaf-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ebaf-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ebaf-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="0ebaf-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ebaf-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ebaf-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ebaf-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ebaf-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ebaf-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ebaf-133">See also</span></span>

- [<span data-ttu-id="0ebaf-134">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0ebaf-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="0ebaf-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ebaf-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="0ebaf-136">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ebaf-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="0ebaf-137">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ebaf-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
