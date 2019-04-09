---
title: ICLRAssemblyIdentityManager::IsStronglyNamed-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 166583f690fc7ed80f80cf2cf5cd5b0348708cc3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159717"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="cf122-102">ICLRAssemblyIdentityManager::IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="cf122-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="cf122-103">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="cf122-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf122-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf122-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf122-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf122-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="cf122-106">[in] Das nicht transparente kanonische Assemblyidentitätsdaten der Assembly, die ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cf122-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="cf122-107">[out] `true`, wenn die Assembly verweist die `pwzAssemblyIdentity` Parameter stark benannt ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="cf122-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf122-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cf122-108">Return Value</span></span>  
  
|<span data-ttu-id="cf122-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf122-109">HRESULT</span></span>|<span data-ttu-id="cf122-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf122-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf122-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf122-111">S_OK</span></span>|<span data-ttu-id="cf122-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cf122-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="cf122-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cf122-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cf122-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cf122-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cf122-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cf122-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cf122-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cf122-116">The call timed out.</span></span>|  
|<span data-ttu-id="cf122-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf122-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cf122-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cf122-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cf122-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cf122-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cf122-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="cf122-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cf122-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cf122-121">E_FAIL</span></span>|<span data-ttu-id="cf122-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cf122-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cf122-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cf122-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cf122-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cf122-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf122-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf122-125">Requirements</span></span>  
 <span data-ttu-id="cf122-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf122-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf122-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cf122-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf122-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cf122-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cf122-129">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cf122-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cf122-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf122-130">See also</span></span>

- [<span data-ttu-id="cf122-131">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cf122-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
