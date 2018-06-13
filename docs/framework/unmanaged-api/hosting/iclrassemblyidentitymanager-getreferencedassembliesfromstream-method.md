---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a5020b387abcdcdc0047de90eb588157eaec08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435309"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="610a8-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="610a8-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="610a8-103">Ruft einen Zeiger auf eine [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) Objekt, das für die Assemblys, die von der Assembly im angegebenen Stream Assemblyidentitätsdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="610a8-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="610a8-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="610a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="610a8-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="610a8-106">[in] Einen Schnittstellenzeiger auf eine `IStream` , die den Assemblyanzeigenamen ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="610a8-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="610a8-107">[in] Für zukünftige Erweiterungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="610a8-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="610a8-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="610a8-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="610a8-109">[in] Ein Zeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Objekt, das Assembly-Identitätsdaten für die Assemblys von ausgeschlossen werden enthält `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="610a8-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="610a8-110">[out] Ein Zeiger auf die Adresse des ein `ICLRReferenceAssemblyEnum` Objekt, das für die Assemblys, die von der Assembly im Assemblyidentitätsdaten enthält `pStream`, mit Ausnahme der Assemblys im `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="610a8-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="610a8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="610a8-111">Return Value</span></span>  
  
|<span data-ttu-id="610a8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="610a8-112">HRESULT</span></span>|<span data-ttu-id="610a8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="610a8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="610a8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="610a8-114">S_OK</span></span>|<span data-ttu-id="610a8-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="610a8-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="610a8-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="610a8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="610a8-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="610a8-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="610a8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="610a8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="610a8-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="610a8-119">The call timed out.</span></span>|  
|<span data-ttu-id="610a8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="610a8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="610a8-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="610a8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="610a8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="610a8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="610a8-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="610a8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="610a8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="610a8-124">E_FAIL</span></span>|<span data-ttu-id="610a8-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="610a8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="610a8-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="610a8-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="610a8-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="610a8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="610a8-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="610a8-128">Remarks</span></span>  
 <span data-ttu-id="610a8-129">Der Aufrufer können einen Satz bekannter Assemblyverweise aus der zurückgegebenen Liste ausschließen.</span><span class="sxs-lookup"><span data-stu-id="610a8-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="610a8-130">Dieser Satz wird definiert, indem `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="610a8-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610a8-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="610a8-131">Requirements</span></span>  
 <span data-ttu-id="610a8-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="610a8-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="610a8-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="610a8-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="610a8-134">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="610a8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="610a8-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="610a8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610a8-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610a8-136">See Also</span></span>  
 [<span data-ttu-id="610a8-137">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="610a8-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="610a8-138">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="610a8-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="610a8-139">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="610a8-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
