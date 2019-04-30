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
ms.openlocfilehash: 619643eb50abc75fd10d59b38767013b2617c8cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915290"
---
# <a name="asmcacheflags-enumeration"></a><span data-ttu-id="27b0a-102">ASM_CACHE_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="27b0a-102">ASM_CACHE_FLAGS Enumeration</span></span>
<span data-ttu-id="27b0a-103">Gibt die Quelle einer Assembly, die durch dargestellt [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="27b0a-103">Indicates the source of an assembly that is represented by [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b0a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27b0a-104">Syntax</span></span>  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="27b0a-105">Member</span><span class="sxs-lookup"><span data-stu-id="27b0a-105">Members</span></span>  
  
|<span data-ttu-id="27b0a-106">Member</span><span class="sxs-lookup"><span data-stu-id="27b0a-106">Member</span></span>|<span data-ttu-id="27b0a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="27b0a-107">Description</span></span>|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|<span data-ttu-id="27b0a-108">Listet den Cache der vorkompilierten Assemblys mit Ngen.exe an.</span><span class="sxs-lookup"><span data-stu-id="27b0a-108">Enumerates the cache of precompiled assemblies by using Ngen.exe.</span></span>|  
|`ASM_CACHE_GAC`|<span data-ttu-id="27b0a-109">Listet die im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="27b0a-109">Enumerates the global assembly cache.</span></span>|  
|`ASM_CACHE_DOWNLOAD`|<span data-ttu-id="27b0a-110">Listet die Assemblys, die bei Bedarf heruntergeladen wurden, oder, die verborgen kopiert wurde.</span><span class="sxs-lookup"><span data-stu-id="27b0a-110">Enumerates the assemblies that have been downloaded on demand or that have been shadow-copied.</span></span>|  
|`ASM_CACHE_ROOT`|<span data-ttu-id="27b0a-111">Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zurückgeben, im globalen Assemblycache für die common Language Runtime (CLR) Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="27b0a-111">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for the common language runtime (CLR) version 2.0.</span></span> <span data-ttu-id="27b0a-112">Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="27b0a-112">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
|`ASM_CACHE_ROOT_EX`|<span data-ttu-id="27b0a-113">Gibt an, dass die [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) Funktion sollte den Pfad zum globalen Assemblycache zurückgeben, für die CLR, Version 4.</span><span class="sxs-lookup"><span data-stu-id="27b0a-113">Indicates that the [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) function should return the path to the global assembly cache for CLR version 4.</span></span> <span data-ttu-id="27b0a-114">Nur im Kontext eines Aufrufs von [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span><span class="sxs-lookup"><span data-stu-id="27b0a-114">Meaningful only in the context of a call to [GetCachePath](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27b0a-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="27b0a-115">Requirements</span></span>  
 <span data-ttu-id="27b0a-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b0a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b0a-117">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="27b0a-117">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="27b0a-118">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="27b0a-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27b0a-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b0a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b0a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27b0a-120">See also</span></span>

- [<span data-ttu-id="27b0a-121">GetCachePath-Funktion</span><span class="sxs-lookup"><span data-stu-id="27b0a-121">GetCachePath Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [<span data-ttu-id="27b0a-122">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27b0a-122">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [<span data-ttu-id="27b0a-123">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="27b0a-123">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
