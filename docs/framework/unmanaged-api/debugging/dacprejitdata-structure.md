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
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793813"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="87ad8-102">DacpReJitData-Struktur</span><span class="sxs-lookup"><span data-stu-id="87ad8-102">DacpReJitData Structure</span></span>

<span data-ttu-id="87ad8-103">Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.</span><span class="sxs-lookup"><span data-stu-id="87ad8-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="87ad8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="87ad8-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="87ad8-105">Member</span><span class="sxs-lookup"><span data-stu-id="87ad8-105">Members</span></span>

| <span data-ttu-id="87ad8-106">Member</span><span class="sxs-lookup"><span data-stu-id="87ad8-106">Member</span></span>           | <span data-ttu-id="87ad8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87ad8-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="87ad8-108">Die ReJIT-Revisionsnummer für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="87ad8-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="87ad8-109">Ein Flag, das den aktuellen Zustand der ReJIT-Instrumentation der Methode für die angegebene Version angibt.</span><span class="sxs-lookup"><span data-stu-id="87ad8-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="87ad8-110">Die Basisadresse der neu cotierten Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="87ad8-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="87ad8-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87ad8-111">Remarks</span></span>

<span data-ttu-id="87ad8-112">Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="87ad8-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="87ad8-113">Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.</span><span class="sxs-lookup"><span data-stu-id="87ad8-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="87ad8-114">Die Struktur muss auch mit `ms_struct` Verpackung definiert werden, wenn die Microsoft-Compiler nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="87ad8-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="87ad8-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87ad8-115">Requirements</span></span>
<span data-ttu-id="87ad8-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87ad8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="87ad8-117">**Header:** Gar</span><span class="sxs-lookup"><span data-stu-id="87ad8-117">**Header:** None</span></span>  
<span data-ttu-id="87ad8-118">**Bibliothek:** Gar</span><span class="sxs-lookup"><span data-stu-id="87ad8-118">**Library:** None</span></span>  
<span data-ttu-id="87ad8-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="87ad8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="87ad8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87ad8-120">See also</span></span>

- [<span data-ttu-id="87ad8-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="87ad8-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="87ad8-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="87ad8-122">Debugging Structures</span></span>](debugging-structures.md)
