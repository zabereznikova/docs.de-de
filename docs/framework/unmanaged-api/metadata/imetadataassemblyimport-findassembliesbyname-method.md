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
ms.openlocfilehash: a6c7bf332d829a440fe216756f7a23ec1277e6c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449285"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="2be86-102">IMetaDataAssemblyImport::FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="2be86-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="2be86-103">Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameters unter Verwendung von Standardregeln, die von der common Language Runtime (CLR) zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="2be86-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2be86-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="2be86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2be86-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="2be86-106">[in] Das Stammverzeichnis, in denen für die angegebene Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2be86-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="2be86-107">Wenn dieser Wert, um festgelegt wird `null`, `FindAssembliesByName` sieht nur im globalen Assemblycache nach der Assembly.</span><span class="sxs-lookup"><span data-stu-id="2be86-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="2be86-108">[in] Eine Liste von durch Semikolons getrennte Unterverzeichnissen (z. B. "Bin; bin2"), unter dem Stammverzeichnis, in dem für die Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2be86-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="2be86-109">Diese Verzeichnisse werden zusätzlich zu den in der standardmäßigen Testregeln angegeben überprüft.</span><span class="sxs-lookup"><span data-stu-id="2be86-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="2be86-110">[in] Der Name der Assembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="2be86-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="2be86-111">Das Format dieser Zeichenfolge wird in der Klasse Referenzseite für definiert <xref:System.Reflection.AssemblyName>.</span><span class="sxs-lookup"><span data-stu-id="2be86-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2be86-112">[in] Ein Array vom Typ <<!--zzxref:IUnknown --> `IUnknown`> zum Speichern der `IMetadataAssemblyImport` -Schnittstellenzeigern.</span><span class="sxs-lookup"><span data-stu-id="2be86-112">[in] An array of type <<!--zzxref:IUnknown --> `IUnknown`> in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2be86-113">[out] Die maximale Anzahl von Schnittstellenzeigern, die in platziert werden können `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="2be86-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="2be86-114">[out] Die Anzahl der zurückgegebenen Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="2be86-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="2be86-115">D. h. die Anzahl der Schnittstellenzeiger, die tatsächlich `ppIUnk`.</span><span class="sxs-lookup"><span data-stu-id="2be86-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2be86-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2be86-116">Return Value</span></span>  
  
|<span data-ttu-id="2be86-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2be86-117">HRESULT</span></span>|<span data-ttu-id="2be86-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2be86-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2be86-119">`FindAssembliesByName` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2be86-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2be86-120">Es gibt keine Assemblys.</span><span class="sxs-lookup"><span data-stu-id="2be86-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2be86-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2be86-121">Remarks</span></span>  
 <span data-ttu-id="2be86-122">Erhält den Namen einer Assembly der `FindAssembliesByName` Methode sucht nach der Assembly gemäß die Standardregeln für das Auflösen von Assemblyverweisen.</span><span class="sxs-lookup"><span data-stu-id="2be86-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="2be86-123">(Weitere Informationen finden Sie unter [so sucht Common Language Runtime nach Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht dem Aufrufer, die verschiedene Aspekte des Kontexts Konfliktlöser Assembly z. B. die Anwendungsbasis und privater Suchpfad konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2be86-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="2be86-124">Die `FindAssembliesByName` Methode muss die CLR im Prozess initialisiert werden, um die Assemblyauflösungslogik aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2be86-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="2be86-125">Aus diesem Grund müssen Sie aufrufen [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT übergeben) vor dem Aufruf `FindAssembliesByName`, und befolgen Sie dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span><span class="sxs-lookup"><span data-stu-id="2be86-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="2be86-126">`FindAssembliesByName` Gibt eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Zeiger auf die Datei, die das Manifest der Name der Assembly enthält, die übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="2be86-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="2be86-127">Der Name der angegebenen Assembly (z. B., wenn eine Version nicht enthalten ist) nicht vollständig angegeben ist, können mehrere Assemblys zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2be86-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="2be86-128">`FindAssembliesByName` wird häufig von einem Compiler verwendet, die versucht, eine Assembly verwiesen wird, zum Zeitpunkt der Kompilierung gefunden.</span><span class="sxs-lookup"><span data-stu-id="2be86-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2be86-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2be86-129">Requirements</span></span>  
 <span data-ttu-id="2be86-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2be86-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2be86-131">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2be86-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2be86-132">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2be86-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2be86-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2be86-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be86-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2be86-134">See Also</span></span>  
 [<span data-ttu-id="2be86-135">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="2be86-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="2be86-136">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2be86-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
