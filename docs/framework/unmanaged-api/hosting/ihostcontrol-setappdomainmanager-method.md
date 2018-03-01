---
title: IHostControl::SetAppDomainManager-Methode
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
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d689a664f5bad19a70a8d635beb1f25f33da6ff6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrolsetappdomainmanager-method"></a><span data-ttu-id="7c575-102">IHostControl::SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="7c575-102">IHostControl::SetAppDomainManager Method</span></span>
<span data-ttu-id="7c575-103">Benachrichtigt den Host an, dass eine Anwendungsdomäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7c575-103">Notifies the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c575-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c575-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c575-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c575-105">Parameters</span></span>  
 `dwAppDomainID`  
 <span data-ttu-id="7c575-106">[in] Den numerischen Bezeichner des ausgewählten <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7c575-106">[in] The numeric identifier of the selected <xref:System.AppDomain>.</span></span>  
  
 `pUnkAppDomainManager`  
 <span data-ttu-id="7c575-107">[in] Ein Zeiger auf die <xref:System.AppDomainManager> -Objekt, das der Host als implementiert `IUnknown`.</span><span class="sxs-lookup"><span data-stu-id="7c575-107">[in] A pointer to the <xref:System.AppDomainManager> object that the host implements as `IUnknown`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c575-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7c575-108">Return Value</span></span>  
  
|<span data-ttu-id="7c575-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c575-109">HRESULT</span></span>|<span data-ttu-id="7c575-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c575-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c575-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c575-111">S_OK</span></span>|<span data-ttu-id="7c575-112">`SetAppDomainManager`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c575-112">`SetAppDomainManager` returned successfully.</span></span>|  
|<span data-ttu-id="7c575-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="7c575-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c575-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7c575-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c575-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c575-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c575-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7c575-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c575-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c575-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c575-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7c575-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c575-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c575-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c575-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7c575-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c575-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c575-121">E_FAIL</span></span>|<span data-ttu-id="7c575-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7c575-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c575-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="7c575-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c575-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7c575-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c575-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c575-125">Remarks</span></span>  
 <span data-ttu-id="7c575-126">Die <xref:System.AppDomainManager> ermöglicht es dem Host einen Mechanismus zum Bootstrapping in verwaltetem Code und zum Steuern der Erstellung und die Einstellungen der einzelnen <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7c575-126">The <xref:System.AppDomainManager> provides the host with a mechanism to bootstrap into managed code and to control the creation and settings of each <xref:System.AppDomain>.</span></span> <span data-ttu-id="7c575-127">Die <xref:System.AppDomainManager> wird in jeder geladen <xref:System.AppDomain> beim, <xref:System.AppDomain> wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="7c575-127">The <xref:System.AppDomainManager> is loaded into each <xref:System.AppDomain> when that <xref:System.AppDomain> is created.</span></span> <span data-ttu-id="7c575-128">Wenn es sich entscheidet, die CLR benachrichtigt den Host, dass die Anwendungsdomäne erstellt wurde, indem Sie den Wert der Einstellung der `pUnkAppDomainManager` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7c575-128">If it chooses, the CLR notifies the host that the application domain has been created by setting the value of the `pUnkAppDomainManager` parameter.</span></span>  
  
 <span data-ttu-id="7c575-129">In seiner Implementierung von der `SetAppDomainManager` -Methode, die können festgelegt werden, den Assemblynamen und Typ für den Anwendungsdomänen-Manager.</span><span class="sxs-lookup"><span data-stu-id="7c575-129">In its implementation of the `SetAppDomainManager` method, the host can set the assembly name and type for the application domain manager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c575-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c575-130">Requirements</span></span>  
 <span data-ttu-id="7c575-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c575-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c575-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c575-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c575-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c575-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c575-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c575-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c575-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c575-135">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="7c575-136">IHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c575-136">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
