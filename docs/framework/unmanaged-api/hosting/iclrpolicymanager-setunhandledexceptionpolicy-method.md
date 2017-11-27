---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59ff5cfd93d8077388694ee2e155133a88319c47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="5d518-102">ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="5d518-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="5d518-103">Gibt das Verhalten der common Language Runtime (CLR) an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="5d518-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d518-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d518-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d518-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d518-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="5d518-106">[in] Eines der [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) Werte, der angibt, ob das Verhalten von CLR oder vom Host festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5d518-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d518-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d518-107">Return Value</span></span>  
  
|<span data-ttu-id="5d518-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d518-108">HRESULT</span></span>|<span data-ttu-id="5d518-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d518-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d518-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d518-110">S_OK</span></span>|<span data-ttu-id="5d518-111">`SetUnhandledExceptionPolicy`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d518-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="5d518-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="5d518-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d518-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5d518-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d518-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d518-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d518-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5d518-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d518-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d518-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d518-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="5d518-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d518-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d518-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d518-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="5d518-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d518-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d518-120">E_FAIL</span></span>|<span data-ttu-id="5d518-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="5d518-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d518-122">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="5d518-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d518-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5d518-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d518-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d518-124">Remarks</span></span>  
 <span data-ttu-id="5d518-125">Standardmäßig die CLR ist der letzte Handler für alle nicht behandelten Ausnahmen und sein Standardverhalten wird an den Prozess.</span><span class="sxs-lookup"><span data-stu-id="5d518-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="5d518-126">Der Host kann dieses Verhalten ändern, durch Festlegen der `policy` eHostDeterminedPolicy Wert.</span><span class="sxs-lookup"><span data-stu-id="5d518-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="5d518-127">Mit diesem Wert kann den Host einen eigenen Standardverhalten zu implementieren, wie in früheren Versionen der CLR.</span><span class="sxs-lookup"><span data-stu-id="5d518-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d518-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d518-128">Requirements</span></span>  
 <span data-ttu-id="5d518-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d518-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d518-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d518-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d518-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5d518-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d518-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d518-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d518-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d518-133">See Also</span></span>  
 [<span data-ttu-id="5d518-134">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5d518-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [<span data-ttu-id="5d518-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d518-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="5d518-136">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d518-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="5d518-137">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d518-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
