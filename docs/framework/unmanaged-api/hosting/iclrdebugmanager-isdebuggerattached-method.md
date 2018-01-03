---
title: ICLRDebugManager::IsDebuggerAttached-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5abd854e224b19efa72100db0163d61b42b0b63c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="f71f0-102">ICLRDebugManager::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="f71f0-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="f71f0-103">Ruft einen Wert ab, der angibt, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="f71f0-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f71f0-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f71f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f71f0-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="f71f0-106">[out] `true` ist ein Debugger an den Prozess angefügt ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f71f0-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f71f0-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f71f0-107">Return Value</span></span>  
  
|<span data-ttu-id="f71f0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f71f0-108">HRESULT</span></span>|<span data-ttu-id="f71f0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f71f0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f71f0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f71f0-110">S_OK</span></span>|<span data-ttu-id="f71f0-111">`IsDebuggerAttached`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f71f0-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="f71f0-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="f71f0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f71f0-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f71f0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f71f0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f71f0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f71f0-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f71f0-115">The call timed out.</span></span>|  
|<span data-ttu-id="f71f0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f71f0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f71f0-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f71f0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f71f0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f71f0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f71f0-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f71f0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f71f0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f71f0-120">E_FAIL</span></span>|<span data-ttu-id="f71f0-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f71f0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f71f0-122">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f71f0-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f71f0-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f71f0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f71f0-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f71f0-124">Remarks</span></span>  
 <span data-ttu-id="f71f0-125">`IsDebuggerAttached`ermöglicht es dem Host zum Abfragen der CLR, um zu bestimmen, ob ein Debugger an den Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="f71f0-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f71f0-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f71f0-126">Requirements</span></span>  
 <span data-ttu-id="f71f0-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f71f0-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71f0-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f71f0-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f71f0-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f71f0-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f71f0-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71f0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71f0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f71f0-131">See Also</span></span>  
 [<span data-ttu-id="f71f0-132">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f71f0-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f71f0-133">ICLRDebugManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f71f0-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="f71f0-134">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f71f0-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
