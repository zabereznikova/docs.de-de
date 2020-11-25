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
ms.openlocfilehash: 0557a8f1c7c495950933a44cacd23ada8e84964e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730499"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="e6ca6-102">ICLRHostProtectionManager::SetProtectedCategories-Methode</span><span class="sxs-lookup"><span data-stu-id="e6ca6-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>

<span data-ttu-id="e6ca6-103">Gibt an, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6ca6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6ca6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6ca6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6ca6-105">Parameters</span></span>  

 `categories`  
 <span data-ttu-id="e6ca6-106">in Eine Kombination aus [EApiCategories](eapicategories-enumeration.md) -Werten, die angibt, welche Kategorien von verwalteten Typen und Membern für die Ausführung in teilweise vertrauenswürdigem Code blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-106">[in] A combination of [EApiCategories](eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6ca6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6ca6-107">Return Value</span></span>  
  
|<span data-ttu-id="e6ca6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6ca6-108">HRESULT</span></span>|<span data-ttu-id="e6ca6-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6ca6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6ca6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6ca6-110">S_OK</span></span>|<span data-ttu-id="e6ca6-111">`SetProtectedCategories` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="e6ca6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6ca6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6ca6-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6ca6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6ca6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6ca6-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-115">The call timed out.</span></span>|  
|<span data-ttu-id="e6ca6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6ca6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6ca6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6ca6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6ca6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6ca6-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6ca6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6ca6-120">E_FAIL</span></span>|<span data-ttu-id="e6ca6-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6ca6-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6ca6-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6ca6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6ca6-124">Remarks</span></span>  

 <span data-ttu-id="e6ca6-125">Jeder `EApiCategories` Wert verweist auf eine Liste verwalteter Typen und Member.</span><span class="sxs-lookup"><span data-stu-id="e6ca6-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="e6ca6-126">Die `EApiCategories` -Enumeration und die- `SetProtectedCategories` Methode sind direkt mit der verwalteten-Klasse verknüpft, mit der verwaltete Typen und Member gekennzeichnet werden, die Funktionen verfügbar machen, <xref:System.Security.Permissions.HostProtectionAttribute> die den in beschriebenen Kategorien entsprechen `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="e6ca6-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="e6ca6-127">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.HostProtectionAttribute> und in der- <xref:System.Security.Permissions.HostProtectionResource> Enumeration, die direkt entspricht `EApiCategories` .</span><span class="sxs-lookup"><span data-stu-id="e6ca6-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6ca6-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e6ca6-128">Requirements</span></span>  

 <span data-ttu-id="e6ca6-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6ca6-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6ca6-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e6ca6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6ca6-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6ca6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6ca6-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6ca6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ca6-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6ca6-133">See also</span></span>

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [<span data-ttu-id="e6ca6-134">EApiCategories-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e6ca6-134">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="e6ca6-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6ca6-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="e6ca6-136">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6ca6-136">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
