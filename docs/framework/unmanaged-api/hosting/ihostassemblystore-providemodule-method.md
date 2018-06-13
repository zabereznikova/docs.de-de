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
ms.openlocfilehash: 8b604e1d7fc3d3c8adf7d95bd95843bc0110dbc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440017"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="0d296-102">IHostAssemblyStore::ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="0d296-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="0d296-103">Löst eine Modul innerhalb einer Assembly oder einer verknüpften (jedoch nicht eingebetteten) Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="0d296-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d296-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d296-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d296-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="0d296-106">[in] Ein Zeiger auf eine [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) Instanz, die des angeforderten Moduls beschreibt <xref:System.AppDomain>, Assembly und der Name des Moduls.</span><span class="sxs-lookup"><span data-stu-id="0d296-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="0d296-107">[out] Ein Zeiger auf einen eindeutigen Bezeichner für die `IStream` , enthält das geladene Modul.</span><span class="sxs-lookup"><span data-stu-id="0d296-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="0d296-108">[out] Ein Zeiger auf die Adresse des ein `IStream` Objekts, das enthält die Datei (portable Executable)-Image geladen werden, oder null, wenn das Modul nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="0d296-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="0d296-109">[out] Ein Zeiger auf die Adresse des ein `IStream` Objekts, das Programm (PDB) Debuginformationen für das angeforderte Modul enthält, oder null, wenn die PDB-Datei nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="0d296-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d296-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d296-110">Return Value</span></span>  
  
|<span data-ttu-id="0d296-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d296-111">HRESULT</span></span>|<span data-ttu-id="0d296-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d296-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d296-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d296-113">S_OK</span></span>|<span data-ttu-id="0d296-114">`ProvideModule` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0d296-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="0d296-115">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="0d296-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d296-116">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="0d296-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d296-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d296-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d296-118">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0d296-118">The call timed out.</span></span>|  
|<span data-ttu-id="0d296-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d296-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d296-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="0d296-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d296-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d296-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d296-122">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="0d296-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d296-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d296-123">E_FAIL</span></span>|<span data-ttu-id="0d296-124">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0d296-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d296-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="0d296-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d296-126">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0d296-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0d296-127">COR_E_FILENOTFOUND (0 X 80070002)</span><span class="sxs-lookup"><span data-stu-id="0d296-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="0d296-128">Die angeforderte Assembly oder verknüpfte Ressource konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0d296-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="0d296-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0d296-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0d296-130">`pdwModuleId` ist nicht groß genug für den Bezeichner enthalten, den möchte, dass der Host zurück.</span><span class="sxs-lookup"><span data-stu-id="0d296-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d296-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d296-131">Remarks</span></span>  
 <span data-ttu-id="0d296-132">Der Identitätswert zurückgegeben wird, für die `pdwModuleId` wird vom Host angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d296-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="0d296-133">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0d296-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="0d296-134">Die CLR verwendet diesen Wert als eindeutiger Bezeichner für den zugeordneten Stream.</span><span class="sxs-lookup"><span data-stu-id="0d296-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="0d296-135">Er überprüft jeden Wert mit den Werten für `pAssemblyId` zurückgegeben, die durch Aufrufe von [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) und mit den Werten für `pdwModuleId` zurückgegeben, die von anderen Aufrufen von `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="0d296-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="0d296-136">Wenn der Host den gleichen Bezeichnerwert für eine andere zurückgibt `IStream`, die CLR überprüft, ob der Inhalt dieses Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="0d296-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="0d296-137">Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Abbilds statt ein neues Konto zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0d296-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="0d296-138">Aus diesem Grund der Bezeichner muss auch nicht überschneiden sich mit der Assembly-IDs, die von zurückgegeben `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="0d296-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d296-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d296-139">Requirements</span></span>  
 <span data-ttu-id="0d296-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d296-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d296-141">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d296-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d296-142">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0d296-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d296-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d296-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d296-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d296-144">See Also</span></span>  
 [<span data-ttu-id="0d296-145">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d296-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="0d296-146">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d296-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="0d296-147">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d296-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
