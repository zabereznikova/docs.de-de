---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55f3bd89f0ca177bcd4edef2e17a7d2256a0042a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773491"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="c4252-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="c4252-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="c4252-103">Ruft eine [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) Enumerator für die Assemblyidentitäten, die von der Assembly mit dem angegebenen Identitätstyp verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c4252-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4252-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4252-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4252-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4252-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="c4252-106">[in] Ein gültiger Wert, der die Prozessorarchitektur, angibt, wie in "Winnt.h" definiert.</span><span class="sxs-lookup"><span data-stu-id="c4252-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c4252-107">[in] Für eine zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c4252-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c4252-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c4252-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="c4252-109">[in] Eine nicht transparente Bindung Assemblyidentität, in der Regel von einem Aufruf zurückgegeben. die [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) oder [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c4252-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="c4252-110">[out] Einen Schnittstellenzeiger auf ein `ICLRProbingAssemblyEnum` Enumerator, der Verweise auf die Assemblys, auf die durch die Assembly enthält `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c4252-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4252-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4252-111">Return Value</span></span>  
  
|<span data-ttu-id="c4252-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c4252-112">HRESULT</span></span>|<span data-ttu-id="c4252-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4252-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4252-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4252-114">S_OK</span></span>|<span data-ttu-id="c4252-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4252-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="c4252-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c4252-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c4252-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c4252-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c4252-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c4252-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c4252-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4252-119">The call timed out.</span></span>|  
|<span data-ttu-id="c4252-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c4252-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c4252-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c4252-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c4252-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c4252-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c4252-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="c4252-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c4252-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c4252-124">E_FAIL</span></span>|<span data-ttu-id="c4252-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c4252-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c4252-126">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4252-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c4252-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c4252-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4252-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4252-128">Requirements</span></span>  
 <span data-ttu-id="c4252-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4252-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4252-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c4252-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4252-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4252-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4252-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4252-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4252-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4252-133">See also</span></span>

- [<span data-ttu-id="c4252-134">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4252-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c4252-135">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4252-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c4252-136">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4252-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
