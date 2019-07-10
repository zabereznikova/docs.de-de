---
title: ASSEMBLYMETADATA-Struktur
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5039117c649943a1f05a91ecccf22eb4230e5e7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776377"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="c41eb-102">ASSEMBLYMETADATA-Struktur</span><span class="sxs-lookup"><span data-stu-id="c41eb-102">ASSEMBLYMETADATA Structure</span></span>
<span data-ttu-id="c41eb-103">Enthält Informationen über die referenzierte Assembly, einschließlich Version und der Grad der Unterstützung für Gebietsschemas, Prozessoren und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="c41eb-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c41eb-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a><span data-ttu-id="c41eb-105">Member</span><span class="sxs-lookup"><span data-stu-id="c41eb-105">Members</span></span>  
  
|<span data-ttu-id="c41eb-106">Member</span><span class="sxs-lookup"><span data-stu-id="c41eb-106">Member</span></span>|<span data-ttu-id="c41eb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c41eb-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="c41eb-108">Die Hauptversionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c41eb-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="c41eb-109">Dieser Wert darf nicht 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c41eb-109">This value cannot be zero.</span></span> <span data-ttu-id="c41eb-110">Wenn alle Bits `usMajorVersion` festgelegt ist, wird die Version ist nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c41eb-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="c41eb-111">Die Nebenversionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c41eb-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="c41eb-112">Dieser Wert darf nicht 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c41eb-112">This value cannot be zero.</span></span> <span data-ttu-id="c41eb-113">Wenn alle Bits `usMinorVersion` festgelegt sind, werden die Nebenversion ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="c41eb-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="c41eb-114">Die Buildnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c41eb-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="c41eb-115">Dieser Wert darf nicht 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c41eb-115">This value cannot be zero.</span></span> <span data-ttu-id="c41eb-116">Wenn alle Bits `usBuildNumber` festgelegt ist, wird die Build-Nummer nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c41eb-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="c41eb-117">Die Revisionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c41eb-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="c41eb-118">Dieser Wert darf nicht 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c41eb-118">This value cannot be zero.</span></span> <span data-ttu-id="c41eb-119">Wenn alle Bits `usRevisionNumber` festgelegt ist, wird die Revisionsnummer nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c41eb-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="c41eb-120">Eine Liste der Gebietsschemanamen, die RFC1766-Spezifikation, getrennt durch ein Semikolon, unterstützt durch die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c41eb-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="c41eb-121">Ein null-Wert gibt die Gebietsschemaunabhängigkeit von der an.</span><span class="sxs-lookup"><span data-stu-id="c41eb-121">A null value indicates locale independence.</span></span> <span data-ttu-id="c41eb-122">**Hinweis**:  In .NET Framework, Version 1.0, die Sie nicht mehr als ein einzelnes Gebietsschema angeben können.</span><span class="sxs-lookup"><span data-stu-id="c41eb-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="c41eb-123">Die Größe in Breitzeichen `szLocale`.</span><span class="sxs-lookup"><span data-stu-id="c41eb-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="c41eb-124">Ein Array von Bezeichnern, wie in "Winnt.h", für die Prozessortypen definiert, die von der referenzierten Assembly unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c41eb-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="c41eb-125">Ein NULL-Wert gibt die Prozessorunabhängigkeit von der an.</span><span class="sxs-lookup"><span data-stu-id="c41eb-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="c41eb-126">Die Länge der `rdwProcessor` Array.</span><span class="sxs-lookup"><span data-stu-id="c41eb-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="c41eb-127">Ein Array von [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) Instanzen angeben, die die Betriebssysteme, die von der referenzierten Assembly unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c41eb-127">An array of [OSINFO](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="c41eb-128">Ein NULL-Wert gibt die Unabhängigkeit von der Betriebssystem-an.</span><span class="sxs-lookup"><span data-stu-id="c41eb-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="c41eb-129">Die Länge der `rOS` Array.</span><span class="sxs-lookup"><span data-stu-id="c41eb-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c41eb-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c41eb-130">Requirements</span></span>  
 <span data-ttu-id="c41eb-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c41eb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c41eb-132">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c41eb-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c41eb-133">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c41eb-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c41eb-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c41eb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41eb-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c41eb-135">See also</span></span>

- [<span data-ttu-id="c41eb-136">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="c41eb-136">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="c41eb-137">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c41eb-137">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c41eb-138">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="c41eb-138">OSINFO Structure</span></span>](../../../../docs/framework/unmanaged-api/metadata/osinfo-structure.md)
