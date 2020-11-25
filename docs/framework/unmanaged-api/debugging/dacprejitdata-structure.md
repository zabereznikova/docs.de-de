---
title: DacpReJitData-Struktur
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46708acc77dad00727ee35e7d06e4228eacbd502
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723037"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="b5f15-102">DacpReJitData-Struktur</span><span class="sxs-lookup"><span data-stu-id="b5f15-102">DacpReJitData Structure</span></span>

<span data-ttu-id="b5f15-103">Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.</span><span class="sxs-lookup"><span data-stu-id="b5f15-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b5f15-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5f15-104">Syntax</span></span>

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a><span data-ttu-id="b5f15-105">Member</span><span class="sxs-lookup"><span data-stu-id="b5f15-105">Members</span></span>

| <span data-ttu-id="b5f15-106">Member</span><span class="sxs-lookup"><span data-stu-id="b5f15-106">Member</span></span>           | <span data-ttu-id="b5f15-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b5f15-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="b5f15-108">Die ReJIT-Revisionsnummer für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="b5f15-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="b5f15-109">Ein Flag, das den aktuellen Zustand der ReJIT-Instrumentation der Methode für die angegebene Version angibt.</span><span class="sxs-lookup"><span data-stu-id="b5f15-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="b5f15-110">Die Basisadresse der neu cotierten Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="b5f15-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="b5f15-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5f15-111">Remarks</span></span>

<span data-ttu-id="b5f15-112">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="b5f15-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b5f15-113">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="b5f15-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="b5f15-114">Die Struktur muss auch mithilfe von Verpackung definiert werden, `ms_struct` Wenn die Microsoft-Compiler nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5f15-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5f15-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b5f15-115">Requirements</span></span>

<span data-ttu-id="b5f15-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5f15-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b5f15-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="b5f15-117">**Header:** None</span></span>  
<span data-ttu-id="b5f15-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="b5f15-118">**Library:** None</span></span>  
<span data-ttu-id="b5f15-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b5f15-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b5f15-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5f15-120">See also</span></span>

- [<span data-ttu-id="b5f15-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b5f15-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="b5f15-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b5f15-122">Debugging Structures</span></span>](debugging-structures.md)
