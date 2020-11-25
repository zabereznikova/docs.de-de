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
ms.openlocfilehash: a2bf0335f8d75c7dbd1a651afdb54da8c7be2460
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731619"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="bfd46-102">IMetaDataAssemblyImport::FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="bfd46-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>

<span data-ttu-id="bfd46-103">Ruft ein Array von Assemblys mit dem angegebenen `szAssemblyName` Parameter ab und verwendet dabei die Standardregeln, die vom Common Language Runtime (CLR) zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfd46-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfd46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfd46-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bfd46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfd46-105">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="bfd46-106">in Das Stammverzeichnis, in dem nach der angegebenen Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfd46-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="bfd46-107">Wenn dieser Wert auf festgelegt ist `null` , `FindAssembliesByName` sucht nur im globalen Assemblycache für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfd46-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="bfd46-108">in Eine Liste von durch Semikolons getrennten Unterverzeichnissen (z. b. "bin; BIN2") unter dem Stammverzeichnis, in dem nach der Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfd46-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="bfd46-109">Diese Verzeichnisse werden zusätzlich zu den in den standardmäßigen Prüfregeln angegebenen Verzeichnissen geprüft.</span><span class="sxs-lookup"><span data-stu-id="bfd46-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="bfd46-110">in Der Name der zu suchenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfd46-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="bfd46-111">Das Format dieser Zeichenfolge wird auf der Klassen Verweisseite für definiert <xref:System.Reflection.AssemblyName> .</span><span class="sxs-lookup"><span data-stu-id="bfd46-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="bfd46-112">in Ein Array vom Typ [IUnknown](/cpp/atl/iunknown) , in dem die Schnittstellen Zeiger abgelegt werden sollen `IMetadataAssemblyImport` .</span><span class="sxs-lookup"><span data-stu-id="bfd46-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="bfd46-113">vorgenommen Die maximale Anzahl von Schnittstellen Zeigern, die in platziert werden können `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="bfd46-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="bfd46-114">vorgenommen Die Anzahl der zurückgegebenen Schnittstellen Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bfd46-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="bfd46-115">Das heißt, die Anzahl der Schnittstellen Zeiger, die tatsächlich in platziert werden `ppIUnk` .</span><span class="sxs-lookup"><span data-stu-id="bfd46-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfd46-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bfd46-116">Return Value</span></span>  
  
|<span data-ttu-id="bfd46-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfd46-117">HRESULT</span></span>|<span data-ttu-id="bfd46-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bfd46-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="bfd46-119">`FindAssembliesByName` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bfd46-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="bfd46-120">Es sind keine Assemblys vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bfd46-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfd46-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfd46-121">Remarks</span></span>  

 <span data-ttu-id="bfd46-122">Bei Angabe eines Assemblynamens findet die- `FindAssembliesByName` Methode die Assembly, indem Sie den Standardregeln zum Auflösen von Assemblyverweisen folgt.</span><span class="sxs-lookup"><span data-stu-id="bfd46-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="bfd46-123">(Weitere Informationen finden Sie unter [so](../../deployment/how-the-runtime-locates-assemblies.md)sucht Common Language Runtime nach Assemblys.) ermöglicht dem Aufrufer, `FindAssembliesByName` verschiedene Aspekte des Assemblyresolverkontexts zu konfigurieren, z. b. Anwendungs Basis und privater Suchpfad.</span><span class="sxs-lookup"><span data-stu-id="bfd46-123">(For more information, see [How the Runtime Locates Assemblies](../../deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="bfd46-124">Die- `FindAssembliesByName` Methode erfordert, dass die CLR im Prozess initialisiert wird, um die Assemblyauflösungs-Logik aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bfd46-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="bfd46-125">Daher müssen Sie vor dem Aufrufen von [CoInitializeEE](../hosting/coinitializeee-function.md) (Übergabe COINITEE_DEFAULT) aufrufen `FindAssembliesByName` und dann mit einem Aufruf von " [zählinitializecor](../hosting/couninitializecor-function.md)" folgen.</span><span class="sxs-lookup"><span data-stu-id="bfd46-125">Therefore, you must call [CoInitializeEE](../hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="bfd46-126">`FindAssembliesByName` Gibt einen [IMetaDataImport](imetadataimport-interface.md) -Zeiger auf die Datei zurück, die das Assemblymanifest für den weiter gegebenen Assemblynamen enthält.</span><span class="sxs-lookup"><span data-stu-id="bfd46-126">`FindAssembliesByName` returns an [IMetaDataImport](imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="bfd46-127">Wenn der angegebene Assemblyname nicht vollständig angegeben ist (z. b. wenn er keine Version enthält), werden möglicherweise mehrere Assemblys zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="bfd46-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="bfd46-128">`FindAssembliesByName` wird häufig von einem Compiler verwendet, der versucht, eine referenzierte Assembly zur Kompilierzeit zu finden.</span><span class="sxs-lookup"><span data-stu-id="bfd46-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfd46-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bfd46-129">Requirements</span></span>  

 <span data-ttu-id="bfd46-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfd46-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfd46-131">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bfd46-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bfd46-132">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfd46-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bfd46-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfd46-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd46-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd46-134">See also</span></span>

- [<span data-ttu-id="bfd46-135">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="bfd46-135">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="bfd46-136">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bfd46-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
