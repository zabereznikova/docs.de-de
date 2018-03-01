---
title: ICLRAssemblyIdentityManager::IsStronglyNamed-Methode
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
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1cb727d9144fc3364a04cd5b9064527c55f5ee79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="ec40f-102">ICLRAssemblyIdentityManager::IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="ec40f-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="ec40f-103">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="ec40f-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec40f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec40f-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec40f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec40f-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="ec40f-106">[in] Die nicht transparenten kanonischen Assemblyidentitätsdaten der Assembly, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="ec40f-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="ec40f-107">[out] `true`, wenn die Assembly verweist die `pwzAssemblyIdentity` Parameter stark benannt ist; andernfalls, `false`.</span><span class="sxs-lookup"><span data-stu-id="ec40f-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec40f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec40f-108">Return Value</span></span>  
  
|<span data-ttu-id="ec40f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec40f-109">HRESULT</span></span>|<span data-ttu-id="ec40f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec40f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec40f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec40f-111">S_OK</span></span>|<span data-ttu-id="ec40f-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ec40f-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="ec40f-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ec40f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec40f-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ec40f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec40f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec40f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec40f-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ec40f-116">The call timed out.</span></span>|  
|<span data-ttu-id="ec40f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec40f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec40f-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ec40f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec40f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec40f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec40f-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ec40f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec40f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec40f-121">E_FAIL</span></span>|<span data-ttu-id="ec40f-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ec40f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec40f-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ec40f-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec40f-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ec40f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec40f-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec40f-125">Requirements</span></span>  
 <span data-ttu-id="ec40f-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec40f-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec40f-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec40f-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec40f-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ec40f-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec40f-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec40f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec40f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec40f-130">See Also</span></span>  
 [<span data-ttu-id="ec40f-131">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec40f-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
