---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 856843cf1c4c5f1dffe23b04cf2655dfe37e476e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="ea192-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="ea192-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="ea192-103">Ruft eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Instanz, eine Liste der Assemblys enthält, auf die Assembly auf der angegebene Pfad verweist.</span><span class="sxs-lookup"><span data-stu-id="ea192-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea192-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea192-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea192-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea192-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="ea192-106">[in] Der Pfad zur Assembly, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="ea192-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ea192-107">[in] Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ea192-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="ea192-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea192-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="ea192-109">[in] Ein Zeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) -Objekt, das Assemblys darstellt, die von ausgeschlossen werden sollten `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="ea192-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="ea192-110">[out] Ein Zeiger auf die Adresse des ein `ICLRReferenceAssemblyEnum` Objekt, das für die Assemblys, die von der Assembly verwiesen Assemblyidentitätsdaten enthält `pwzFilePath`, mit Ausnahme der Assemblys, dargestellt durch `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="ea192-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea192-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea192-111">Return Value</span></span>  
  
|<span data-ttu-id="ea192-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea192-112">HRESULT</span></span>|<span data-ttu-id="ea192-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea192-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ea192-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea192-114">S_OK</span></span>|<span data-ttu-id="ea192-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea192-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="ea192-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="ea192-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ea192-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ea192-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ea192-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ea192-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ea192-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ea192-119">The call timed out.</span></span>|  
|<span data-ttu-id="ea192-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ea192-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ea192-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ea192-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ea192-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ea192-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ea192-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ea192-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ea192-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ea192-124">E_FAIL</span></span>|<span data-ttu-id="ea192-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="ea192-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ea192-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="ea192-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ea192-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ea192-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea192-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea192-128">Remarks</span></span>  
 <span data-ttu-id="ea192-129">Der Aufrufer können einen Satz bekannter Assemblyverweise aus der zurückgegebenen Liste ausschließen.</span><span class="sxs-lookup"><span data-stu-id="ea192-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="ea192-130">Diese Gruppe wird definiert, durch die `pExcludeAssembliesList` Parameter.</span><span class="sxs-lookup"><span data-stu-id="ea192-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea192-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea192-131">Requirements</span></span>  
 <span data-ttu-id="ea192-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea192-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea192-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ea192-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ea192-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ea192-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ea192-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea192-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea192-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea192-136">See Also</span></span>  
 [<span data-ttu-id="ea192-137">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea192-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="ea192-138">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea192-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="ea192-139">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea192-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
