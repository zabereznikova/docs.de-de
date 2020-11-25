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
ms.openlocfilehash: ef043dd2308c4b76e975bd2ad1f68725579e8fc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728907"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="1823f-102">ICLRRuntimeHost::ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="1823f-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>

<span data-ttu-id="1823f-103">Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1823f-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="1823f-104">Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="1823f-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1823f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1823f-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1823f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1823f-106">Parameters</span></span>  

 `pwzAppFullName`  
 <span data-ttu-id="1823f-107">in Der vollständige Name der Anwendung, wie für definiert <xref:System.ApplicationIdentity> .</span><span class="sxs-lookup"><span data-stu-id="1823f-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="1823f-108">in Die Anzahl der Zeichen folgen, die im Array enthalten sind `ppwzManifestPaths` .</span><span class="sxs-lookup"><span data-stu-id="1823f-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="1823f-109">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="1823f-109">[in] Optional.</span></span> <span data-ttu-id="1823f-110">Ein Zeichen folgen Array, das Manifeste Pfade für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="1823f-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="1823f-111">in Die Anzahl der Zeichen folgen, die im Array enthalten sind `ppwzActivationData` .</span><span class="sxs-lookup"><span data-stu-id="1823f-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="1823f-112">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="1823f-112">[in] Optional.</span></span> <span data-ttu-id="1823f-113">Ein Zeichen folgen Array, das die Aktivierungsdaten der Anwendung enthält, z. b. den Teil der Abfrage Zeichenfolge der URL für Anwendungen, die über das Web bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="1823f-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="1823f-114">vorgenommen Der Wert, der vom Einstiegspunkt der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1823f-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1823f-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1823f-115">Return Value</span></span>  
  
|<span data-ttu-id="1823f-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1823f-116">HRESULT</span></span>|<span data-ttu-id="1823f-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1823f-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1823f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1823f-118">S_OK</span></span>|<span data-ttu-id="1823f-119">`ExecuteApplication` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1823f-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="1823f-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1823f-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1823f-121">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="1823f-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1823f-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1823f-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1823f-123">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="1823f-123">The call timed out.</span></span>|  
|<span data-ttu-id="1823f-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1823f-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1823f-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1823f-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1823f-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1823f-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1823f-127">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="1823f-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1823f-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1823f-128">E_FAIL</span></span>|<span data-ttu-id="1823f-129">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1823f-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1823f-130">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="1823f-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1823f-131">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1823f-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1823f-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1823f-132">Remarks</span></span>  

 <span data-ttu-id="1823f-133">`ExecuteApplication` wird verwendet, um ClickOnce-Anwendungen in einer neu erstellten Anwendungsdomäne zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1823f-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="1823f-134">Der `pReturnValue` Output-Parameter wird auf den Wert festgelegt, der von der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1823f-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="1823f-135">Wenn Sie für den Wert NULL angeben, `pReturnValue` schlägt `ExecuteApplication` nicht fehl, aber es wird kein Wert zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1823f-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1823f-136">Rufen Sie nicht die Methode [Start Methode](iclrruntimehost-start-method.md) auf, bevor Sie die- `ExecuteApplication` Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1823f-136">Do not call the [Start Method](iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="1823f-137">Wenn die- `Start` Methode zuerst aufgerufen wird, kann der `ExecuteApplication` Methodenaufruf nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1823f-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1823f-138">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1823f-138">Requirements</span></span>  

 <span data-ttu-id="1823f-139">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1823f-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1823f-140">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1823f-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1823f-141">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1823f-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1823f-142">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1823f-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1823f-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1823f-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="1823f-144">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1823f-144">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="1823f-145">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="1823f-145">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="1823f-146">Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der ClickOnce-Bereitstellungs-API mit</span><span class="sxs-lookup"><span data-stu-id="1823f-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
