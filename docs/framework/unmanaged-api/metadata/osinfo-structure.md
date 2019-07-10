---
title: OSINFO-Struktur
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a36cd3c5fb638799a735e4b4a1a98959500300b5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761601"
---
# <a name="osinfo-structure"></a><span data-ttu-id="fe3e9-102">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="fe3e9-102">OSINFO Structure</span></span>
<span data-ttu-id="fe3e9-103">Enthält Details über das Betriebssystem für eine Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe3e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe3e9-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="fe3e9-105">Member</span><span class="sxs-lookup"><span data-stu-id="fe3e9-105">Members</span></span>  
  
|<span data-ttu-id="fe3e9-106">Member</span><span class="sxs-lookup"><span data-stu-id="fe3e9-106">Member</span></span>|<span data-ttu-id="fe3e9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe3e9-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="fe3e9-108">Die ID-Werte, die von der Microsoft Windows-Plattform-Funktion definiert `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="fe3e9-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="fe3e9-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="fe3e9-110">-VER_PLATFORM_WIN32s, oder 0 x 0000, Microsoft Windows 3.1 angeben.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="fe3e9-111">-VER_PLATFORM_WIN32_WINDOWS, oder 0 x 0001, die Angabe von Windows 95, Windows 98 oder Betriebssysteme, die von ihnen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="fe3e9-112">-VER_PLATFORM_WIN32_NT, oder 0 x 0010, die Angabe von Windows NT oder Betriebssysteme, die von ihm abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="fe3e9-113">Die Hauptversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="fe3e9-114">Die Nebenversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe3e9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe3e9-115">Remarks</span></span>  
 <span data-ttu-id="fe3e9-116">`OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete die Microsoft Windows-Plattform-Funktion `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="fe3e9-117">Diese Struktur wird durch die ASSEMBLYMETADATA-Struktur verwendet, um die betriebssystemunterstützung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fe3e9-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe3e9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe3e9-118">Requirements</span></span>  
 <span data-ttu-id="fe3e9-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe3e9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe3e9-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe3e9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe3e9-121">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="fe3e9-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe3e9-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe3e9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe3e9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe3e9-123">See also</span></span>

- [<span data-ttu-id="fe3e9-124">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="fe3e9-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="fe3e9-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe3e9-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
