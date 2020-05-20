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
ms.openlocfilehash: 4f06dd7b85446eec986055418d2cf558b9b5bd7a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615929"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="e6947-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream-Methode</span><span class="sxs-lookup"><span data-stu-id="e6947-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="e6947-103">Ruft einen Zeiger auf ein [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) -Objekt ab, das Assemblyidentitätsdaten für die Assemblys enthält, auf die von der Assembly im angegebenen Stream verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e6947-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6947-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6947-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6947-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6947-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="e6947-106">in Ein Schnittstellen Zeiger auf eine, `IStream` die die auszuwertende Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="e6947-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e6947-107">in Wird für zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e6947-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="e6947-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, der von der aktuellen Version des Common Language Runtime (CLR) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e6947-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="e6947-109">in Ein Zeiger auf ein [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) -Objekt, das Assemblyidentitätsdaten für die Assemblys enthält, die von ausgeschlossen werden sollen `ppReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="e6947-109">[in] A pointer to an [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="e6947-110">vorgenommen Ein Zeiger auf die Adresse eines `ICLRReferenceAssemblyEnum` Objekts, das Assemblyidentitätsdaten für die Assemblys enthält, auf die die Assembly in verweist `pStream` , ausgenommen der Assemblys in `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="e6947-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6947-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e6947-111">Return Value</span></span>  
  
|<span data-ttu-id="e6947-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6947-112">HRESULT</span></span>|<span data-ttu-id="e6947-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e6947-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6947-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6947-114">S_OK</span></span>|<span data-ttu-id="e6947-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e6947-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="e6947-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6947-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6947-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="e6947-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6947-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6947-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6947-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="e6947-119">The call timed out.</span></span>|  
|<span data-ttu-id="e6947-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6947-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6947-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e6947-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6947-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6947-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6947-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="e6947-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6947-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6947-124">E_FAIL</span></span>|<span data-ttu-id="e6947-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e6947-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6947-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="e6947-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6947-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e6947-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6947-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6947-128">Remarks</span></span>  
 <span data-ttu-id="e6947-129">Der Aufrufer kann eine Reihe bekannter Assemblyverweise aus der zurückgegebenen Liste ausschließen.</span><span class="sxs-lookup"><span data-stu-id="e6947-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="e6947-130">Diese Gruppe wird von definiert `pExcludeAssembliesList` .</span><span class="sxs-lookup"><span data-stu-id="e6947-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6947-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6947-131">Requirements</span></span>  
 <span data-ttu-id="e6947-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6947-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6947-133">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e6947-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6947-134">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6947-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6947-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6947-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6947-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6947-136">See also</span></span>

- [<span data-ttu-id="e6947-137">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6947-137">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="e6947-138">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6947-138">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="e6947-139">ICLRReferenceAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6947-139">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
