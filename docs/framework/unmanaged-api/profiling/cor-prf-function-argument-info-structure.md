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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bb92f9ba8ff0aed1c6eb1fa44fb4d7c9abc186a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714230"
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="cee4a-102">COR_PRF_FUNCTION_ARGUMENT_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="cee4a-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="cee4a-103">Stellt die Argumente einer Funktion dar, in Reihenfolge von links nach rechts.</span><span class="sxs-lookup"><span data-stu-id="cee4a-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cee4a-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="cee4a-105">Member</span><span class="sxs-lookup"><span data-stu-id="cee4a-105">Members</span></span>  
  
|<span data-ttu-id="cee4a-106">Member</span><span class="sxs-lookup"><span data-stu-id="cee4a-106">Member</span></span>|<span data-ttu-id="cee4a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cee4a-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="cee4a-108">Die Anzahl der Blöcke der Argumente.</span><span class="sxs-lookup"><span data-stu-id="cee4a-108">The number of blocks of arguments.</span></span> <span data-ttu-id="cee4a-109">Dieser Wert ist, also die Anzahl der [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) Strukturen in der `ranges` Array.</span><span class="sxs-lookup"><span data-stu-id="cee4a-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="cee4a-110">Die Gesamtgröße aller Argumente.</span><span class="sxs-lookup"><span data-stu-id="cee4a-110">The total size of all arguments.</span></span> <span data-ttu-id="cee4a-111">Das heißt, ist dieser Wert die Summe der Argumentlängen.</span><span class="sxs-lookup"><span data-stu-id="cee4a-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="cee4a-112">Ein Array von `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede einen Block von Funktionsargumenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="cee4a-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cee4a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cee4a-113">Remarks</span></span>  
 <span data-ttu-id="cee4a-114">Eine Funktion möglicherweise viele Argumente.</span><span class="sxs-lookup"><span data-stu-id="cee4a-114">A function may have many arguments.</span></span> <span data-ttu-id="cee4a-115">Diese Argumente können nicht im Arbeitsspeicher zusammenhängend gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cee4a-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="cee4a-116">Sie möglicherweise einen Block von drei Argumenten an einem Ort, einen Block, der zwei Argumente in einen anderen Speicherort und ein letzter Block eines Arguments in einer anderen Stelle.</span><span class="sxs-lookup"><span data-stu-id="cee4a-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="cee4a-117">Diese Argumente werden alle für die gleiche Funktion; Sie können nur an verschiedenen Speicherorten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cee4a-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="cee4a-118">Die `COR_PRF_FUNCTION_ARGUMENT_INFO` Werttypstruktur alle Argumente eine einzelne Funktion.</span><span class="sxs-lookup"><span data-stu-id="cee4a-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="cee4a-119">Er verwendet ein Array, um alle Blöcke der Argumente der Funktion zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="cee4a-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="cee4a-120">Für eine einzelne Funktion, Sie müssen daher eine einzelne `COR_PRF_FUNCTION_ARGUMENT_INFO` -Struktur, die mehrere verweist auf `COR_PRF_FUNCTION_ARGUMENT_RANGE` Strukturen, von denen jede auf eine oder mehrere Argumente der Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="cee4a-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="cee4a-121">Argumente, die in Registern gespeichert werden, sind in den Arbeitsspeicher zum Erstellen von Strukturen überlaufen.</span><span class="sxs-lookup"><span data-stu-id="cee4a-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee4a-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cee4a-122">Requirements</span></span>  
 <span data-ttu-id="cee4a-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cee4a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cee4a-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="cee4a-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="cee4a-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cee4a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cee4a-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cee4a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee4a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cee4a-127">See also</span></span>
- [<span data-ttu-id="cee4a-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="cee4a-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
