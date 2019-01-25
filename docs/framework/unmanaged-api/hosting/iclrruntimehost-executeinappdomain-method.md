---
title: ICLRRuntimeHost::ExecuteInAppDomain-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5a1ae284b4f2474cb824ee9dbff2eb82c5a0ead
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568789"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="c4f02-102">ICLRRuntimeHost::ExecuteInAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="c4f02-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="c4f02-103">Gibt an, die <xref:System.AppDomain> in dem den angegebenen verwalteten Code ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4f02-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4f02-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4f02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4f02-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="c4f02-106">[in] Die numerische ID des dem <xref:System.AppDomain> in dem die angegebene Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c4f02-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="c4f02-107">[in] Ein Zeiger auf die Funktion, die innerhalb des angegebenen ausführen <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="c4f02-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="c4f02-108">[in] Ein Zeiger auf nicht transparente, vom Aufrufer reservierten Speicher.</span><span class="sxs-lookup"><span data-stu-id="c4f02-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="c4f02-109">Dieser Parameter wird von der common Language Runtime (CLR) an den Domänenrückruf übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4f02-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="c4f02-110">Es ist nicht die Common Language Runtime verwalteten Heapspeicher. die Zuordnung und die Lebensdauer dieses Arbeitsspeichers werden von der aufrufenden Funktion gesteuert.</span><span class="sxs-lookup"><span data-stu-id="c4f02-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4f02-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4f02-111">Return Value</span></span>  
  
|<span data-ttu-id="c4f02-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4f02-112">HRESULT</span></span>|<span data-ttu-id="c4f02-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4f02-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4f02-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4f02-114">S_OK</span></span>|<span data-ttu-id="c4f02-115">`ExecuteInAppDomain` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4f02-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="c4f02-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4f02-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4f02-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c4f02-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4f02-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4f02-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4f02-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4f02-119">The call timed out.</span></span>|  
|<span data-ttu-id="c4f02-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4f02-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4f02-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c4f02-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4f02-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4f02-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4f02-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c4f02-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4f02-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4f02-124">E_FAIL</span></span>|<span data-ttu-id="c4f02-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4f02-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4f02-126">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4f02-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4f02-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c4f02-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4f02-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4f02-128">Remarks</span></span>  
 <span data-ttu-id="c4f02-129">`ExecuteInAppDomain` ermöglicht dem Host, die Kontrolle über den verwalteten <xref:System.AppDomain> in die angegebene Methode ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c4f02-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="c4f02-130">Sie erhalten den Wert des Bezeichners für eine Anwendungsdomäne, der dem Wert entspricht der <xref:System.AppDomain.Id%2A> Eigenschaft, durch den Aufruf [GetCurrentAppDomainId-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="c4f02-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f02-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4f02-131">Requirements</span></span>  
 <span data-ttu-id="c4f02-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4f02-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4f02-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4f02-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4f02-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4f02-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4f02-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4f02-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f02-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4f02-136">See also</span></span>
- [<span data-ttu-id="c4f02-137">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4f02-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
