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
ms.openlocfilehash: e3f2429462b4454e87690d98ad9fb446574add91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141033"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="f0014-102">ICLRHostProtectionManager::SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="f0014-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="f0014-103">Gibt an, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0014-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0014-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0014-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0014-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0014-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="f0014-106">in Eine Kombination aus [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) -Werten, die angibt, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0014-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0014-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0014-107">Return Value</span></span>  
  
|<span data-ttu-id="f0014-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0014-108">HRESULT</span></span>|<span data-ttu-id="f0014-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0014-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f0014-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0014-110">S_OK</span></span>|<span data-ttu-id="f0014-111">`SetProtectedCategories` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f0014-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="f0014-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f0014-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f0014-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f0014-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f0014-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f0014-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f0014-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="f0014-115">The call timed out.</span></span>|  
|<span data-ttu-id="f0014-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f0014-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f0014-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f0014-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f0014-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f0014-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f0014-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f0014-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f0014-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f0014-120">E_FAIL</span></span>|<span data-ttu-id="f0014-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0014-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f0014-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0014-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f0014-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f0014-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0014-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0014-124">Remarks</span></span>  
 <span data-ttu-id="f0014-125">Jeder `EApiCategories` Wert verweist auf eine Liste verwalteter Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="f0014-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="f0014-126">Die `EApiCategories`-Enumeration und die `SetProtectedCategories`-Methode sind direkt mit der verwalteten <xref:System.Security.Permissions.HostProtectionAttribute>-Klasse verknüpft, mit der verwaltete Typen und Member gekennzeichnet werden, die Funktionen verfügbar machen, die den in `EApiCategories`beschriebenen Kategorien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="f0014-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="f0014-127">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und der <xref:System.Security.Permissions.HostProtectionResource>-Enumeration, die `EApiCategories`direkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="f0014-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0014-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0014-128">Requirements</span></span>  
 <span data-ttu-id="f0014-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0014-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0014-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f0014-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0014-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0014-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0014-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0014-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0014-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0014-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="f0014-134">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f0014-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="f0014-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0014-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="f0014-136">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0014-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
