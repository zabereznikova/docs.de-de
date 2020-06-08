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
ms.openlocfilehash: 162def0d703ea81efc3df3ea5ee08b58e34822e6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501572"
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="16420-102">IHostAssemblyStore::ProvideAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="16420-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="16420-103">Ruft einen Verweis auf eine Assembly ab, auf die von [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) , die von [IHostAssemblyManager:: getnonhoststoreassemblys](ihostassemblymanager-getnonhoststoreassemblies-method.md)zurückgegeben wird, nicht verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="16420-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="16420-104">Der Common Language Runtime (CLR) ruft `ProvideAssembly` für jede Assembly auf, die nicht in der Liste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="16420-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16420-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="16420-105">Syntax</span></span>  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16420-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="16420-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="16420-107">in Ein Zeiger auf eine [AssemblyBindInfo](assemblybindinfo-structure.md) -Instanz, die der Host verwendet, um bestimmte Bindungseigenschaften zu bestimmen, einschließlich der Anwesenheit oder Abwesenheit jeglicher Versions Richtlinien und der Assembly, an die die Bindung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="16420-107">[in] A pointer to an [AssemblyBindInfo](assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="16420-108">vorgenommen Ein Zeiger auf einen eindeutigen Bezeichner für die angeforderte Assembly für diesen `IStream` .</span><span class="sxs-lookup"><span data-stu-id="16420-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="16420-109">vorgenommen Ein Zeiger auf Host spezifische Daten, die verwendet werden, um den Beweis der angeforderten Assembly zu bestimmen, ohne dass ein Platt Form Aufruf erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="16420-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="16420-110">`pHostContext`entspricht der- <xref:System.Reflection.Assembly.HostContext%2A> Eigenschaft der verwalteten- <xref:System.Reflection.Assembly> Klasse.</span><span class="sxs-lookup"><span data-stu-id="16420-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="16420-111">vorgenommen Ein Zeiger auf die Adresse eines, der `IStream` das zu ladende portable ausführbare Image (PE) enthält, oder NULL, wenn die Assembly nicht gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="16420-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="16420-112">vorgenommen Ein Zeiger auf die Adresse eines, der `IStream` die Programm Debuginformationen (PDB) enthält, oder NULL, wenn die PDB-Datei nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="16420-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16420-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16420-113">Return Value</span></span>  
  
|<span data-ttu-id="16420-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16420-114">HRESULT</span></span>|<span data-ttu-id="16420-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16420-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16420-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="16420-116">S_OK</span></span>|<span data-ttu-id="16420-117">`ProvideAssembly`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="16420-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="16420-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16420-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16420-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="16420-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16420-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16420-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16420-121">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="16420-121">The call timed out.</span></span>|  
|<span data-ttu-id="16420-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16420-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16420-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="16420-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16420-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16420-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16420-125">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="16420-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16420-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16420-126">E_FAIL</span></span>|<span data-ttu-id="16420-127">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="16420-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16420-128">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="16420-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16420-129">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="16420-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="16420-130">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="16420-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="16420-131">Die angeforderte Assembly konnte nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="16420-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="16420-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="16420-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="16420-133">Die von angegebene Puffergröße `pAssemblyId` ist nicht groß genug zum Speichern des Bezeichners, den der Host zurückgeben möchte.</span><span class="sxs-lookup"><span data-stu-id="16420-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16420-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="16420-134">Remarks</span></span>  
 <span data-ttu-id="16420-135">Der für zurückgegebene Identitäts Wert `pAssemblyId` wird vom Host angegeben.</span><span class="sxs-lookup"><span data-stu-id="16420-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="16420-136">Bezeichner müssen innerhalb der Lebensdauer eines Prozesses eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="16420-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="16420-137">Die CLR verwendet diesen Wert als eindeutigen Bezeichner für den Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="16420-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="16420-138">Jeder Wert wird anhand der Werte für überprüft `pAssemblyId` , die von anderen Aufrufen von zurückgegeben werden `ProvideAssembly` .</span><span class="sxs-lookup"><span data-stu-id="16420-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="16420-139">Wenn der Host denselben `pAssemblyId` Wert für einen anderen zurückgibt `IStream` , überprüft die CLR, ob der Inhalt dieses Streams bereits zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="16420-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="16420-140">Wenn dies der Fall ist, lädt die Laufzeit die vorhandene Kopie des Bilds, anstatt eine neue zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="16420-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16420-141">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="16420-141">Requirements</span></span>  
 <span data-ttu-id="16420-142">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16420-142">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16420-143">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="16420-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16420-144">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="16420-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16420-145">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16420-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16420-146">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="16420-146">See also</span></span>

- [<span data-ttu-id="16420-147">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16420-147">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="16420-148">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16420-148">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="16420-149">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="16420-149">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
