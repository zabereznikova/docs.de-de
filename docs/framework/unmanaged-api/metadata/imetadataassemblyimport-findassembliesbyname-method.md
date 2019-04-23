---
title: IMetaDataAssemblyImport::FindAssembliesByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b388dae0f109ff366f83c92de99b00b80bcc01a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108718"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="c14c5-102">IMetaDataAssemblyImport::FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c14c5-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="c14c5-103">Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameters unter Verwendung von die Standardregeln, die von der common Language Runtime (CLR) zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="c14c5-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c14c5-104">Syntax</span></span>  
  
```  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c14c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c14c5-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="c14c5-106">[in] Das Stammverzeichnis, in denen für die angegebene Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c14c5-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="c14c5-107">Wenn dieser Wert, um festgelegt ist `null`, `FindAssembliesByName` wird nur im globalen Assemblycache suchen Sie nach der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c14c5-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="c14c5-108">[in] Eine Liste von durch Semikolons getrennte Unterverzeichnisse (z. B. "Bin; bin2"), unter dem Stammverzeichnis, in dem für die Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c14c5-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="c14c5-109">Diese Verzeichnisse sind zusätzlich zu den in der Überprüfung der Regeln angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c14c5-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="c14c5-110">[in] Der Name der Assembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c14c5-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="c14c5-111">Das Format dieser Zeichenfolge wird definiert, in der Klasse Referenzseite für <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="c14c5-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="c14c5-112">[in] Ein Array vom Typ [IUnknown](/cpp/atl/iunknown) zum Speichern der `IMetadataAssemblyImport` Schnittstellenzeigern.</span><span class="sxs-lookup"><span data-stu-id="c14c5-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c14c5-113">[out] Die maximale Anzahl der Schnittstellenzeiger, der in eingefügt werden können `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="c14c5-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="c14c5-114">[out] Die Anzahl der Schnittstellenzeiger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c14c5-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="c14c5-115">D. h. die Anzahl der Schnittstellenzeiger, die tatsächlich `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="c14c5-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c14c5-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c14c5-116">Return Value</span></span>  
  
|<span data-ttu-id="c14c5-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c14c5-117">HRESULT</span></span>|<span data-ttu-id="c14c5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c14c5-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c14c5-119">`FindAssembliesByName` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c14c5-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c14c5-120">Es sind keine Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c14c5-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c14c5-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c14c5-121">Remarks</span></span>  
 <span data-ttu-id="c14c5-122">Erhält den Namen einer Assembly die `FindAssembliesByName` Methode sucht die Assembly, indem Sie die folgenden Standardregeln für das Auflösen von Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="c14c5-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="c14c5-123">(Weitere Informationen finden Sie unter [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht dem Aufrufer, die verschiedene Aspekte der Kontext des Assembly-Auflösung, z. B. Basisklassen und privaten Suchpfad konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c14c5-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="c14c5-124">Die `FindAssembliesByName` Methode muss die CLR im Prozess initialisiert werden, um die Logik zur Assembly aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c14c5-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="c14c5-125">Aus diesem Grund müssen Sie aufrufen [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT übergeben) vor dem Aufruf `FindAssembliesByName`, und befolgen Sie dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="c14c5-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="c14c5-126">`FindAssembliesByName` Gibt eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Zeiger auf die Datei mit dem Assemblymanifest für die Namen der Assembly, die übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c14c5-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="c14c5-127">Wenn der angegebene Assemblyname (z. B., wenn eine Version nicht enthalten ist) nicht vollständig angegeben wurde, können mehrere Assemblys zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c14c5-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="c14c5-128">`FindAssembliesByName` wird häufig durch einen Compiler verwendet, die versucht, eine referenzierte Assembly zum Zeitpunkt der Kompilierung zu finden.</span><span class="sxs-lookup"><span data-stu-id="c14c5-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14c5-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c14c5-129">Requirements</span></span>  
 <span data-ttu-id="c14c5-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c14c5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14c5-131">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c14c5-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c14c5-132">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c14c5-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c14c5-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14c5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14c5-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c14c5-134">See also</span></span>

- [<span data-ttu-id="c14c5-135">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="c14c5-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="c14c5-136">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c14c5-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
