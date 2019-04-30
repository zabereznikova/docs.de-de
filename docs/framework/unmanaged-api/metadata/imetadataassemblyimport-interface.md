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
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905410"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="09466-102">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09466-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="09466-103">Stellt Methoden zum Zugreifen auf und Untersuchen der Inhalte eines Assemblymanifests bereit.</span><span class="sxs-lookup"><span data-stu-id="09466-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="09466-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="09466-104">Methods</span></span>  
  
|<span data-ttu-id="09466-105">Methode</span><span class="sxs-lookup"><span data-stu-id="09466-105">Method</span></span>|<span data-ttu-id="09466-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09466-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="09466-107">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="09466-108">Gibt das Handle für den angegebenen Enumerator frei.</span><span class="sxs-lookup"><span data-stu-id="09466-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="09466-109">EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="09466-110">Ruft einen Schnittstellenzeiger auf einem Enumerator, enthält die `mdAssemblyRef` Token der Assemblys auf, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09466-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="09466-111">EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="09466-112">Ruft einen Schnittstellenzeiger auf einem Enumerator, enthält die `mdExportedType` Token von der COM-Typen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09466-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="09466-113">EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="09466-114">Ruft einen Schnittstellenzeiger auf einem Enumerator, enthält die `mdFile` Token der Dateien auf, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09466-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="09466-115">EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="09466-116">Ruft einen Schnittstellenzeiger auf einem Enumerator, enthält die `mdManifestResource` Token, die Ressourcen, die von der Assembly im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09466-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="09466-117">FindAssembliesByName-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="09466-118">Ruft ein Array von `mdAssemblyRef` -Token für die Assemblys mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="09466-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="09466-119">FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="09466-120">Ruft eine `mdExportedType` token für den COM-Typ mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="09466-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="09466-121">FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="09466-122">Ruft eine `mdManifestResource` token für die Ressource mit dem angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="09466-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="09466-123">GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="09466-124">Ruft das Token für die Assembly im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="09466-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="09466-125">GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="09466-126">Ruft die Einstellungen der Eigenschaft der angegebenen Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="09466-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="09466-127">GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="09466-128">Ruft die Einstellungen der Eigenschaft des angegebenen `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="09466-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="09466-129">GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="09466-130">Ruft die Einstellungen der Eigenschaft des angegebenen COM-Typs ab.</span><span class="sxs-lookup"><span data-stu-id="09466-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="09466-131">GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="09466-132">Ruft die Einstellungen der Eigenschaft der angegebenen Datei ab.</span><span class="sxs-lookup"><span data-stu-id="09466-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="09466-133">GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="09466-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="09466-134">Ruft die eigenschafteneinstellungen an, der die angegebene Manifestressource ab.</span><span class="sxs-lookup"><span data-stu-id="09466-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09466-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09466-135">Requirements</span></span>  
 <span data-ttu-id="09466-136">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09466-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09466-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09466-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09466-138">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="09466-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09466-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09466-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09466-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09466-140">See also</span></span>

- [<span data-ttu-id="09466-141">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="09466-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="09466-142">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09466-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
