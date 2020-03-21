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
ms.openlocfilehash: 048fe687e4d979576896f5310bddc855b40bb695
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175225"
---
# <a name="osinfo-structure"></a><span data-ttu-id="6fb95-102">OSINFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="6fb95-102">OSINFO Structure</span></span>
<span data-ttu-id="6fb95-103">Enthält Details zum Betriebssystem für eine Baugruppe oder ein Modul.</span><span class="sxs-lookup"><span data-stu-id="6fb95-103">Contains details about the operating system for an assembly or module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fb95-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="6fb95-105">Members</span><span class="sxs-lookup"><span data-stu-id="6fb95-105">Members</span></span>  
  
|<span data-ttu-id="6fb95-106">Member</span><span class="sxs-lookup"><span data-stu-id="6fb95-106">Member</span></span>|<span data-ttu-id="6fb95-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6fb95-107">Description</span></span>|  
|------------|-----------------|  
|`dwOSPlatformId`|<span data-ttu-id="6fb95-108">Einer der bezeichnern, der `GetVersionEx`durch die Microsoft Windows-Plattformfunktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6fb95-108">One of the identifier values defined by the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="6fb95-109">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6fb95-109">The following values are supported:</span></span><br /><br /> <span data-ttu-id="6fb95-110">- VER_PLATFORM_WIN32s oder 0x0000, um Microsoft Windows 3.1 anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb95-110">-   VER_PLATFORM_WIN32s, or 0x0000, to specify Microsoft Windows 3.1.</span></span><br /><span data-ttu-id="6fb95-111">- VER_PLATFORM_WIN32_WINDOWS oder 0x0001, um Windows 95, Windows 98 oder Betriebssysteme anzugeben, die von ihnen abstammen.</span><span class="sxs-lookup"><span data-stu-id="6fb95-111">-   VER_PLATFORM_WIN32_WINDOWS, or 0x0001, to specify Windows 95, Windows 98, or operating systems descended from them.</span></span><br /><span data-ttu-id="6fb95-112">- VER_PLATFORM_WIN32_NT oder 0x0002, um Windows NT oder von ihm abstammende Betriebssysteme anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb95-112">-   VER_PLATFORM_WIN32_NT, or 0x0002, to specify Windows NT or operating systems descended from it.</span></span>|  
|`dwOSMajorVersion`|<span data-ttu-id="6fb95-113">Die Hauptversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb95-113">The operating system major version, or a NULL value to indicate any version.</span></span>|  
|`dwOSMinorVersion`|<span data-ttu-id="6fb95-114">Die Nebenversion des Betriebssystems oder ein NULL-Wert, um eine beliebige Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb95-114">The operating system minor version, or a NULL value to indicate any version.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fb95-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6fb95-115">Remarks</span></span>  
 <span data-ttu-id="6fb95-116">`OSINFO`basiert auf `OSVERSIONINFOEX` der Struktur, die bei Aufrufen der `GetVersionEx`Microsoft Windows-Plattformfunktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6fb95-116">`OSINFO` is based on the `OSVERSIONINFOEX` structure that is used in calls to the Microsoft Windows platform function `GetVersionEx`.</span></span> <span data-ttu-id="6fb95-117">Diese Struktur wird von der ASSEMBLYMETADATA-Struktur verwendet, um die Betriebssystemunterstützung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6fb95-117">This structure is used by the ASSEMBLYMETADATA structure to indicate its operating system support.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fb95-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6fb95-118">Requirements</span></span>  
 <span data-ttu-id="6fb95-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fb95-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb95-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6fb95-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6fb95-121">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6fb95-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6fb95-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb95-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb95-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fb95-123">See also</span></span>

- [<span data-ttu-id="6fb95-124">Metadatenstrukturen</span><span class="sxs-lookup"><span data-stu-id="6fb95-124">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="6fb95-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fb95-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
