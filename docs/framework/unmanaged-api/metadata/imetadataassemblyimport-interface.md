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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da75f98edb54080658dc86f48d4ebb458d72f20d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449311"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="04de8-102">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04de8-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="04de8-103">Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.</span><span class="sxs-lookup"><span data-stu-id="04de8-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04de8-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="04de8-104">Methods</span></span>  
  
|<span data-ttu-id="04de8-105">Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-105">Method</span></span>|<span data-ttu-id="04de8-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04de8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04de8-107">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="04de8-108">Gibt das Handle für den angegebenen Enumerator frei.</span><span class="sxs-lookup"><span data-stu-id="04de8-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="04de8-109">EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="04de8-110">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdAssemblyRef` Token der Assemblys, auf die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="04de8-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="04de8-111">EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="04de8-112">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdExportedType` Token von der COM-Typen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="04de8-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="04de8-113">EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="04de8-114">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdFile` Token der Dateien, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="04de8-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="04de8-115">EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="04de8-116">Ruft einen Schnittstellenzeiger auf einem Enumerator, der enthält die `mdManifestResource` Token, die Ressourcen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="04de8-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="04de8-117">FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="04de8-118">Ruft ein Array von `mdAssemblyRef` Token für die Assemblys mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="04de8-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="04de8-119">FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="04de8-120">Ruft eine `mdExportedType` token für den COM-Typ mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="04de8-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="04de8-121">FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="04de8-122">Ruft eine `mdManifestResource` token für die Ressource mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="04de8-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="04de8-123">GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="04de8-124">Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="04de8-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="04de8-125">GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="04de8-126">Ruft die eigenschafteneinstellungen der angegebenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="04de8-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="04de8-127">GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="04de8-128">Ruft die eigenschafteneinstellungen des angegebenen `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="04de8-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="04de8-129">GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="04de8-130">Ruft die eigenschafteneinstellungen des angegebenen COM-Typs ab.</span><span class="sxs-lookup"><span data-stu-id="04de8-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="04de8-131">GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="04de8-132">Ruft die eigenschafteneinstellungen der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="04de8-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="04de8-133">GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="04de8-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="04de8-134">Ruft die eigenschafteneinstellungen für die angegebene Manifestressource ab.</span><span class="sxs-lookup"><span data-stu-id="04de8-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04de8-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="04de8-135">Requirements</span></span>  
 <span data-ttu-id="04de8-136">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04de8-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04de8-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04de8-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04de8-138">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="04de8-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04de8-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04de8-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04de8-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04de8-140">See Also</span></span>  
 [<span data-ttu-id="04de8-141">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="04de8-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="04de8-142">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="04de8-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
