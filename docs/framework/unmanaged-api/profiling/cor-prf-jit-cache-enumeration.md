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
ms.openlocfilehash: 57d6ba77081536eb2bce0bf62d43ac080b2f5554
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447345"
---
# <a name="cor_prf_jit_cache-enumeration"></a><span data-ttu-id="a76a6-102">COR_PRF_JIT_CACHE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a76a6-102">COR_PRF_JIT_CACHE Enumeration</span></span>
<span data-ttu-id="a76a6-103">Zeigt das Ergebnis einer zwischengespeicherten Funktionssuche.</span><span class="sxs-lookup"><span data-stu-id="a76a6-103">Indicates the result of a cached function search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a76a6-104">`COR_PRF_CACHED_FUNCTION_FOUND` hat den Wert 0 (null), sodass `COR_PRF_JIT_CACHE` nicht als boolesches Ersatz Zeichen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a76a6-104">`COR_PRF_CACHED_FUNCTION_FOUND` has a value of zero, so `COR_PRF_JIT_CACHE` cannot be used as a Boolean surrogate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a76a6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a76a6-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CACHED_FUNCTION_FOUND,  
    COR_PRF_CACHED_FUNCTION_NOT_FOUND  
} COR_PRF_JIT_CACHE;  
```  
  
## <a name="members"></a><span data-ttu-id="a76a6-106">Member</span><span class="sxs-lookup"><span data-stu-id="a76a6-106">Members</span></span>  
  
|<span data-ttu-id="a76a6-107">Member</span><span class="sxs-lookup"><span data-stu-id="a76a6-107">Member</span></span>|<span data-ttu-id="a76a6-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a76a6-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FUNCTION_FOUND`|<span data-ttu-id="a76a6-109">Bei der Suche wurde die-Funktion gefunden.</span><span class="sxs-lookup"><span data-stu-id="a76a6-109">The search found the function.</span></span>|  
|`COR_PRF_FUNCTION_NOT_FOUND`|<span data-ttu-id="a76a6-110">Die Funktion wurde von der Suche nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="a76a6-110">The search did not find the function.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a76a6-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a76a6-111">Requirements</span></span>  
 <span data-ttu-id="a76a6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a76a6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a76a6-113">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a76a6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a76a6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a76a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a76a6-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a76a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a76a6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a76a6-116">See also</span></span>

- [<span data-ttu-id="a76a6-117">Profilerstellungsenumerationen</span><span class="sxs-lookup"><span data-stu-id="a76a6-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
