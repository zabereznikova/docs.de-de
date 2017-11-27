---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80ffc1cb4c1387aae673ec757b846c7075e20b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="1603f-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="1603f-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="1603f-103">Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten auf die von der Assembly mit dem angegebenen Identitätstyp verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1603f-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1603f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1603f-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1603f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1603f-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="1603f-106">[in] Ein gültiger Wert, der die Prozessorarchitektur angibt, wie in "Winnt.h" definiert.</span><span class="sxs-lookup"><span data-stu-id="1603f-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1603f-107">[in] Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1603f-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="1603f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1603f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="1603f-109">[in] Ein nicht transparenter Bindung Assemblyidentität, in der Regel von einem Aufruf zurückgegebene der [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) oder [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="1603f-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="1603f-110">[out] Einen Schnittstellenzeiger auf eine `ICLRProbingAssemblyEnum` Enumerator, der Verweise auf Assemblys, auf die durch die Assembly verweist enthält `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="1603f-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1603f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1603f-111">Return Value</span></span>  
  
|<span data-ttu-id="1603f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1603f-112">HRESULT</span></span>|<span data-ttu-id="1603f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1603f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1603f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1603f-114">S_OK</span></span>|<span data-ttu-id="1603f-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1603f-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="1603f-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="1603f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1603f-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1603f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1603f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1603f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1603f-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1603f-119">The call timed out.</span></span>|  
|<span data-ttu-id="1603f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1603f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1603f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1603f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1603f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1603f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1603f-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1603f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1603f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1603f-124">E_FAIL</span></span>|<span data-ttu-id="1603f-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1603f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1603f-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="1603f-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1603f-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1603f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1603f-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1603f-128">Requirements</span></span>  
 <span data-ttu-id="1603f-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1603f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1603f-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1603f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1603f-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1603f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1603f-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1603f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1603f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1603f-133">See Also</span></span>  
 [<span data-ttu-id="1603f-134">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1603f-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="1603f-135">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1603f-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="1603f-136">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1603f-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
