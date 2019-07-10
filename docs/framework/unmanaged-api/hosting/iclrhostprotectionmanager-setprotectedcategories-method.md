---
title: ICLRHostProtectionManager::SetProtectedCategories-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f6dc1254261197583f2369587a61b5e179d760b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779644"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="20997-102">ICLRHostProtectionManager::SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="20997-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="20997-103">Gibt an, welche Kategorien von verwalteten Typen und Membern ausführen in teilweise vertrauenswürdigen Code blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20997-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20997-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20997-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20997-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20997-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="20997-106">[in] Eine Kombination von [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) Werte, der angibt, welche Kategorien von verwalteten Typen und Membern ausführen in teilweise vertrauenswürdigen Code blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20997-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20997-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20997-107">Return Value</span></span>  
  
|<span data-ttu-id="20997-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20997-108">HRESULT</span></span>|<span data-ttu-id="20997-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20997-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20997-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="20997-110">S_OK</span></span>|<span data-ttu-id="20997-111">`SetProtectedCategories` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20997-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="20997-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="20997-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="20997-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="20997-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="20997-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="20997-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="20997-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="20997-115">The call timed out.</span></span>|  
|<span data-ttu-id="20997-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="20997-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="20997-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="20997-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="20997-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="20997-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="20997-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="20997-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="20997-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="20997-120">E_FAIL</span></span>|<span data-ttu-id="20997-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="20997-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="20997-122">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20997-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="20997-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="20997-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20997-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20997-124">Remarks</span></span>  
 <span data-ttu-id="20997-125">Jede `EApiCategories` Wert verweist auf eine Liste der verwalteten Typen und Membern.</span><span class="sxs-lookup"><span data-stu-id="20997-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="20997-126">Die `EApiCategories` Enumeration und die `SetProtectedCategories` Methode beziehen sich direkt an die verwaltete <xref:System.Security.Permissions.HostProtectionAttribute> -Klasse, die verwendet wird, um verwaltete Typen und Member, die Funktionen von beschriebenen Kategorien verfügbar machen `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="20997-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="20997-127">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und <xref:System.Security.Permissions.HostProtectionResource> -Enumeration, die direkt entspricht `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="20997-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20997-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20997-128">Requirements</span></span>  
 <span data-ttu-id="20997-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20997-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20997-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20997-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20997-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20997-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20997-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20997-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20997-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20997-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="20997-134">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="20997-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="20997-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20997-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="20997-136">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20997-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
