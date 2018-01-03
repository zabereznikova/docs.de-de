---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec4cf37150cab7b52066a884b6fe117b0e611106
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="be264-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="be264-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="be264-103">Ruft die angegebene Methode des angegebenen Typs in der angegebenen verwalteten Assembly.</span><span class="sxs-lookup"><span data-stu-id="be264-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be264-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be264-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be264-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be264-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="be264-106">[in] Der Pfad zu der <xref:System.Reflection.Assembly> , definiert die <xref:System.Type> , dessen Methode besteht darin, aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="be264-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="be264-107">[in] Der Name des der <xref:System.Type> , die für die aufzurufende Methode definiert.</span><span class="sxs-lookup"><span data-stu-id="be264-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="be264-108">[in] Der Name der aufzurufenden Methode.</span><span class="sxs-lookup"><span data-stu-id="be264-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="be264-109">[in] Der Zeichenfolgenparameter an die Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="be264-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="be264-110">[out] Der Integer-Wert, der von der aufgerufenen Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="be264-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be264-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="be264-111">Return Value</span></span>  
  
|<span data-ttu-id="be264-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="be264-112">HRESULT</span></span>|<span data-ttu-id="be264-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be264-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="be264-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="be264-114">S_OK</span></span>|<span data-ttu-id="be264-115">`ExecuteInDefaultAppDomain`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be264-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="be264-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="be264-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="be264-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="be264-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="be264-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="be264-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="be264-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="be264-119">The call timed out.</span></span>|  
|<span data-ttu-id="be264-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="be264-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="be264-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="be264-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="be264-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="be264-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="be264-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="be264-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="be264-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="be264-124">E_FAIL</span></span>|<span data-ttu-id="be264-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="be264-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="be264-126">Wenn eine Methode E_FAIL zurückgibt, ist die Zertifikatsperrliste nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="be264-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="be264-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="be264-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="be264-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be264-128">Remarks</span></span>  
 <span data-ttu-id="be264-129">Die aufgerufene Methode muss die folgende Signatur aufweisen:</span><span class="sxs-lookup"><span data-stu-id="be264-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="be264-130">wobei `pwzMethodName` den Namen der aufgerufenen Methode darstellt und `pwzArgument` darstellt, die der Zeichenfolgenwert an diese Methode als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="be264-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="be264-131">Wenn der HRESULT-Wert, mit S_OK festgelegt ist, `pReturnValue` auf den ganzzahligen Wert zurückgegeben, die von der aufgerufenen Methode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="be264-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="be264-132">Andernfalls `pReturnValue` ist nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="be264-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be264-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be264-133">Requirements</span></span>  
 <span data-ttu-id="be264-134">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be264-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be264-135">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="be264-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be264-136">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="be264-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be264-137">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be264-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be264-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be264-138">See Also</span></span>  
 [<span data-ttu-id="be264-139">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be264-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
