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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144793"
---
# <a name="corprfjitcache-enumeration"></a><span data-ttu-id="ab738-102">COR_PRF_JIT_CACHE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ab738-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="ab738-103">Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.</span><span class="sxs-lookup"><span data-stu-id="ab738-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab738-104">`COR_PRF_CACHED_FUNCTION_FOUND` hat den Wert 0 (null), also `COR_PRF_JIT_CACHE` kann nicht als boolesches Ersatzzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab738-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab738-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab738-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="ab738-106">Member</span><span class="sxs-lookup"><span data-stu-id="ab738-106">Members</span></span>  
  
|<span data-ttu-id="ab738-107">Member</span><span class="sxs-lookup"><span data-stu-id="ab738-107">Member</span></span>|<span data-ttu-id="ab738-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab738-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="ab738-109">Die Suche finden Sie die Funktion.</span><span class="sxs-lookup"><span data-stu-id="ab738-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="ab738-110">Die Suche wurde die Funktion nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="ab738-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab738-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab738-111">Requirements</span></span>  
 <span data-ttu-id="ab738-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab738-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab738-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab738-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab738-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab738-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab738-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab738-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab738-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab738-116">See also</span></span>

- [<span data-ttu-id="ab738-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="ab738-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
