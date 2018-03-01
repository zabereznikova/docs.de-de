---
title: OSINFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd30fe7904fa6c0685dd9c39931cc545e4e30583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="osinfo-structure"></a><span data-ttu-id="617e7-102">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="617e7-102">OSINFO Structure</span></span>
<span data-ttu-id="617e7-103">Enthält Details über das Betriebssystem für eine Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="617e7-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="617e7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="617e7-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="617e7-105">Member</span><span class="sxs-lookup"><span data-stu-id="617e7-105">Members</span></span>  
  
|<span data-ttu-id="617e7-106">Member</span><span class="sxs-lookup"><span data-stu-id="617e7-106">Member</span></span>|<span data-ttu-id="617e7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="617e7-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="617e7-108">Einer der Bezeichnerwerte, die durch die Microsoft Windows-Plattform-Funktion definierten `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="617e7-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="617e7-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="617e7-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="617e7-110">-VER_PLATFORM_WIN32s, oder 0 x 0000, um Microsoft Windows 3.1 anzugeben.</span><span class="sxs-lookup"><span data-stu-id="617e7-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="617e7-111">-VER_PLATFORM_WIN32_WINDOWS, oder 0 x 0001, Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von ihnen abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="617e7-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="617e7-112">-VER_PLATFORM_WIN32_NT, oder 0 x 0010, Windows NT oder Betriebssysteme anzugeben, die von der sie abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="617e7-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="617e7-113">Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="617e7-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="617e7-114">Die Nebenversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="617e7-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="617e7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="617e7-115">Remarks</span></span>  
 <span data-ttu-id="617e7-116">`OSINFO`basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete der Microsoft Windows-Plattform-Funktion `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="617e7-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="617e7-117">Diese Struktur wird von der ASSEMBLYMETADATA-Struktur an, dass die Betriebssystem-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="617e7-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="617e7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="617e7-118">Requirements</span></span>  
 <span data-ttu-id="617e7-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="617e7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="617e7-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="617e7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="617e7-121">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="617e7-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="617e7-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="617e7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617e7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="617e7-123">See Also</span></span>  
 [<span data-ttu-id="617e7-124">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="617e7-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
 [<span data-ttu-id="617e7-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="617e7-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
