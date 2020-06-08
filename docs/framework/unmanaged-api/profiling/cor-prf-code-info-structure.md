---
title: COR_PRF_CODE_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: 9dbe0219f5932a9d212edaf5181b96335c47db0e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501013"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="81e61-102">COR_PRF_CODE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="81e61-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="81e61-103">Stellt einen zusammenhängenden Block von im Speicher befindlichem systemeigenem Code dar.</span><span class="sxs-lookup"><span data-stu-id="81e61-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81e61-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="81e61-105">Member</span><span class="sxs-lookup"><span data-stu-id="81e61-105">Members</span></span>  
  
|<span data-ttu-id="81e61-106">Member</span><span class="sxs-lookup"><span data-stu-id="81e61-106">Member</span></span>|<span data-ttu-id="81e61-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81e61-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="81e61-108">Die Startadresse des zusammenhängenden Code Blocks.</span><span class="sxs-lookup"><span data-stu-id="81e61-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="81e61-109">Die Größe des Blocks.</span><span class="sxs-lookup"><span data-stu-id="81e61-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81e61-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="81e61-110">Requirements</span></span>  
 <span data-ttu-id="81e61-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81e61-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81e61-112">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="81e61-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="81e61-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81e61-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81e61-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81e61-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e61-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="81e61-115">See also</span></span>

- [<span data-ttu-id="81e61-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="81e61-116">Profiling Structures</span></span>](profiling-structures.md)
