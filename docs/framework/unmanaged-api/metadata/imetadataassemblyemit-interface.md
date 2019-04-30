---
title: IMetaDataAssemblyEmit-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3a66ef090a205019493e099919739867e3936873
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905228"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="9a993-102">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a993-102">IMetaDataAssemblyEmit Interface</span></span>
<span data-ttu-id="9a993-103">Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9a993-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a993-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9a993-104">Methods</span></span>  
  
|<span data-ttu-id="9a993-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-105">Method</span></span>|<span data-ttu-id="9a993-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a993-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a993-107">DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-107">DefineAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="9a993-108">Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="9a993-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="9a993-109">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-109">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="9a993-110">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="9a993-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="9a993-111">DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-111">DefineExportedType Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="9a993-112">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="9a993-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="9a993-113">DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-113">DefineFile Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="9a993-114">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="9a993-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="9a993-115">DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-115">DefineManifestResource Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="9a993-116">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="9a993-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="9a993-117">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-117">SetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="9a993-118">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="9a993-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="9a993-119">SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-119">SetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="9a993-120">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="9a993-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="9a993-121">SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-121">SetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="9a993-122">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="9a993-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="9a993-123">SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-123">SetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="9a993-124">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="9a993-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="9a993-125">SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="9a993-125">SetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="9a993-126">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="9a993-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a993-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a993-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a993-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a993-128">Requirements</span></span>  
 <span data-ttu-id="9a993-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a993-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a993-130">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a993-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a993-131">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9a993-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a993-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a993-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a993-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a993-133">See also</span></span>

- [<span data-ttu-id="9a993-134">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9a993-134">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="9a993-135">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a993-135">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
