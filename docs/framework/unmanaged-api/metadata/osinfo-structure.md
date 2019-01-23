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
ms.openlocfilehash: abab67f28a5fabfc6c348af6b8b502b46510d460
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548754"
---
# <a name="osinfo-structure"></a><span data-ttu-id="cefed-102">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="cefed-102">OSINFO Structure</span></span>
<span data-ttu-id="cefed-103">Enthält Details über das Betriebssystem für eine Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="cefed-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cefed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cefed-104">Syntax</span></span>  
  
```  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="cefed-105">Member</span><span class="sxs-lookup"><span data-stu-id="cefed-105">Members</span></span>  
  
|<span data-ttu-id="cefed-106">Member</span><span class="sxs-lookup"><span data-stu-id="cefed-106">Member</span></span>|<span data-ttu-id="cefed-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cefed-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="cefed-108">Die ID-Werte, die von der Microsoft Windows-Plattform-Funktion definiert `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="cefed-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="cefed-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="cefed-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="cefed-110">-VER_PLATFORM_WIN32s, oder 0 x 0000, Microsoft Windows 3.1 angeben.</span><span class="sxs-lookup"><span data-stu-id="cefed-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="cefed-111">-VER_PLATFORM_WIN32_WINDOWS, oder 0 x 0001, die Angabe von Windows 95, Windows 98 oder Betriebssysteme, die von ihnen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="cefed-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="cefed-112">-VER_PLATFORM_WIN32_NT, oder 0 x 0010, die Angabe von Windows NT oder Betriebssysteme, die von ihm abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="cefed-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="cefed-113">Die Hauptversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cefed-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="cefed-114">Die Nebenversion des Betriebssystems oder einen NULL-Wert, der eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cefed-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cefed-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cefed-115">Remarks</span></span>  
 <span data-ttu-id="cefed-116">`OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen verwendete die Microsoft Windows-Plattform-Funktion `GetVersionEx`.</span><span class="sxs-lookup"><span data-stu-id="cefed-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="cefed-117">Diese Struktur wird durch die ASSEMBLYMETADATA-Struktur verwendet, um die betriebssystemunterstützung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cefed-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cefed-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cefed-118">Requirements</span></span>  
 <span data-ttu-id="cefed-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefed-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cefed-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cefed-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cefed-121">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="cefed-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cefed-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cefed-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefed-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cefed-123">See also</span></span>
- [<span data-ttu-id="cefed-124">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="cefed-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="cefed-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cefed-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
