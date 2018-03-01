---
title: ICLRHostProtectionManager::SetProtectedCategories-Methode
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
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0971e93f02420966d6561c5b7d4dce8b75e222fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="cea1a-102">ICLRHostProtectionManager::SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="cea1a-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="cea1a-103">Gibt an, welche Kategorien von verwalteten Typen und Membern ausführen in teilweise vertrauenswürdigem Code gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cea1a-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea1a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cea1a-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cea1a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cea1a-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="cea1a-106">[in] Eine Kombination von [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) Werte, der angibt, welche Kategorien von verwalteten Typen und Membern ausführen in teilweise vertrauenswürdigem Code gesperrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cea1a-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cea1a-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cea1a-107">Return Value</span></span>  
  
|<span data-ttu-id="cea1a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cea1a-108">HRESULT</span></span>|<span data-ttu-id="cea1a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cea1a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cea1a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cea1a-110">S_OK</span></span>|<span data-ttu-id="cea1a-111">`SetProtectedCategories`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cea1a-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="cea1a-112">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="cea1a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cea1a-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="cea1a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cea1a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cea1a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cea1a-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cea1a-115">The call timed out.</span></span>|  
|<span data-ttu-id="cea1a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cea1a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cea1a-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cea1a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cea1a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cea1a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cea1a-119">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="cea1a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cea1a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cea1a-120">E_FAIL</span></span>|<span data-ttu-id="cea1a-121">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="cea1a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cea1a-122">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="cea1a-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cea1a-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cea1a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cea1a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cea1a-124">Remarks</span></span>  
 <span data-ttu-id="cea1a-125">Jede `EApiCategories` Wert verweist auf eine Liste von verwalteten Typen und Membern.</span><span class="sxs-lookup"><span data-stu-id="cea1a-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="cea1a-126">Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt zu den verwalteten <xref:System.Security.Permissions.HostProtectionAttribute> -Klasse, die verwendet wird, um das Markieren von verwalteten Typen und Membern, die Funktionen, die Kategorien, die durch beschrieben entspricht verfügbar machen `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="cea1a-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="cea1a-127">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und <xref:System.Security.Permissions.HostProtectionResource> -Enumeration, die direkt entspricht `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="cea1a-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cea1a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cea1a-128">Requirements</span></span>  
 <span data-ttu-id="cea1a-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea1a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea1a-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cea1a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cea1a-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cea1a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cea1a-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea1a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea1a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cea1a-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="cea1a-134">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cea1a-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="cea1a-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cea1a-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="cea1a-136">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cea1a-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
