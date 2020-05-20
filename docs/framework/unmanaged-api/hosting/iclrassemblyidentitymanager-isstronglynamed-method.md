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
ms.openlocfilehash: d388f366671f50c3dcb3bd9d387300dd1bbb168f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615903"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="8700a-102">ICLRAssemblyIdentityManager::IsStronglyNamed-Methode</span><span class="sxs-lookup"><span data-stu-id="8700a-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="8700a-103">Ruft einen Wert ab, der angibt, ob die angegebene Assembly einen starken Namen hat.</span><span class="sxs-lookup"><span data-stu-id="8700a-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8700a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8700a-104">Syntax</span></span>  
  
```cpp  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8700a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8700a-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="8700a-106">in Die nicht transparenten kanonischen Assemblyidentitätsdaten der Assembly, die ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8700a-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="8700a-107">[out] `true` , wenn die Assembly, auf die durch den-Parameter verwiesen wird, einen `pwzAssemblyIdentity` starken Namen hat, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="8700a-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8700a-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8700a-108">Return Value</span></span>  
  
|<span data-ttu-id="8700a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8700a-109">HRESULT</span></span>|<span data-ttu-id="8700a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8700a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8700a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8700a-111">S_OK</span></span>|<span data-ttu-id="8700a-112">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8700a-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="8700a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8700a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8700a-114">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8700a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8700a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8700a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8700a-116">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="8700a-116">The call timed out.</span></span>|  
|<span data-ttu-id="8700a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8700a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8700a-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="8700a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8700a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8700a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8700a-120">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="8700a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8700a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8700a-121">E_FAIL</span></span>|<span data-ttu-id="8700a-122">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8700a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8700a-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8700a-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8700a-124">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8700a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8700a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8700a-125">Requirements</span></span>  
 <span data-ttu-id="8700a-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8700a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8700a-127">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8700a-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8700a-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8700a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8700a-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8700a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8700a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8700a-130">See also</span></span>

- [<span data-ttu-id="8700a-131">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8700a-131">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
