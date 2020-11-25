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
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732783"
---
# <a name="assemblymetadata-structure"></a><span data-ttu-id="b760d-102">ASSEMBLYMETADATA-Struktur</span><span class="sxs-lookup"><span data-stu-id="b760d-102">ASSEMBLYMETADATA Structure</span></span>

<span data-ttu-id="b760d-103">Enthält Informationen über die Assembly, auf die verwiesen wird, einschließlich ihrer Version und ihrer Unterstützung für Gebiets Schemas, Prozessoren und Betriebssysteme.</span><span class="sxs-lookup"><span data-stu-id="b760d-103">Contains information about the referenced assembly, including its version and its level of support for locales, processors, and operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b760d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b760d-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b760d-105">Member</span><span class="sxs-lookup"><span data-stu-id="b760d-105">Members</span></span>  
  
|<span data-ttu-id="b760d-106">Member</span><span class="sxs-lookup"><span data-stu-id="b760d-106">Member</span></span>|<span data-ttu-id="b760d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b760d-107">Description</span></span>|  
|------------|-----------------|  
|`usMajorVersion`|<span data-ttu-id="b760d-108">Die Hauptversionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b760d-108">The major version number of the referenced assembly.</span></span> <span data-ttu-id="b760d-109">Dieser Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="b760d-109">This value cannot be zero.</span></span> <span data-ttu-id="b760d-110">Wenn alle Bits von `usMajorVersion` festgelegt sind, wird die Hauptversion nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-110">If all the bits of `usMajorVersion` are set, the major version is not specified.</span></span>|  
|`usMinorVersion`|<span data-ttu-id="b760d-111">Die neben Versionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b760d-111">The minor version number of the referenced assembly.</span></span> <span data-ttu-id="b760d-112">Dieser Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="b760d-112">This value cannot be zero.</span></span> <span data-ttu-id="b760d-113">Wenn alle Bits von `usMinorVersion` festgelegt sind, wird die neben Version nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-113">If all the bits of `usMinorVersion` are set, the minor version is not specified.</span></span>|  
|`usBuildNumber`|<span data-ttu-id="b760d-114">Die Buildnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b760d-114">The build number of the referenced assembly.</span></span> <span data-ttu-id="b760d-115">Dieser Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="b760d-115">This value cannot be zero.</span></span> <span data-ttu-id="b760d-116">Wenn alle Bits von `usBuildNumber` festgelegt sind, wird die Buildnummer nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-116">If all the bits of `usBuildNumber` are set, the build number is not specified.</span></span>|  
|`usRevisionNumber`|<span data-ttu-id="b760d-117">Die Revisionsnummer der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b760d-117">The revision number of the referenced assembly.</span></span> <span data-ttu-id="b760d-118">Dieser Wert darf nicht NULL sein.</span><span class="sxs-lookup"><span data-stu-id="b760d-118">This value cannot be zero.</span></span> <span data-ttu-id="b760d-119">Wenn alle Bits von `usRevisionNumber` festgelegt sind, wird die Revisionsnummer nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-119">If all the bits of `usRevisionNumber` are set, the revision number is not specified.</span></span>|  
|`szLocale`|<span data-ttu-id="b760d-120">Eine Liste von Gebiets Schema Namen, die der durch Semikolons getrennten RFC1766-Spezifikation entsprechen und die von der referenzierten Assembly unterstützten Gebiets Schemas angeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-120">A list of locale names conforming to the RFC1766 specification, separated by semicolons, specifying the locales supported by the referenced assembly.</span></span> <span data-ttu-id="b760d-121">Ein NULL-Wert gibt Gebiets Schema Unabhängigkeit an.</span><span class="sxs-lookup"><span data-stu-id="b760d-121">A null value indicates locale independence.</span></span> <span data-ttu-id="b760d-122">**Hinweis:**  In der .NET Framework Version 1,0 können Sie nicht mehr als ein Gebiets Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="b760d-122">**Note:**  In the .NET Framework version 1.0 you cannot specify more than one locale.</span></span>|  
|`cbLocale`|<span data-ttu-id="b760d-123">Die Größe in breit Zeichen von `szLocale` .</span><span class="sxs-lookup"><span data-stu-id="b760d-123">The size in wide characters of `szLocale`.</span></span>|  
|`rdwProcessor`|<span data-ttu-id="b760d-124">Ein Array von Bezeichners, wie in "Winnt. h" definiert, für die Prozessortypen, die von der Assembly unterstützt werden, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b760d-124">An array of identifiers, as defined in Winnt.h, for the processor types that are supported by the referenced assembly.</span></span> <span data-ttu-id="b760d-125">Ein NULL-Wert gibt die Unabhängigkeit des Prozessors an.</span><span class="sxs-lookup"><span data-stu-id="b760d-125">A NULL value indicates processor independence.</span></span>|  
|`ulProcessor`|<span data-ttu-id="b760d-126">Die Länge des `rdwProcessor`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b760d-126">The length of the `rdwProcessor` array.</span></span>|  
|`rOS`|<span data-ttu-id="b760d-127">Ein Array von [OSInfo](osinfo-structure.md) -Instanzen, das die Betriebssysteme angibt, die von der referenzierten Assembly unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b760d-127">An array of [OSINFO](osinfo-structure.md) instances specifying the operating systems that are supported by the referenced assembly.</span></span> <span data-ttu-id="b760d-128">Ein NULL-Wert gibt die Unabhängigkeit des Betriebssystems an.</span><span class="sxs-lookup"><span data-stu-id="b760d-128">A NULL value indicates operating-system independence.</span></span>|  
|`ulOS`|<span data-ttu-id="b760d-129">Die Länge des `rOS`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b760d-129">The length of the `rOS` array.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b760d-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b760d-130">Requirements</span></span>  

 <span data-ttu-id="b760d-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b760d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b760d-132">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b760d-132">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b760d-133">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b760d-133">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b760d-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b760d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b760d-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b760d-135">See also</span></span>

- [<span data-ttu-id="b760d-136">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="b760d-136">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="b760d-137">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b760d-137">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="b760d-138">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="b760d-138">OSINFO Structure</span></span>](osinfo-structure.md)
