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
ms.workload: dotnet
ms.openlocfilehash: 6a7e4bd68bfd985b8902ae3b2340773ca77eee10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="5d6a1-102">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d6a1-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="5d6a1-103">Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d6a1-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5d6a1-104">Methods</span></span>  
  
|<span data-ttu-id="5d6a1-105">Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-105">Method</span></span>|<span data-ttu-id="5d6a1-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d6a1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d6a1-107">DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="5d6a1-108">Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="5d6a1-109">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="5d6a1-110">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="5d6a1-111">DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="5d6a1-112">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="5d6a1-113">DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="5d6a1-114">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="5d6a1-115">DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="5d6a1-116">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="5d6a1-117">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="5d6a1-118">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="5d6a1-119">SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="5d6a1-120">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="5d6a1-121">SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="5d6a1-122">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="5d6a1-123">SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="5d6a1-124">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="5d6a1-125">SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5d6a1-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="5d6a1-126">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5d6a1-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d6a1-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d6a1-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d6a1-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d6a1-128">Requirements</span></span>  
 <span data-ttu-id="5d6a1-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d6a1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d6a1-130">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d6a1-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d6a1-131">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5d6a1-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d6a1-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d6a1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6a1-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d6a1-133">See Also</span></span>  
 [<span data-ttu-id="5d6a1-134">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5d6a1-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="5d6a1-135">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d6a1-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
