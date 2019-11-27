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
ms.openlocfilehash: 89111bf7eb03d20c2010c7a20c4cd055c2a021e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430736"
---
# <a name="osinfo-structure"></a><span data-ttu-id="21106-102">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="21106-102">OSINFO Structure</span></span>
<span data-ttu-id="21106-103">Enthält Details zum Betriebssystem für eine Assembly oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="21106-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21106-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21106-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;   
    DWORD   dwOSMinorVersion;   
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="21106-105">Member</span><span class="sxs-lookup"><span data-stu-id="21106-105">Members</span></span>  
  
|<span data-ttu-id="21106-106">Member</span><span class="sxs-lookup"><span data-stu-id="21106-106">Member</span></span>|<span data-ttu-id="21106-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21106-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="21106-108">Einer der Bezeichnerwerte, die von der Microsoft Windows-Platt Form Funktion `GetVersionEx`definiert werden.</span><span class="sxs-lookup"><span data-stu-id="21106-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="21106-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="21106-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="21106-110">-VER_PLATFORM_WIN32s oder 0x0000 zum Angeben von Microsoft Windows 3,1.</span><span class="sxs-lookup"><span data-stu-id="21106-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="21106-111">-VER_PLATFORM_WIN32_WINDOWS oder 0x0001, um Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von Ihnen abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="21106-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="21106-112">-VER_PLATFORM_WIN32_NT oder 0x0010, um Windows NT oder Betriebssysteme anzugeben, die davon abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="21106-112">-   VER_PLATFORM_WIN32_NT, or 0x0010, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="21106-113">Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="21106-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="21106-114">Die neben Version des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="21106-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21106-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21106-115">Remarks</span></span>  
 <span data-ttu-id="21106-116">`OSINFO` basiert auf der `OSVERSIONINFOEX` Struktur, die in Aufrufen der Funktion `GetVersionEx`der Microsoft Windows-Plattform verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="21106-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="21106-117">Diese Struktur wird von der ASSEMBLYMETADATA-Struktur verwendet, um die Betriebssystemunterstützung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="21106-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21106-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="21106-118">Requirements</span></span>  
 <span data-ttu-id="21106-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21106-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21106-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="21106-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="21106-121">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="21106-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="21106-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21106-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21106-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21106-123">See also</span></span>

- [<span data-ttu-id="21106-124">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="21106-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="21106-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21106-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
