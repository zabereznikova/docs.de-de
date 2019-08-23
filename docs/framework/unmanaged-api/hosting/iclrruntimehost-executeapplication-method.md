---
title: ICLRRuntimeHost::ExecuteApplication-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965359"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="fe264-102">ICLRRuntimeHost::ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="fe264-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="fe264-103">Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe264-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="fe264-104">Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="fe264-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe264-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe264-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe264-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe264-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="fe264-107">in Der vollständige Name der Anwendung, wie für <xref:System.ApplicationIdentity>definiert.</span><span class="sxs-lookup"><span data-stu-id="fe264-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="fe264-108">in Die Anzahl der Zeichen folgen, die `ppwzManifestPaths` im Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fe264-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="fe264-109">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="fe264-109">[in] Optional.</span></span> <span data-ttu-id="fe264-110">Ein Zeichen folgen Array, das Manifeste Pfade für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="fe264-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="fe264-111">in Die Anzahl der Zeichen folgen, die `ppwzActivationData` im Array enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fe264-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="fe264-112">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="fe264-112">[in] Optional.</span></span> <span data-ttu-id="fe264-113">Ein Zeichen folgen Array, das die Aktivierungsdaten der Anwendung enthält, z. b. den Teil der Abfrage Zeichenfolge der URL für Anwendungen, die über das Web bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="fe264-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="fe264-114">vorgenommen Der Wert, der vom Einstiegspunkt der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe264-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe264-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe264-115">Return Value</span></span>  
  
|<span data-ttu-id="fe264-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe264-116">HRESULT</span></span>|<span data-ttu-id="fe264-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe264-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fe264-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe264-118">S_OK</span></span>|<span data-ttu-id="fe264-119">`ExecuteApplication`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe264-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="fe264-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fe264-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fe264-121">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fe264-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fe264-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fe264-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fe264-123">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="fe264-123">The call timed out.</span></span>|  
|<span data-ttu-id="fe264-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fe264-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fe264-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fe264-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fe264-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fe264-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fe264-127">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="fe264-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fe264-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fe264-128">E_FAIL</span></span>|<span data-ttu-id="fe264-129">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fe264-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fe264-130">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe264-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fe264-131">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fe264-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe264-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe264-132">Remarks</span></span>  
 <span data-ttu-id="fe264-133">`ExecuteApplication`wird verwendet, um ClickOnce-Anwendungen in einer neu erstellten Anwendungsdomäne zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe264-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="fe264-134">Der `pReturnValue` Output-Parameter wird auf den Wert festgelegt, der von der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="fe264-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="fe264-135">Wenn Sie für `pReturnValue` `ExecuteApplication` den Wert NULL angeben, schlägt nicht fehl, aber es wird kein Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fe264-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fe264-136">Rufen Sie nicht die Methode [Start Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) auf, bevor `ExecuteApplication` Sie die-Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe264-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="fe264-137">Wenn die `Start` -Methode zuerst aufgerufen wird, `ExecuteApplication` kann der Methodenaufruf nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe264-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe264-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe264-138">Requirements</span></span>  
 <span data-ttu-id="fe264-139">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe264-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe264-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fe264-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fe264-141">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fe264-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe264-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe264-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe264-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe264-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="fe264-144">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe264-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="fe264-145">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="fe264-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="fe264-146">Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers</span><span class="sxs-lookup"><span data-stu-id="fe264-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
