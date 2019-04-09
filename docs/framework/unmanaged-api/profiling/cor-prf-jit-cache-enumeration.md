---
title: COR_PRF_JIT_CACHE-Enumeration
ms.date: 03/30/2017
api_name:
- COR_PRF_JIT_CACHE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_JIT_CACHE
helpviewer_keywords:
- COR_PRF_JIT_CACHE enumeration [.NET Framework profiling]
ms.assetid: e7b8f6b4-95bc-4ba5-b9eb-f5590a7326a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cdbe36403f830926d611ffdc655d82ea25ddeef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144793"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="7081b-102">COR_PRF_JIT_CACHE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7081b-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="7081b-103">Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.</span><span class="sxs-lookup"><span data-stu-id="7081b-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  `COR_PRF_CACHED_FUNCTION_FOUND` <span data-ttu-id="7081b-104">hat den Wert 0 (null), also `COR_PRF_JIT_CACHE` kann nicht als boolesches Ersatzzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7081b-104">has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7081b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7081b-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="7081b-106">Member</span><span class="sxs-lookup"><span data-stu-id="7081b-106">Members</span></span>  
  
|<span data-ttu-id="7081b-107">Member</span><span class="sxs-lookup"><span data-stu-id="7081b-107">Member</span></span>|<span data-ttu-id="7081b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7081b-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="7081b-109">Die Suche finden Sie die Funktion.</span><span class="sxs-lookup"><span data-stu-id="7081b-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="7081b-110">Die Suche wurde die Funktion nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="7081b-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7081b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7081b-111">Requirements</span></span>  
 <span data-ttu-id="7081b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7081b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7081b-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7081b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7081b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7081b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7081b-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7081b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7081b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7081b-116">See also</span></span>

- [<span data-ttu-id="7081b-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="7081b-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
