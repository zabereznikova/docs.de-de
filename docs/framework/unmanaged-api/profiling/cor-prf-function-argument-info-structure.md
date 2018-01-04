---
title: COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="7200f-102">COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="7200f-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="7200f-103">Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="7200f-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7200f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7200f-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7200f-105">Member</span><span class="sxs-lookup"><span data-stu-id="7200f-105">Members</span></span>  
  
|<span data-ttu-id="7200f-106">Member</span><span class="sxs-lookup"><span data-stu-id="7200f-106">Member</span></span>|<span data-ttu-id="7200f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7200f-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="7200f-108">Die Anzahl der Blöcke von Argumenten.</span><span class="sxs-lookup"><span data-stu-id="7200f-108">The number of blocks of arguments.</span></span> <span data-ttu-id="7200f-109">Dieser Wert ist, also die Anzahl der [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Strukturen in den `ranges` Array.</span><span class="sxs-lookup"><span data-stu-id="7200f-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="7200f-110">Die Gesamtgröße aller Argumente.</span><span class="sxs-lookup"><span data-stu-id="7200f-110">The total size of all arguments.</span></span> <span data-ttu-id="7200f-111">Das heißt, ist dieser Wert die Summe der Argumentlängen.</span><span class="sxs-lookup"><span data-stu-id="7200f-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="7200f-112">Ein Array von `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede einen Block von Funktionsargumenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7200f-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7200f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7200f-113">Remarks</span></span>  
 <span data-ttu-id="7200f-114">Eine Funktion möglicherweise viele Argumente.</span><span class="sxs-lookup"><span data-stu-id="7200f-114">A function may have many arguments.</span></span> <span data-ttu-id="7200f-115">Diese Argumente können nicht zusammenhängend im Arbeitsspeicher gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7200f-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="7200f-116">Sie können einen Speicherblock, der drei Argumente an einem Ort, einen Speicherblock, der zwei Argumente in einer anderen Stelle und eine abschließende Block eines Arguments in einem anderen Ort verfügen.</span><span class="sxs-lookup"><span data-stu-id="7200f-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="7200f-117">Diese Argumente werden alle für die gleiche Funktion; Sie sind nur an unterschiedlichen Orten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7200f-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="7200f-118">Die `COR_PRF_FUNCTION_ARGUMENT_INFO` -Struktur stellt alle Argumente einer einzelnen Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="7200f-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="7200f-119">Ein Array verwendet, um alle Blöcke von Funktionsargumenten zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="7200f-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="7200f-120">Für eine einzelne Funktion haben Sie daher eine einzelne `COR_PRF_FUNCTION_ARGUMENT_INFO` -Struktur, die mehrere verweist auf `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede auf eine oder mehrere Argumente der Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="7200f-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="7200f-121">Argumente, die in Registern gespeichert sind, werden in den Arbeitsspeicher zum Erstellen von Strukturen gefüllt.</span><span class="sxs-lookup"><span data-stu-id="7200f-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7200f-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7200f-122">Requirements</span></span>  
 <span data-ttu-id="7200f-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7200f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7200f-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7200f-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7200f-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7200f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7200f-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7200f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7200f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7200f-127">See Also</span></span>  
 [<span data-ttu-id="7200f-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="7200f-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
