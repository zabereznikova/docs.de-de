---
title: IHostAssemblyStore::ProvideAssembly-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8491852ea1fd9791de761d848b774480f4b461
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550291"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="f7d60-102">IHostAssemblyStore::ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f7d60-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="f7d60-103">Ruft einen Verweis auf eine Assembly, die nicht verwiesen wird die [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) von zurückgegebene [IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="f7d60-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="f7d60-104">Ruft die common Language Runtime (CLR) `ProvideAssembly` für jede Assembly, die nicht in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f7d60-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d60-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7d60-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7d60-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7d60-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="f7d60-107">[in] Ein Zeiger auf ein [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) -Instanz, die vom Host verwendet, um bestimmte Bindungsmerkmale, einschließlich das Vorhandensein oder fehlen, versionsverwaltung, Richtlinien zu ermitteln und die Assembly zum Binden an.</span><span class="sxs-lookup"><span data-stu-id="f7d60-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="f7d60-108">[out] Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für diese `IStream`.</span><span class="sxs-lookup"><span data-stu-id="f7d60-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="f7d60-109">[out] Ein Zeiger auf hostspezifische Daten an, die verwendet wird, um zu bestimmen, die Beweise für die angeforderte Assembly ohne die Notwendigkeit einer Plattform Plattformaufrufs.</span><span class="sxs-lookup"><span data-stu-id="f7d60-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="f7d60-110">`pHostContext` entspricht der <xref:System.Reflection.Assembly.HostContext%2A> Eigenschaft der verwalteten <xref:System.Reflection.Assembly> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f7d60-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="f7d60-111">[out] Ein Zeiger auf die Adresse einer `IStream` , enthält das PE (portable Executable)-Image geladen werden, oder null, wenn die Assembly nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="f7d60-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="f7d60-112">[out] Ein Zeiger auf die Adresse einer `IStream` , enthält die Programm-Debuginformationen (PDB) oder Null, wenn die PDB-Datei nicht gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="f7d60-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7d60-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7d60-113">Return Value</span></span>  
  
|<span data-ttu-id="f7d60-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f7d60-114">HRESULT</span></span>|<span data-ttu-id="f7d60-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7d60-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f7d60-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="f7d60-116">S_OK</span></span>|<span data-ttu-id="f7d60-117">`ProvideAssembly` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f7d60-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="f7d60-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f7d60-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f7d60-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f7d60-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f7d60-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f7d60-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f7d60-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f7d60-121">The call timed out.</span></span>|  
|<span data-ttu-id="f7d60-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f7d60-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f7d60-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="f7d60-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f7d60-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f7d60-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f7d60-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="f7d60-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f7d60-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f7d60-126">E_FAIL</span></span>|<span data-ttu-id="f7d60-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f7d60-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f7d60-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7d60-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f7d60-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f7d60-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f7d60-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="f7d60-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="f7d60-131">Die angeforderte Assembly konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f7d60-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="f7d60-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f7d60-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f7d60-133">Durch die angegebene Puffergröße `pAssemblyId` ist nicht groß genug für den Bezeichner, der der Host zurückgeben möchte.</span><span class="sxs-lookup"><span data-stu-id="f7d60-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7d60-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7d60-134">Remarks</span></span>  
 <span data-ttu-id="f7d60-135">Der Identitätswert zurückgegeben wird, für die `pAssemblyId` vom Host angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f7d60-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="f7d60-136">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f7d60-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="f7d60-137">Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den Stream.</span><span class="sxs-lookup"><span data-stu-id="f7d60-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="f7d60-138">Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die von anderen Aufrufen von `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="f7d60-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="f7d60-139">Wenn der Host die gleiche zurückgibt `pAssemblyId` Wert für eine andere `IStream`, die CLR wird überprüft, ob der Inhalt des Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="f7d60-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="f7d60-140">Wenn dies der Fall ist, lädt die Runtime die vorhandene Kopie des Bildes statt ein neues zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="f7d60-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d60-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7d60-141">Requirements</span></span>  
 <span data-ttu-id="f7d60-142">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7d60-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d60-143">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f7d60-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7d60-144">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f7d60-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d60-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d60-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d60-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7d60-146">See also</span></span>
- [<span data-ttu-id="f7d60-147">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7d60-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f7d60-148">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7d60-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="f7d60-149">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7d60-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
