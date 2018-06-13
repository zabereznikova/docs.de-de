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
ms.openlocfilehash: be778fed910b2cbdbf5e9ae7754abae437ef6bec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433733"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="a526f-102">ICLRControl::SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="a526f-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="a526f-103">Legt einen von abgeleiteten Typ <xref:System.AppDomainManager> als Typ für Anwendungsdomänen-Manager.</span><span class="sxs-lookup"><span data-stu-id="a526f-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a526f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a526f-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a526f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a526f-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="a526f-106">[in] Der Name der Assembly, in dem der angeforderte Typ abgeleitet <xref:System.AppDomainManager> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a526f-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="a526f-107">[in] Der Name des Typs in implementiert die `pwzAppDomainManagerAssembly` Parameter, der die Funktionen von implementiert <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="a526f-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a526f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a526f-108">Return Value</span></span>  
  
|<span data-ttu-id="a526f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a526f-109">HRESULT</span></span>|<span data-ttu-id="a526f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a526f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a526f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a526f-111">S_OK</span></span>|<span data-ttu-id="a526f-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a526f-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="a526f-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="a526f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a526f-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a526f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a526f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a526f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a526f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a526f-116">The call timed out.</span></span>|  
|<span data-ttu-id="a526f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a526f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a526f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a526f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a526f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a526f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a526f-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a526f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a526f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a526f-121">E_FAIL</span></span>|<span data-ttu-id="a526f-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a526f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a526f-123">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a526f-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a526f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a526f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a526f-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a526f-125">Requirements</span></span>  
 <span data-ttu-id="a526f-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a526f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a526f-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a526f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a526f-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a526f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a526f-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a526f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a526f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a526f-130">See Also</span></span>  
 [<span data-ttu-id="a526f-131">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a526f-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a526f-132">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a526f-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
