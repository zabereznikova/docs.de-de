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
ms.openlocfilehash: 4436ece72b0a6a405fc41cba5413093fc42ce750
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860778"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="e4140-102">DacpReJitData-Struktur</span><span class="sxs-lookup"><span data-stu-id="e4140-102">DacpReJitData Structure</span></span>

<span data-ttu-id="e4140-103">Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.</span><span class="sxs-lookup"><span data-stu-id="e4140-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e4140-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4140-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="e4140-105">Members</span><span class="sxs-lookup"><span data-stu-id="e4140-105">Members</span></span>

| <span data-ttu-id="e4140-106">Member</span><span class="sxs-lookup"><span data-stu-id="e4140-106">Member</span></span>           | <span data-ttu-id="e4140-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4140-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="e4140-108">Die ReJIT-Revisionsnummer für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="e4140-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="e4140-109">Ein Flag, das den aktuellen Zustand der ReJIT-Instrumentation der Methode für die angegebene Version angibt.</span><span class="sxs-lookup"><span data-stu-id="e4140-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="e4140-110">Die Basisadresse der neu cotierten Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="e4140-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="e4140-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4140-111">Remarks</span></span>

<span data-ttu-id="e4140-112">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="e4140-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e4140-113">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="e4140-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="e4140-114">Die Struktur muss auch mithilfe `ms_struct` von Verpackung definiert werden, wenn die Microsoft-Compiler nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4140-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4140-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4140-115">Requirements</span></span>
<span data-ttu-id="e4140-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4140-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e4140-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="e4140-117">**Header:** None</span></span>  
<span data-ttu-id="e4140-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="e4140-118">**Library:** None</span></span>  
<span data-ttu-id="e4140-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e4140-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e4140-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="e4140-120">See also</span></span>

- [<span data-ttu-id="e4140-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="e4140-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e4140-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="e4140-122">Debugging Structures</span></span>](debugging-structures.md)
