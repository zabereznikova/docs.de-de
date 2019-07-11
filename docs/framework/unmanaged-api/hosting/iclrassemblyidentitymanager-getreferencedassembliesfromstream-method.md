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
ms.openlocfilehash: 9655981bf7ca21a6f59b305f6ea3fa5ff47f608a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773399"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="09d57-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="09d57-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="09d57-103">Ruft einen Zeiger auf ein [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) -Objekt, das Assembly für die Assemblys, auf die verwiesen wird durch die Assembly im angegebenen Stream enthält.</span><span class="sxs-lookup"><span data-stu-id="09d57-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09d57-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09d57-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="09d57-106">[in] Einen Schnittstellenzeiger auf ein `IStream` mit der Assembly, die ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="09d57-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="09d57-107">[in] Für eine zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="09d57-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="09d57-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, den die aktuelle Version der common Language Runtime (CLR) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="09d57-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="09d57-109">[in] Ein Zeiger auf ein [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) Objekt, das Assembly-Identitätsdaten für die Assemblys aus ausgeschlossen werden sollen enthält `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="09d57-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="09d57-110">[out] Ein Zeiger auf die Adresse des ein `ICLRReferenceAssemblyEnum` -Objekt, das Assembly für die Assemblys, auf die verwiesen wird von der Assembly im enthält `pStream`, mit Ausnahme der Assemblys in `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="09d57-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09d57-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="09d57-111">Return Value</span></span>  
  
|<span data-ttu-id="09d57-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09d57-112">HRESULT</span></span>|<span data-ttu-id="09d57-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d57-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09d57-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="09d57-114">S_OK</span></span>|<span data-ttu-id="09d57-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="09d57-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="09d57-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09d57-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09d57-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="09d57-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09d57-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09d57-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09d57-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="09d57-119">The call timed out.</span></span>|  
|<span data-ttu-id="09d57-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09d57-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09d57-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="09d57-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09d57-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09d57-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09d57-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="09d57-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09d57-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09d57-124">E_FAIL</span></span>|<span data-ttu-id="09d57-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="09d57-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09d57-126">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="09d57-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09d57-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="09d57-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09d57-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09d57-128">Remarks</span></span>  
 <span data-ttu-id="09d57-129">Der Aufrufer kann auch einen Satz bekannter Assemblyverweise in der zurückgegebenen Liste ausschließen.</span><span class="sxs-lookup"><span data-stu-id="09d57-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="09d57-130">Dieser Satz wird definiert, indem `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="09d57-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d57-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09d57-131">Requirements</span></span>  
 <span data-ttu-id="09d57-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09d57-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d57-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09d57-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09d57-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="09d57-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09d57-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d57-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d57-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09d57-136">See also</span></span>

- [<span data-ttu-id="09d57-137">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09d57-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="09d57-138">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09d57-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="09d57-139">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09d57-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
