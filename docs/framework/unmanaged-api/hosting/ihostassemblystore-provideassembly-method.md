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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124485"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="84433-102">IHostAssemblyStore::ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="84433-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="84433-103">Ruft einen Verweis auf eine Assembly ab, auf die von [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die von [IHostAssemblyManager:: getnonhoststoreassemblys](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wird, nicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="84433-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="84433-104">Der Common Language Runtime (CLR) ruft `ProvideAssembly` für jede Assembly auf, die nicht in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="84433-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84433-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="84433-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84433-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="84433-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="84433-107">in Ein Zeiger auf eine [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) -Instanz, die der Host verwendet, um bestimmte Bindungseigenschaften zu bestimmen, einschließlich der Anwesenheit oder Abwesenheit jeglicher Versions Richtlinien und der Assembly, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="84433-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="84433-108">vorgenommen Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für dieses `IStream`.</span><span class="sxs-lookup"><span data-stu-id="84433-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="84433-109">vorgenommen Ein Zeiger auf Host spezifische Daten, die verwendet werden, um den Beweis der angeforderten Assembly zu bestimmen, ohne dass ein Platt Form Aufruf erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="84433-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="84433-110">`pHostContext` entspricht der <xref:System.Reflection.Assembly.HostContext%2A>-Eigenschaft der verwalteten <xref:System.Reflection.Assembly>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="84433-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="84433-111">vorgenommen Ein Zeiger auf die Adresse einer `IStream`, die das zu ladende portable ausführbare Image (PE) enthält, oder NULL, wenn die Assembly nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="84433-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="84433-112">vorgenommen Ein Zeiger auf die Adresse einer `IStream`, die die Programm Debuginformationen (PDB) enthält, oder NULL, wenn die PDB-Datei nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="84433-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84433-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84433-113">Return Value</span></span>  
  
|<span data-ttu-id="84433-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84433-114">HRESULT</span></span>|<span data-ttu-id="84433-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84433-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84433-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="84433-116">S_OK</span></span>|<span data-ttu-id="84433-117">`ProvideAssembly` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84433-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="84433-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84433-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84433-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="84433-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84433-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84433-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84433-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="84433-121">The call timed out.</span></span>|  
|<span data-ttu-id="84433-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84433-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84433-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="84433-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84433-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84433-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84433-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="84433-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84433-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84433-126">E_FAIL</span></span>|<span data-ttu-id="84433-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="84433-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84433-128">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84433-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84433-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="84433-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84433-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="84433-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="84433-131">Die angeforderte Assembly konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="84433-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="84433-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="84433-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="84433-133">Die durch `pAssemblyId` angegebene Puffergröße ist nicht groß genug zum Speichern des Bezeichners, den der Host zurückgeben möchte.</span><span class="sxs-lookup"><span data-stu-id="84433-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84433-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84433-134">Remarks</span></span>  
 <span data-ttu-id="84433-135">Der für `pAssemblyId` zurückgegebene Identitäts Wert wird vom Host angegeben.</span><span class="sxs-lookup"><span data-stu-id="84433-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="84433-136">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="84433-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="84433-137">Die CLR verwendet diesen Wert als eindeutigen Bezeichner für den Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="84433-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="84433-138">Jeder Wert wird anhand der Werte für `pAssemblyId` überprüft, die von anderen Aufrufen von `ProvideAssembly`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84433-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="84433-139">Wenn der Host denselben `pAssemblyId` Wert für einen anderen `IStream`zurückgibt, überprüft die CLR, ob der Inhalt dieses Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="84433-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="84433-140">Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie des Bilds, anstatt eine neue zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="84433-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84433-141">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84433-141">Requirements</span></span>  
 <span data-ttu-id="84433-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84433-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84433-143">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="84433-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84433-144">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84433-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84433-145">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84433-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84433-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84433-146">See also</span></span>

- [<span data-ttu-id="84433-147">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84433-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="84433-148">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84433-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="84433-149">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84433-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
