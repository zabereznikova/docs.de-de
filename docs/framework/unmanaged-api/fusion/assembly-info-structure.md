---
title: ASSEMBLY_INFO-Struktur
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
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 215d80c3d207c2f50cfbd74386915b0467692b57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyinfo-structure"></a><span data-ttu-id="eaf02-102">ASSEMBLY_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="eaf02-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="eaf02-103">Enthält Informationen zu einer Assembly, die im globalen Assemblycache registriert ist.</span><span class="sxs-lookup"><span data-stu-id="eaf02-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eaf02-104">Syntax</span></span>  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="eaf02-105">Member</span><span class="sxs-lookup"><span data-stu-id="eaf02-105">Members</span></span>  
  
|<span data-ttu-id="eaf02-106">Member</span><span class="sxs-lookup"><span data-stu-id="eaf02-106">Member</span></span>|<span data-ttu-id="eaf02-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaf02-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="eaf02-108">Die Größe in Bytes, der Struktur.</span><span class="sxs-lookup"><span data-stu-id="eaf02-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="eaf02-109">Dieses Feld ist für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="eaf02-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="eaf02-110">Flags, die Details zur Installation über die Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="eaf02-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="eaf02-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="eaf02-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="eaf02-112">– Der ASSEMBLYINFO_FLAG_INSTALLED-Wert, der angibt, dass die Assembly installiert ist.</span><span class="sxs-lookup"><span data-stu-id="eaf02-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="eaf02-113">Legt die aktuelle Version von .NET Framework `dwAssemblyFlags` mit diesem Wert.</span><span class="sxs-lookup"><span data-stu-id="eaf02-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="eaf02-114">– Der ASSEMBLYINFO_FLAG_PAYLOADRESIDENT-Wert, der gibt an, dass die Assembly eine residenten Nutzlast ist.</span><span class="sxs-lookup"><span data-stu-id="eaf02-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="eaf02-115">Die aktuelle Version von .NET Framework nie legt `dwAssemblyFlags` mit diesem Wert.</span><span class="sxs-lookup"><span data-stu-id="eaf02-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="eaf02-116">Die Gesamtgröße der Dateien, die die Assembly enthält in Kilobytes.</span><span class="sxs-lookup"><span data-stu-id="eaf02-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="eaf02-117">Ein Zeiger auf einen Zeichenfolgenpuffer, der den aktuellen Pfad der Manifestdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="eaf02-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="eaf02-118">Der Pfad muss mit einem Null-Zeichen enden.</span><span class="sxs-lookup"><span data-stu-id="eaf02-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="eaf02-119">Die Anzahl der Breitzeichen, einschließlich der null-Abschlusszeichen, `pszCurrentAssemblyPathBuf` enthält.</span><span class="sxs-lookup"><span data-stu-id="eaf02-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eaf02-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eaf02-120">Requirements</span></span>  
 <span data-ttu-id="eaf02-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf02-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf02-122">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="eaf02-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eaf02-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf02-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf02-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaf02-124">See Also</span></span>  
 [<span data-ttu-id="eaf02-125">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="eaf02-125">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [<span data-ttu-id="eaf02-126">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="eaf02-126">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
