---
title: IMetaDataAssemblyImport-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 992b588d16bc221f6b72044da40d09fbb6894511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="86c1b-102">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86c1b-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="86c1b-103">Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.</span><span class="sxs-lookup"><span data-stu-id="86c1b-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86c1b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="86c1b-104">Methods</span></span>  
  
|<span data-ttu-id="86c1b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-105">Method</span></span>|<span data-ttu-id="86c1b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86c1b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86c1b-107">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="86c1b-108">Gibt das Handle für den angegebenen Enumerator frei.</span><span class="sxs-lookup"><span data-stu-id="86c1b-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="86c1b-109">EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="86c1b-110">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdAssemblyRef` Token der Assemblys, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="86c1b-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="86c1b-111">EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="86c1b-112">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdExportedType` Token von der COM-Typen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="86c1b-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="86c1b-113">EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="86c1b-114">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdFile` Token der Dateien, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="86c1b-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="86c1b-115">EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="86c1b-116">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdManifestResource` Token, die Ressourcen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="86c1b-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="86c1b-117">FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="86c1b-118">Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="86c1b-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="86c1b-119">FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="86c1b-120">Ruft eine `mdExportedType` token für den COM-Typ mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="86c1b-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="86c1b-121">FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="86c1b-122">Ruft eine `mdManifestResource` token für die Ressource mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="86c1b-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="86c1b-123">GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="86c1b-124">Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="86c1b-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="86c1b-125">GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="86c1b-126">Ruft die eigenschafteneinstellungen der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="86c1b-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="86c1b-127">GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="86c1b-128">Ruft die eigenschafteneinstellungen des angegebenen `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="86c1b-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="86c1b-129">GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="86c1b-130">Ruft die eigenschafteneinstellungen des angegebenen COM-Typs ab.</span><span class="sxs-lookup"><span data-stu-id="86c1b-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="86c1b-131">GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="86c1b-132">Ruft die eigenschafteneinstellungen der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="86c1b-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="86c1b-133">GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="86c1b-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="86c1b-134">Ruft die eigenschafteneinstellungen für die angegebene Manifestressource ab.</span><span class="sxs-lookup"><span data-stu-id="86c1b-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="86c1b-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86c1b-135">Requirements</span></span>  
 <span data-ttu-id="86c1b-136">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86c1b-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86c1b-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="86c1b-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86c1b-138">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="86c1b-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86c1b-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86c1b-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86c1b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86c1b-140">See Also</span></span>  
 [<span data-ttu-id="86c1b-141">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="86c1b-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="86c1b-142">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86c1b-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
