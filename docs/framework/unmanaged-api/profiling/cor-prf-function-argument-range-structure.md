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
ms.openlocfilehash: dae5ed7c25f85051d1a28681fb88b056617c4de0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867245"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="62535-102">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="62535-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="62535-103">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="62535-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62535-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="62535-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="62535-105">Member</span><span class="sxs-lookup"><span data-stu-id="62535-105">Members</span></span>  
  
|<span data-ttu-id="62535-106">Member</span><span class="sxs-lookup"><span data-stu-id="62535-106">Members</span></span>|<span data-ttu-id="62535-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62535-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="62535-108">Die Startadresse des Blocks.</span><span class="sxs-lookup"><span data-stu-id="62535-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="62535-109">Die Länge des zusammenhängenden Blocks.</span><span class="sxs-lookup"><span data-stu-id="62535-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62535-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62535-110">Requirements</span></span>  
 <span data-ttu-id="62535-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62535-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62535-112">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="62535-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="62535-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62535-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62535-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62535-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62535-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62535-115">See also</span></span>

- [<span data-ttu-id="62535-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="62535-116">Profiling Structures</span></span>](profiling-structures.md)
