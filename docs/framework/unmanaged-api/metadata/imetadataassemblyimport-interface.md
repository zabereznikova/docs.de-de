---
title: IMetaDataAssemblyImport-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714756"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="10fd2-102">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10fd2-102">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="10fd2-103">Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.</span><span class="sxs-lookup"><span data-stu-id="10fd2-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10fd2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="10fd2-104">Methods</span></span>  
  
|<span data-ttu-id="10fd2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-105">Method</span></span>|<span data-ttu-id="10fd2-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10fd2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10fd2-107">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="10fd2-108">Gibt das Handle für den angegebenen Enumerator frei.</span><span class="sxs-lookup"><span data-stu-id="10fd2-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="10fd2-109">EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="10fd2-110">Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die Token der Assemblys enthält, `mdAssemblyRef` auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="10fd2-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="10fd2-111">EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="10fd2-112">Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdExportedType` Token der com-Typen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="10fd2-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="10fd2-113">EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="10fd2-114">Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdFile` Token der Dateien enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="10fd2-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="10fd2-115">EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="10fd2-116">Ruft einen Schnittstellen Zeiger auf einen Enumerator ab, der die `mdManifestResource` Token der Ressourcen enthält, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="10fd2-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="10fd2-117">FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="10fd2-118">Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="10fd2-119">FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="10fd2-120">Ruft ein `mdExportedType` Token für den com-Typ mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="10fd2-121">FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="10fd2-122">Ruft ein `mdManifestResource` Token für die Ressource mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="10fd2-123">GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="10fd2-124">Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="10fd2-125">GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="10fd2-126">Ruft die Eigenschafts Einstellungen der angegebenen Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="10fd2-127">GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="10fd2-128">Ruft die Eigenschafts Einstellungen des angegebenen Tokens ab `mdAssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="10fd2-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="10fd2-129">GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="10fd2-130">Ruft die Eigenschafts Einstellungen des angegebenen COM-Typs ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="10fd2-131">GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="10fd2-132">Ruft die Eigenschafts Einstellungen der angegebenen Datei ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="10fd2-133">GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="10fd2-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="10fd2-134">Ruft die Eigenschafts Einstellungen der angegebenen Manifestressource ab.</span><span class="sxs-lookup"><span data-stu-id="10fd2-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10fd2-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10fd2-135">Requirements</span></span>  

 <span data-ttu-id="10fd2-136">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10fd2-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10fd2-137">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="10fd2-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10fd2-138">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="10fd2-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10fd2-139">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10fd2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10fd2-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10fd2-140">See also</span></span>

- [<span data-ttu-id="10fd2-141">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="10fd2-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="10fd2-142">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10fd2-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
