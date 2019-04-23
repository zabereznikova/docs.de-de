---
title: IHostAssemblyStore::ProvideModule-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078337"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="1d101-102">IHostAssemblyStore::ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="1d101-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="1d101-103">Löst eine Modul innerhalb einer Assembly oder ein verknüpftes (aber nicht auf ein eingebettetes) Ressourcendatei an.</span><span class="sxs-lookup"><span data-stu-id="1d101-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d101-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d101-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d101-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d101-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="1d101-106">[in] Ein Zeiger auf eine [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) Instanz, die des angeforderten Moduls beschreibt <xref:System.AppDomain>, Assembly und Modul mit Name.</span><span class="sxs-lookup"><span data-stu-id="1d101-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="1d101-107">[out] Ein Zeiger auf einen eindeutigen Bezeichner für die `IStream` , die das geladene Modul.</span><span class="sxs-lookup"><span data-stu-id="1d101-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="1d101-108">[out] Ein Zeiger auf die Adresse einer `IStream` Objekts, das enthält die Datei (portable Executable)-Image geladen werden, oder null, wenn das Modul nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1d101-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="1d101-109">[out] Ein Zeiger auf die Adresse einer `IStream` Objekts, das Programm (PDB) Debuginformationen für das angeforderte Modul enthält, oder null, wenn die PDB-Datei nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="1d101-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d101-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1d101-110">Return Value</span></span>  
  
|<span data-ttu-id="1d101-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d101-111">HRESULT</span></span>|<span data-ttu-id="1d101-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d101-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d101-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d101-113">S_OK</span></span>|<span data-ttu-id="1d101-114">`ProvideModule` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d101-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="1d101-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d101-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d101-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1d101-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d101-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d101-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d101-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1d101-118">The call timed out.</span></span>|  
|<span data-ttu-id="1d101-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d101-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d101-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="1d101-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d101-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d101-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d101-122">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="1d101-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d101-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d101-123">E_FAIL</span></span>|<span data-ttu-id="1d101-124">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1d101-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d101-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d101-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d101-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="1d101-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1d101-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="1d101-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="1d101-128">Die angeforderte Assembly oder eine verknüpfte Ressource konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1d101-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="1d101-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="1d101-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="1d101-130">`pdwModuleId` ist nicht groß genug ist, den Bezeichner enthält, den der Host zurückgeben möchte.</span><span class="sxs-lookup"><span data-stu-id="1d101-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d101-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d101-131">Remarks</span></span>  
 <span data-ttu-id="1d101-132">Der Identitätswert zurückgegeben wird, für die `pdwModuleId` vom Host angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1d101-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="1d101-133">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="1d101-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="1d101-134">Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den zugeordneten Stream.</span><span class="sxs-lookup"><span data-stu-id="1d101-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="1d101-135">Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die durch Aufrufe von [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) und mit den Werten für `pdwModuleId` zurückgegeben, die von anderen Aufrufen von `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="1d101-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="1d101-136">Wenn der Host den gleichen Bezeichnerwert für eine andere zurückgibt `IStream`, die CLR wird überprüft, ob der Inhalt des Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="1d101-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="1d101-137">Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Bildes statt ein neues zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="1d101-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="1d101-138">Aus diesem Grund der Bezeichner muss auch nicht überschneiden sich mit den Assemblybezeichnern, die von zurückgegeben `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="1d101-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d101-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d101-139">Requirements</span></span>  
 <span data-ttu-id="1d101-140">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d101-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d101-141">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d101-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d101-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d101-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d101-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d101-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d101-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d101-144">See also</span></span>

- [<span data-ttu-id="1d101-145">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d101-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="1d101-146">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d101-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="1d101-147">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d101-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
