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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177798"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="9e466-102">IMetaDataAssemblyImport::FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="9e466-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="9e466-103">Ruft ein Array von `szAssemblyName` Assemblys mit dem angegebenen Parameter ab, wobei die Standardregeln verwendet werden, die von der Common Language Runtime (CLR) zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9e466-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e466-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e466-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,
    [in]  LPCWSTR     szPrivateBin,
    [in]  LPCWSTR     szAssemblyName,
    [out] IUnknown    *ppIUnk[],
    [in]  ULONG       cMax,
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e466-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9e466-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="9e466-106">[in] Das Stammverzeichnis, in dem nach der angegebenen Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e466-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="9e466-107">Wenn dieser Wert `null`auf `FindAssembliesByName` festgelegt ist, wird nur im globalen Assemblycache für die Assembly gesucht.</span><span class="sxs-lookup"><span data-stu-id="9e466-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="9e466-108">[in] Eine Liste von Subverzeichnissen, die durch Semikolons getrennt sind (z. B. "bin;bin2"), unter dem Stammverzeichnis, in dem nach der Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9e466-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="9e466-109">Diese Verzeichnisse werden zusätzlich zu den in den Standardprüfregeln angegebenen Prüfregeln untersucht.</span><span class="sxs-lookup"><span data-stu-id="9e466-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="9e466-110">[in] Der Name der zu suchenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="9e466-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="9e466-111">Das Format dieser Zeichenfolge ist in der <xref:System.Reflection.AssemblyName>Klassenreferenzseite für definiert.</span><span class="sxs-lookup"><span data-stu-id="9e466-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="9e466-112">[in] Ein Array vom Typ [IUnknown,](/cpp/atl/iunknown) in dem die `IMetadataAssemblyImport` Schnittstellenzeiger gesetzt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9e466-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9e466-113">[out] Die maximale Anzahl von Schnittstellenzeigern, `ppIUnk`die in platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="9e466-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="9e466-114">[out] Die Anzahl der zurückgegebenen Schnittstellenzeiger.</span><span class="sxs-lookup"><span data-stu-id="9e466-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="9e466-115">Das heißt, die Anzahl der Schnittstellenzeiger, die tatsächlich in `ppIUnk`platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="9e466-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e466-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9e466-116">Return Value</span></span>  
  
|<span data-ttu-id="9e466-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e466-117">HRESULT</span></span>|<span data-ttu-id="9e466-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e466-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9e466-119">`FindAssembliesByName`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9e466-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9e466-120">Es sind keine Assemblys vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9e466-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e466-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9e466-121">Remarks</span></span>  
 <span data-ttu-id="9e466-122">Bei einem Assemblynamen `FindAssembliesByName` findet die Methode die Assembly, indem sie den Standardregeln zum Auflösen von Assemblyverweisen folgt.</span><span class="sxs-lookup"><span data-stu-id="9e466-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="9e466-123">(Weitere Informationen finden Sie unter [So findet die Laufzeit Assemblys](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` ermöglicht es dem Aufrufer, verschiedene Aspekte des Assembly-Resolver-Kontexts zu konfigurieren, z. B. Anwendungsbasis und privater Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="9e466-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="9e466-124">Die `FindAssembliesByName` Methode erfordert, dass die CLR im Prozess initialisiert wird, um die Assemblyauflösungslogik aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="9e466-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="9e466-125">Daher müssen Sie [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (übergeben COINITEE_DEFAULT) aufrufen, bevor Sie aufrufen, `FindAssembliesByName`und dann mit einem Aufruf von [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)folgen.</span><span class="sxs-lookup"><span data-stu-id="9e466-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="9e466-126">`FindAssembliesByName`gibt einen [IMetaDataImport-Zeiger](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) auf die Datei zurück, die das Assemblymanifest für den übergebenen Assemblynamen enthält.</span><span class="sxs-lookup"><span data-stu-id="9e466-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="9e466-127">Wenn der angegebene Assemblyname nicht vollständig angegeben ist (z. B. wenn er keine Version enthält), können mehrere Assemblys zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9e466-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="9e466-128">`FindAssembliesByName`wird häufig von einem Compiler verwendet, der versucht, eine Assembly zu finden, auf die zur Kompilierungszeit verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9e466-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e466-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9e466-129">Requirements</span></span>  
 <span data-ttu-id="9e466-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e466-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e466-131">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9e466-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e466-132">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9e466-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e466-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e466-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e466-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e466-134">See also</span></span>

- [<span data-ttu-id="9e466-135">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="9e466-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="9e466-136">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e466-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
