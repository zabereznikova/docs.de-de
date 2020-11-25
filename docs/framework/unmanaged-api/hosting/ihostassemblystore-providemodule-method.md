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
ms.openlocfilehash: 35805d277774e1de03bb7dee1740a2e1305a97c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732995"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="31ce8-102">IHostAssemblyStore::ProvideModule-Methode</span><span class="sxs-lookup"><span data-stu-id="31ce8-102">IHostAssemblyStore::ProvideModule Method</span></span>

<span data-ttu-id="31ce8-103">Löst ein Modul in einer Assembly oder einer verknüpften (aber nicht eingebetteten) Ressourcen Datei auf.</span><span class="sxs-lookup"><span data-stu-id="31ce8-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ce8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31ce8-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ce8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31ce8-105">Parameters</span></span>  

 `pBindInfo`  
 <span data-ttu-id="31ce8-106">in Ein Zeiger auf eine [ModuleBindInfo](modulebindinfo-structure.md) -Instanz, die die, die <xref:System.AppDomain> Assembly und den Modulnamen des angeforderten Moduls beschreibt.</span><span class="sxs-lookup"><span data-stu-id="31ce8-106">[in] A pointer to a [ModuleBindInfo](modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="31ce8-107">vorgenommen Ein Zeiger auf einen eindeutigen Bezeichner für das, `IStream` das das geladene Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="31ce8-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="31ce8-108">vorgenommen Ein Zeiger auf die Adresse eines `IStream` Objekts, das das PE-Bild (portable ausführbare Datei) enthält, das geladen werden soll, oder NULL, wenn das Modul nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="31ce8-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="31ce8-109">vorgenommen Ein Zeiger auf die Adresse eines `IStream` Objekts, das die Programm Debuginformationen (PDB) für das angeforderte Modul enthält, oder NULL, wenn die PDB-Datei nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="31ce8-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31ce8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31ce8-110">Return Value</span></span>  
  
|<span data-ttu-id="31ce8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31ce8-111">HRESULT</span></span>|<span data-ttu-id="31ce8-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="31ce8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31ce8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="31ce8-113">S_OK</span></span>|<span data-ttu-id="31ce8-114">`ProvideModule` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31ce8-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="31ce8-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="31ce8-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="31ce8-116">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="31ce8-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="31ce8-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="31ce8-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="31ce8-118">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="31ce8-118">The call timed out.</span></span>|  
|<span data-ttu-id="31ce8-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="31ce8-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="31ce8-120">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="31ce8-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="31ce8-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="31ce8-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="31ce8-122">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="31ce8-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="31ce8-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="31ce8-123">E_FAIL</span></span>|<span data-ttu-id="31ce8-124">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="31ce8-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="31ce8-125">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="31ce8-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="31ce8-126">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="31ce8-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="31ce8-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="31ce8-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="31ce8-128">Die angeforderte Assembly oder verknüpfte Ressource konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="31ce8-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="31ce8-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="31ce8-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="31ce8-130">`pdwModuleId` ist nicht groß genug, um den Bezeichner zu enthalten, der vom Host zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="31ce8-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31ce8-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31ce8-131">Remarks</span></span>  

 <span data-ttu-id="31ce8-132">Der für zurückgegebene Identitäts Wert `pdwModuleId` wird vom Host angegeben.</span><span class="sxs-lookup"><span data-stu-id="31ce8-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="31ce8-133">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="31ce8-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="31ce8-134">Die CLR verwendet diesen Wert als eindeutigen Bezeichner für den zugeordneten Stream.</span><span class="sxs-lookup"><span data-stu-id="31ce8-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="31ce8-135">Er überprüft jeden Wert anhand der Werte, die `pAssemblyId` von Aufrufen von [ProvideAssembly](ihostassemblystore-provideassembly-method.md) zurückgegeben werden, und `pdwModuleId` mit den Werten, die von anderen Aufrufen von zurückgegeben werden `ProvideModule` .</span><span class="sxs-lookup"><span data-stu-id="31ce8-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="31ce8-136">Wenn der Host denselben Bezeichnerwert für einen anderen zurückgibt `IStream` , überprüft die CLR, ob der Inhalt dieses Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="31ce8-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="31ce8-137">Wenn dies der Fall ist, lädt die CLR die vorhandene Kopie des Bilds, anstatt eine neue zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="31ce8-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="31ce8-138">Daher muss sich der Bezeichner auch nicht mit den von zurückgegebenen Assemblybezeichnern überschneiden `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="31ce8-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31ce8-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="31ce8-139">Requirements</span></span>  

 <span data-ttu-id="31ce8-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31ce8-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ce8-141">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="31ce8-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="31ce8-142">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="31ce8-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="31ce8-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ce8-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ce8-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31ce8-144">See also</span></span>

- [<span data-ttu-id="31ce8-145">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31ce8-145">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="31ce8-146">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31ce8-146">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="31ce8-147">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31ce8-147">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
