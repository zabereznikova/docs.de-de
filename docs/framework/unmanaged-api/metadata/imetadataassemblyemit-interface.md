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
ms.openlocfilehash: 5d8bc54a94e1571ff8335c934407bbf235179ecc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728289"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="2cdf5-102">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cdf5-102">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="2cdf5-103">Stellt Methoden bereit, die das Selbstbeschreibungsmodell unterstützen, das von der Common Language Runtime zum Auflösen und Verwenden von Ressourcen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-103">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cdf5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2cdf5-104">Methods</span></span>  
  
|<span data-ttu-id="2cdf5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-105">Method</span></span>|<span data-ttu-id="2cdf5-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2cdf5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cdf5-107">DefineAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-107">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="2cdf5-108">Erstellt eine Assemblydatenstruktur, die Metadaten für die angegebene Assembly enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-108">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="2cdf5-109">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-109">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="2cdf5-110">Erstellt eine `AssemblyRef`-Struktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-110">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="2cdf5-111">DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-111">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="2cdf5-112">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-112">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="2cdf5-113">DefineFile-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-113">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="2cdf5-114">Erstellt eine `File`-Metadatenstruktur, die Metadaten für die Assembly enthält, auf die diese Assembly verweist, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-114">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="2cdf5-115">DefineManifestResource-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-115">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="2cdf5-116">Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-116">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="2cdf5-117">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-117">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="2cdf5-118">Ändert die angegebene `Assembly`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-118">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="2cdf5-119">SetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-119">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="2cdf5-120">Ändert die angegebene `AssemblyRef`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-120">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="2cdf5-121">SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-121">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="2cdf5-122">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-122">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="2cdf5-123">SetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-123">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="2cdf5-124">Ändert die angegebene `File`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-124">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="2cdf5-125">SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cdf5-125">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="2cdf5-126">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-126">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cdf5-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2cdf5-127">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cdf5-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2cdf5-128">Requirements</span></span>  

 <span data-ttu-id="2cdf5-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cdf5-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cdf5-130">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2cdf5-130">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cdf5-131">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cdf5-131">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2cdf5-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cdf5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdf5-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cdf5-133">See also</span></span>

- [<span data-ttu-id="2cdf5-134">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cdf5-134">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="2cdf5-135">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cdf5-135">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
