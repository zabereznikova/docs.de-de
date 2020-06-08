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
ms.openlocfilehash: 8b3785955ec138bbf898e84aa4deb5ed2a6e6b53
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500948"
---
# <a name="cor_prf_function_argument_range-structure"></a><span data-ttu-id="bee4d-102">COR_PRF_FUNCTION_ARGUMENT_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="bee4d-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="bee4d-103">Stellt einen Block von Funktionsargumenten dar, die nacheinander in der Reihenfolge von links nach rechts im Arbeitsspeicher gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="bee4d-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bee4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bee4d-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="bee4d-105">Member</span><span class="sxs-lookup"><span data-stu-id="bee4d-105">Members</span></span>  
  
|<span data-ttu-id="bee4d-106">Members</span><span class="sxs-lookup"><span data-stu-id="bee4d-106">Members</span></span>|<span data-ttu-id="bee4d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bee4d-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="bee4d-108">Die Startadresse des Blocks.</span><span class="sxs-lookup"><span data-stu-id="bee4d-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="bee4d-109">Die Länge des zusammenhängenden Blocks.</span><span class="sxs-lookup"><span data-stu-id="bee4d-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bee4d-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bee4d-110">Requirements</span></span>  
 <span data-ttu-id="bee4d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bee4d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bee4d-112">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="bee4d-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="bee4d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bee4d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bee4d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bee4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bee4d-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="bee4d-115">See also</span></span>

- [<span data-ttu-id="bee4d-116">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="bee4d-116">Profiling Structures</span></span>](profiling-structures.md)
