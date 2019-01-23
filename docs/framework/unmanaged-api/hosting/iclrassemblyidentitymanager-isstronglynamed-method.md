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
ms.openlocfilehash: a958e38857d2407930cb8c03a08eabdf6574cda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563887"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="94681-102">ICLRAssemblyIdentityManager::IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="94681-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="94681-103">Ruft einen Wert, der angibt, ob die angegebene Assembly stark benannt wird.</span><span class="sxs-lookup"><span data-stu-id="94681-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94681-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94681-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94681-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94681-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="94681-106">[in] Das nicht transparente kanonische Assemblyidentitätsdaten der Assembly, die ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="94681-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="94681-107">[out] `true`, wenn die Assembly verweist die `pwzAssemblyIdentity` Parameter stark benannt ist; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="94681-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94681-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="94681-108">Return Value</span></span>  
  
|<span data-ttu-id="94681-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94681-109">HRESULT</span></span>|<span data-ttu-id="94681-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="94681-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94681-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="94681-111">S_OK</span></span>|<span data-ttu-id="94681-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="94681-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="94681-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="94681-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="94681-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="94681-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="94681-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="94681-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="94681-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94681-116">The call timed out.</span></span>|  
|<span data-ttu-id="94681-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="94681-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="94681-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="94681-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="94681-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="94681-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="94681-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="94681-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="94681-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94681-121">E_FAIL</span></span>|<span data-ttu-id="94681-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="94681-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="94681-123">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94681-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="94681-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="94681-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94681-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94681-125">Requirements</span></span>  
 <span data-ttu-id="94681-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94681-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94681-127">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94681-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94681-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94681-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94681-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94681-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94681-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94681-130">See also</span></span>
- [<span data-ttu-id="94681-131">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94681-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
