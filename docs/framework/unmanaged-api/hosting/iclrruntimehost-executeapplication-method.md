---
title: ICLRRuntimeHost::ExecuteApplication-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteApplication
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3b43365ad208dae5b28b31cf494de37ca670d791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="7abd9-102">ICLRRuntimeHost::ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="7abd9-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="7abd9-103">In Szenarien für die ClickOnce-Manifest-basiertes verwendet, an die Anwendung in einer neuen Domäne aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="7abd9-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="7abd9-104">Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="7abd9-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abd9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7abd9-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7abd9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7abd9-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="7abd9-107">[in] Der vollständige Name der Anwendung, entsprechend der Definition für <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="7abd9-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="7abd9-108">[in] Die Anzahl der Zeichenfolgen die `ppwzManifestPaths` Array.</span><span class="sxs-lookup"><span data-stu-id="7abd9-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="7abd9-109">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="7abd9-109">[in] Optional.</span></span> <span data-ttu-id="7abd9-110">Ein Zeichenfolgenarray, das manifest Pfade für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="7abd9-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="7abd9-111">[in] Die Anzahl der Zeichenfolgen die `ppwzActivationData` Array.</span><span class="sxs-lookup"><span data-stu-id="7abd9-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="7abd9-112">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="7abd9-112">[in] Optional.</span></span> <span data-ttu-id="7abd9-113">Ein Zeichenfolgenarray, das die Anwendung Aktivierungsdaten, z. B. die Zeichenfolge Abfrageteil der URL für Anwendungen, die über das Internet bereitgestellt enthält.</span><span class="sxs-lookup"><span data-stu-id="7abd9-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="7abd9-114">[out] Der Wert, der vom Einstiegspunkt der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7abd9-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7abd9-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7abd9-115">Return Value</span></span>  
  
|<span data-ttu-id="7abd9-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7abd9-116">HRESULT</span></span>|<span data-ttu-id="7abd9-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7abd9-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7abd9-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="7abd9-118">S_OK</span></span>|<span data-ttu-id="7abd9-119">`ExecuteApplication`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7abd9-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="7abd9-120">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="7abd9-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7abd9-121">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7abd9-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7abd9-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7abd9-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7abd9-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7abd9-123">The call timed out.</span></span>|  
|<span data-ttu-id="7abd9-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7abd9-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7abd9-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7abd9-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7abd9-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7abd9-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7abd9-127">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7abd9-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7abd9-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7abd9-128">E_FAIL</span></span>|<span data-ttu-id="7abd9-129">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7abd9-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7abd9-130">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7abd9-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7abd9-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7abd9-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7abd9-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7abd9-132">Remarks</span></span>  
 <span data-ttu-id="7abd9-133">`ExecuteApplication`Dient zum Aktivieren von ClickOnce-Anwendungen in eine neu erstellte Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="7abd9-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="7abd9-134">Die `pReturnValue` Output-Parameter von der Anwendung zurückgegebenen Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7abd9-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="7abd9-135">Wenn Sie angeben, dass einen Wert von Null für `pReturnValue`, `ExecuteApplication` schlägt nicht fehl, aber es gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="7abd9-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7abd9-136">Rufen Sie nicht die [Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der `ExecuteApplication` Methode, um ein Manifest-basierten Anwendung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7abd9-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="7abd9-137">Wenn die `Start` -Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="7abd9-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7abd9-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7abd9-138">Requirements</span></span>  
 <span data-ttu-id="7abd9-139">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7abd9-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7abd9-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7abd9-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7abd9-141">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7abd9-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7abd9-142">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7abd9-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abd9-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7abd9-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="7abd9-144">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7abd9-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="7abd9-145">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="7abd9-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="7abd9-146">Exemplarische Vorgehensweise: Bedarfsgerechtes Herunterladen von Assemblys mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers</span><span class="sxs-lookup"><span data-stu-id="7abd9-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
