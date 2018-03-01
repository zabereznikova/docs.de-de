---
title: ICLRRuntimeHost::ExecuteInAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8c540c9618655e6df30ad253e0c4cccdf6624e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="99bb3-102">ICLRRuntimeHost::ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="99bb3-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="99bb3-103">Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99bb3-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99bb3-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99bb3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99bb3-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="99bb3-106">[in] Die numerische ID des dem <xref:System.AppDomain> in dem die angegebene Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="99bb3-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="99bb3-107">[in] Ein Zeiger auf die Funktion, die innerhalb des angegebenen ausgeführt <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="99bb3-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="99bb3-108">[in] Ein Zeiger auf nicht transparenten vom Aufrufer reservierten Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="99bb3-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="99bb3-109">Dieser Parameter wird von der common Language Runtime (CLR) an den Domänenrückruf übergeben.</span><span class="sxs-lookup"><span data-stu-id="99bb3-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="99bb3-110">Es ist nicht zur Laufzeit verwaltete Heap-Speicher. die Zuordnung und die Lebensdauer dieses Arbeitsspeichers werden vom Aufrufer gesteuert.</span><span class="sxs-lookup"><span data-stu-id="99bb3-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99bb3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99bb3-111">Return Value</span></span>  
  
|<span data-ttu-id="99bb3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99bb3-112">HRESULT</span></span>|<span data-ttu-id="99bb3-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99bb3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99bb3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="99bb3-114">S_OK</span></span>|<span data-ttu-id="99bb3-115">`ExecuteInAppDomain`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="99bb3-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="99bb3-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="99bb3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99bb3-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="99bb3-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99bb3-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99bb3-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99bb3-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="99bb3-119">The call timed out.</span></span>|  
|<span data-ttu-id="99bb3-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99bb3-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99bb3-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="99bb3-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99bb3-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99bb3-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99bb3-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="99bb3-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99bb3-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99bb3-124">E_FAIL</span></span>|<span data-ttu-id="99bb3-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="99bb3-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99bb3-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="99bb3-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99bb3-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="99bb3-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99bb3-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99bb3-128">Remarks</span></span>  
 <span data-ttu-id="99bb3-129">`ExecuteInAppDomain`ermöglicht es dem Host, um die Steuerung zu in welchem <xref:System.AppDomain> die angegebene verwaltete Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="99bb3-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="99bb3-130">Sie erhalten eine Anwendungsdomäne-Bezeichner, der auf den Wert der entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft durch den Aufruf [[GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="99bb3-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99bb3-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99bb3-131">Requirements</span></span>  
 <span data-ttu-id="99bb3-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99bb3-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99bb3-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99bb3-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99bb3-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99bb3-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99bb3-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99bb3-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99bb3-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99bb3-136">See Also</span></span>  
 [<span data-ttu-id="99bb3-137">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99bb3-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
