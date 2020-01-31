---
title: COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867248"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="d739d-102">COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="d739d-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="d739d-103">Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="d739d-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d739d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d739d-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d739d-105">Member</span><span class="sxs-lookup"><span data-stu-id="d739d-105">Members</span></span>  
  
|<span data-ttu-id="d739d-106">Member</span><span class="sxs-lookup"><span data-stu-id="d739d-106">Member</span></span>|<span data-ttu-id="d739d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d739d-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="d739d-108">Die Anzahl der Argument Blöcke.</span><span class="sxs-lookup"><span data-stu-id="d739d-108">The number of blocks of arguments.</span></span> <span data-ttu-id="d739d-109">Das heißt, dieser Wert ist die Anzahl der [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) Strukturen im `ranges` Array.</span><span class="sxs-lookup"><span data-stu-id="d739d-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="d739d-110">Die Gesamtgröße aller Argumente.</span><span class="sxs-lookup"><span data-stu-id="d739d-110">The total size of all arguments.</span></span> <span data-ttu-id="d739d-111">Mit anderen Worten: dieser Wert ist die Summe der Argument Längen.</span><span class="sxs-lookup"><span data-stu-id="d739d-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="d739d-112">Ein Array von `COR_PRF_FUNCTION_ARGUMENT_RANGE`-Strukturen, von denen jedes einen Block von Funktions Argumenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="d739d-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d739d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d739d-113">Remarks</span></span>  
 <span data-ttu-id="d739d-114">Eine Funktion kann viele Argumente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d739d-114">A function may have many arguments.</span></span> <span data-ttu-id="d739d-115">Diese Argumente werden möglicherweise nicht im Arbeitsspeicher zusammenhängend gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d739d-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="d739d-116">Möglicherweise verfügen Sie über einen Block von drei Argumenten an einem Ort, einen Block mit zwei Argumenten an einer anderen Stelle und einen abschließenden Block eines Arguments an einer anderen Stelle.</span><span class="sxs-lookup"><span data-stu-id="d739d-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="d739d-117">Diese Argumente sind alle für die gleiche Funktion. Sie werden nur an unterschiedlichen Stellen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d739d-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="d739d-118">Die `COR_PRF_FUNCTION_ARGUMENT_INFO`-Struktur stellt alle Argumente einer einzelnen Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="d739d-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="d739d-119">Dabei wird ein Array verwendet, um auf alle Blöcke von Funktions Argumenten zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d739d-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="d739d-120">Für eine einzelne Funktion verfügen Sie also über eine einzelne `COR_PRF_FUNCTION_ARGUMENT_INFO` Struktur, die auf mehrere `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen verweist, die jeweils auf ein oder mehrere Funktionsargumente verweisen.</span><span class="sxs-lookup"><span data-stu-id="d739d-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="d739d-121">Argumente, die in Registern gespeichert werden, werden in den Arbeitsspeicher übertragen, um die Strukturen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d739d-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d739d-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d739d-122">Requirements</span></span>  
 <span data-ttu-id="d739d-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d739d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d739d-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="d739d-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d739d-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d739d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d739d-126">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d739d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d739d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d739d-127">See also</span></span>

- [<span data-ttu-id="d739d-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d739d-128">Profiling Structures</span></span>](profiling-structures.md)
