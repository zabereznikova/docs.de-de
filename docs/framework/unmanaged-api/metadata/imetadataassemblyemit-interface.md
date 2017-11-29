---
title: IMetaDataAssemblyEmit-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af7a5fd5a564aa7366924f47b0c526aff7153521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="4fcbb-102">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fcbb-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="4fcbb-103">Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4fcbb-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="4fcbb-104">Methods</span></span>  
  
|<span data-ttu-id="4fcbb-105">Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-105">Method</span></span>|<span data-ttu-id="4fcbb-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4fcbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4fcbb-107">DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="4fcbb-108">Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="4fcbb-109">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="4fcbb-110">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="4fcbb-111">DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="4fcbb-112">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="4fcbb-113">DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="4fcbb-114">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="4fcbb-115">DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="4fcbb-116">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="4fcbb-117">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="4fcbb-118">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="4fcbb-119">SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="4fcbb-120">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="4fcbb-121">SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="4fcbb-122">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="4fcbb-123">SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="4fcbb-124">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="4fcbb-125">SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcbb-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="4fcbb-126">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="4fcbb-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fcbb-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fcbb-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fcbb-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4fcbb-128">Requirements</span></span>  
 <span data-ttu-id="4fcbb-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fcbb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcbb-130">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4fcbb-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4fcbb-131">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4fcbb-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4fcbb-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcbb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcbb-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fcbb-133">See Also</span></span>  
 [<span data-ttu-id="4fcbb-134">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4fcbb-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="4fcbb-135">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fcbb-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
