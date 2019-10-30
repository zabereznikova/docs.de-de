---
title: ASM_CACHE_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
ms.openlocfilehash: 85ac976daec8fd76ee21012a30611235609f4b34
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109491"
---
# <a name="asm_cache_flags-enumeration"></a><span data-ttu-id="2ad10-102">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2ad10-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="2ad10-103">Gibt die Quelle einer Assembly an, die von [IAssemblyCacheItem im globalen Assemblycache](iassemblycacheitem-interface.md) dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2ad10-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ad10-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2ad10-105">Member</span><span class="sxs-lookup"><span data-stu-id="2ad10-105">Members</span></span>  
  
|<span data-ttu-id="2ad10-106">Member</span><span class="sxs-lookup"><span data-stu-id="2ad10-106">Member</span></span>|<span data-ttu-id="2ad10-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ad10-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="2ad10-108">Listet den Cache von vorkompilierten Assemblys mithilfe von "ngen. exe" auf.</span><span class="sxs-lookup"><span data-stu-id="2ad10-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="2ad10-109">Listet den globalen Assemblycache auf.</span><span class="sxs-lookup"><span data-stu-id="2ad10-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="2ad10-110">Listet die Assemblys auf, die bei Bedarf heruntergeladen wurden oder auf die eine Schatten Kopie kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2ad10-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="2ad10-111">Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für die Common Language Runtime (CLR) Version 2,0 zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="2ad10-111">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="2ad10-112">Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="2ad10-112">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="2ad10-113">Gibt an, dass die [GetCachePath](getcachepath-function.md) -Funktion den Pfad zum globalen Assemblycache für CLR, Version 4, zurückgeben soll.</span><span class="sxs-lookup"><span data-stu-id="2ad10-113">Indicates that the [GetCachePath](getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="2ad10-114">Nur im Kontext eines Aufrufens von [GetCachePath](getcachepath-function.md)sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="2ad10-114">Meaningful only in the context of a call to [GetCachePath](getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ad10-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ad10-115">Requirements</span></span>  
 <span data-ttu-id="2ad10-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ad10-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ad10-117">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2ad10-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2ad10-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2ad10-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ad10-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ad10-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad10-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ad10-120">See also</span></span>

- [<span data-ttu-id="2ad10-121">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ad10-121">GetCachePath Function</span></span>](getcachepath-function.md)
- [<span data-ttu-id="2ad10-122">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ad10-122">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
- [<span data-ttu-id="2ad10-123">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="2ad10-123">Fusion Enumerations</span></span>](fusion-enumerations.md)
