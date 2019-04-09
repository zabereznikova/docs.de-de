---
title: ICLRControl::SetAppDomainManagerType-Methode
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eacd3802c51cb6ccf3f7ba874c75a2d2774439d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091188"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="6668d-102">ICLRControl::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="6668d-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="6668d-103">Legt die von abgeleiteten Typs <xref:System.AppDomainManager> als Typ für Anwendungsdomänen-Manager.</span><span class="sxs-lookup"><span data-stu-id="6668d-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6668d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6668d-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6668d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6668d-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="6668d-106">[in] Der Name der Assembly, in dem der angeforderte Typ abgeleitet <xref:System.AppDomainManager> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="6668d-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="6668d-107">[in] Der Name des implementierten Typs der `pwzAppDomainManagerAssembly` Parameter, der die Funktionen von implementiert <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="6668d-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6668d-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6668d-108">Return Value</span></span>  
  
|<span data-ttu-id="6668d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6668d-109">HRESULT</span></span>|<span data-ttu-id="6668d-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6668d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6668d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6668d-111">S_OK</span></span>|<span data-ttu-id="6668d-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6668d-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="6668d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6668d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6668d-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6668d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6668d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6668d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6668d-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6668d-116">The call timed out.</span></span>|  
|<span data-ttu-id="6668d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6668d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6668d-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="6668d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6668d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6668d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6668d-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="6668d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6668d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6668d-121">E_FAIL</span></span>|<span data-ttu-id="6668d-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6668d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6668d-123">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6668d-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6668d-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6668d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6668d-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6668d-125">Requirements</span></span>  
 <span data-ttu-id="6668d-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6668d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6668d-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6668d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6668d-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6668d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6668d-129">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6668d-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6668d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6668d-130">See also</span></span>

- [<span data-ttu-id="6668d-131">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6668d-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6668d-132">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6668d-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
