---
title: ASSEMBLY_INFO-Struktur
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390ab4881396bbc01337d087f05b6066153bfed1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795485"
---
# <a name="assembly_info-structure"></a><span data-ttu-id="4c24a-102">ASSEMBLY_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="4c24a-102">ASSEMBLY_INFO Structure</span></span>
<span data-ttu-id="4c24a-103">Enthält Informationen zu einer Assembly, die im globalen Assemblycache registriert ist.</span><span class="sxs-lookup"><span data-stu-id="4c24a-103">Contains information about an assembly that is registered in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c24a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c24a-104">Syntax</span></span>  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="4c24a-105">Member</span><span class="sxs-lookup"><span data-stu-id="4c24a-105">Members</span></span>  
  
|<span data-ttu-id="4c24a-106">Member</span><span class="sxs-lookup"><span data-stu-id="4c24a-106">Member</span></span>|<span data-ttu-id="4c24a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c24a-107">Description</span></span>|  
|------------|-----------------|  
|`cbAssemblyInfo`|<span data-ttu-id="4c24a-108">Die Größe der-Struktur in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4c24a-108">The size, in bytes, of the structure.</span></span> <span data-ttu-id="4c24a-109">Dieses Feld ist für die spätere Erweiterbarkeit reserviert.</span><span class="sxs-lookup"><span data-stu-id="4c24a-109">This field is reserved for future extensibility.</span></span>|  
|`dwAssemblyFlags`|<span data-ttu-id="4c24a-110">Flags, die Installationsdetails über die Assembly angeben.</span><span class="sxs-lookup"><span data-stu-id="4c24a-110">Flags that indicate installation details about the assembly.</span></span> <span data-ttu-id="4c24a-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4c24a-111">The following values are supported:</span></span><br /><br /> <span data-ttu-id="4c24a-112">: Der ASSEMBLYINFO_FLAG_INSTALLED-Wert, der angibt, dass die Assembly installiert ist.</span><span class="sxs-lookup"><span data-stu-id="4c24a-112">-   The ASSEMBLYINFO_FLAG_INSTALLED value, which indicates that the assembly is installed.</span></span> <span data-ttu-id="4c24a-113">Die aktuelle Version des-.NET Framework legt `dwAssemblyFlags` immer auf diesen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="4c24a-113">The current version of the .NET Framework always sets `dwAssemblyFlags` to this value.</span></span><br /><span data-ttu-id="4c24a-114">: Der ASSEMBLYINFO_FLAG_PAYLOADRESIDENT-Wert, der angibt, dass die Assembly eine Nutzlast ist.</span><span class="sxs-lookup"><span data-stu-id="4c24a-114">-   The ASSEMBLYINFO_FLAG_PAYLOADRESIDENT value, which indicates that the assembly is a payload resident.</span></span> <span data-ttu-id="4c24a-115">Die aktuelle Version des .NET Framework nie auf diesen `dwAssemblyFlags` Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c24a-115">The current version of the .NET Framework never sets `dwAssemblyFlags` to this value.</span></span>|  
|`uliAssemblySizeInKB`|<span data-ttu-id="4c24a-116">Die Gesamtgröße der Dateien in Kilobyte, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4c24a-116">The total size, in kilobytes, of the files that the assembly contains.</span></span>|  
|`pszCurrentAssemblyPathBuf`|<span data-ttu-id="4c24a-117">Ein Zeiger auf einen Zeichen folgen Puffer, der den aktuellen Pfad zur Manifest-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="4c24a-117">A pointer to a string buffer that holds the current path to the manifest file.</span></span> <span data-ttu-id="4c24a-118">Der Pfad muss mit einem NULL-Zeichen enden.</span><span class="sxs-lookup"><span data-stu-id="4c24a-118">The path must end with a null character.</span></span>|  
|`cchBuf`|<span data-ttu-id="4c24a-119">Die Anzahl der breit Zeichen, einschließlich des NULL-Abschluss Zeichens `pszCurrentAssemblyPathBuf` , das enthält.</span><span class="sxs-lookup"><span data-stu-id="4c24a-119">The number of wide characters, including the null terminator, that `pszCurrentAssemblyPathBuf` contains.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4c24a-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c24a-120">Requirements</span></span>  
 <span data-ttu-id="4c24a-121">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c24a-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c24a-122">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4c24a-122">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4c24a-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c24a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c24a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c24a-124">See also</span></span>

- [<span data-ttu-id="4c24a-125">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="4c24a-125">Fusion Structures</span></span>](fusion-structures.md)
- [<span data-ttu-id="4c24a-126">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="4c24a-126">Global Assembly Cache</span></span>](../../app-domains/gac.md)
