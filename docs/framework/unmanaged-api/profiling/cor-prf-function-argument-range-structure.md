---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dffefedf14d5f219736e429be191021b2de7ddd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125592"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="f9647-102">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="f9647-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="f9647-103">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="f9647-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9647-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9647-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="f9647-105">Member</span><span class="sxs-lookup"><span data-stu-id="f9647-105">Members</span></span>  
  
|<span data-ttu-id="f9647-106">Member</span><span class="sxs-lookup"><span data-stu-id="f9647-106">Members</span></span>|<span data-ttu-id="f9647-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9647-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="f9647-108">Die Startadresse des Blocks.</span><span class="sxs-lookup"><span data-stu-id="f9647-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="f9647-109">Die Länge der zusammenhängende Block wird.</span><span class="sxs-lookup"><span data-stu-id="f9647-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9647-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9647-110">Requirements</span></span>  
 <span data-ttu-id="f9647-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9647-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9647-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f9647-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f9647-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9647-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f9647-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f9647-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9647-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9647-115">See also</span></span>

- [<span data-ttu-id="f9647-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="f9647-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
