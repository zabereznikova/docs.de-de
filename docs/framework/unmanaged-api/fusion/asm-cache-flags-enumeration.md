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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b712c6ae5978e83dab085f48dd1fd572757384a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47107895"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="9b1e9-102">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b1e9-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="9b1e9-103">Gibt die Quelle einer Assembly, die durch dargestellt [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b1e9-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9b1e9-105">Member</span><span class="sxs-lookup"><span data-stu-id="9b1e9-105">Members</span></span>  
  
|<span data-ttu-id="9b1e9-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b1e9-106">Member</span></span>|<span data-ttu-id="9b1e9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b1e9-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="9b1e9-108">Listet den Cache der vorkompilierten Assemblys mit Ngen.exe an.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="9b1e9-109">Listet die im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="9b1e9-110">Listet die Assemblys, die bei Bedarf heruntergeladen wurden, oder, die verborgen kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="9b1e9-111">Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zurückgeben, im globalen Assemblycache für die common Language Runtime (CLR) Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="9b1e9-112">Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b1e9-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="9b1e9-113">Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zum globalen Assemblycache zurückgeben, für die CLR, Version 4.</span><span class="sxs-lookup"><span data-stu-id="9b1e9-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="9b1e9-114">Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="9b1e9-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b1e9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b1e9-115">Requirements</span></span>  
 <span data-ttu-id="9b1e9-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b1e9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b1e9-117">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9b1e9-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9b1e9-118">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b1e9-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b1e9-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b1e9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b1e9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b1e9-120">See Also</span></span>  
 [<span data-ttu-id="9b1e9-121">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b1e9-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)  
 [<span data-ttu-id="9b1e9-122">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b1e9-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 [<span data-ttu-id="9b1e9-123">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="9b1e9-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
