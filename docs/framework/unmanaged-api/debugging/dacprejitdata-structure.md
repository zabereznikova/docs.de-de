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
ms.openlocfilehash: 77ef2c65157df4a033700bb8d0295875ede46554
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739106"
---
# <a name="dacprejitdata-structure"></a><span data-ttu-id="ee4f0-102">DacpReJitData-Struktur</span><span class="sxs-lookup"><span data-stu-id="ee4f0-102">DacpReJitData Structure</span></span>

<span data-ttu-id="ee4f0-103">Definiert die grundlegende Informationen zu einer bestimmten Profiler-instrumentierter Methode.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-103">Defines the basic information about a given profiler-instrumented method.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ee4f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee4f0-104">Syntax</span></span>

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

## <a name="members"></a><span data-ttu-id="ee4f0-105">Member</span><span class="sxs-lookup"><span data-stu-id="ee4f0-105">Members</span></span>

| <span data-ttu-id="ee4f0-106">Member</span><span class="sxs-lookup"><span data-stu-id="ee4f0-106">Member</span></span>           | <span data-ttu-id="ee4f0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee4f0-107">Description</span></span>                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | <span data-ttu-id="ee4f0-108">Die ReJit-Revisionsnummer für eine Methode.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-108">The ReJit revision number for a method.</span></span>                                                          |
| `flags`          | <span data-ttu-id="ee4f0-109">Ein Flag, das den aktuellen Status der ReJit-Instrumentierung für die angegebene Version der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-109">A flag indicating the current state of the method's ReJit instrumentation for the given version.</span></span> |
| `NativeCodeAddr` | <span data-ttu-id="ee4f0-110">Die Basisadresse des Rejitted-Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-110">The base address of the method's rejitted implementation.</span></span>                                         |

## <a name="remarks"></a><span data-ttu-id="ee4f0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee4f0-111">Remarks</span></span>

<span data-ttu-id="ee4f0-112">Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-112">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ee4f0-113">Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-113">To use it, define the structure as specified above.</span></span> <span data-ttu-id="ee4f0-114">Die Struktur muss auch mit definiert werden `ms_struct` packen, wenn nicht die Microsoft-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ee4f0-114">The structure must also be defined using `ms_struct` packing if not using the Microsoft compilers.</span></span>

## <a name="requirements"></a><span data-ttu-id="ee4f0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee4f0-115">Requirements</span></span>
<span data-ttu-id="ee4f0-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee4f0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ee4f0-117">**Header:** Keiner</span><span class="sxs-lookup"><span data-stu-id="ee4f0-117">**Header:** None</span></span>  
<span data-ttu-id="ee4f0-118">**Bibliothek:** Keiner</span><span class="sxs-lookup"><span data-stu-id="ee4f0-118">**Library:** None</span></span>  
<span data-ttu-id="ee4f0-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ee4f0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ee4f0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee4f0-120">See also</span></span>

- [<span data-ttu-id="ee4f0-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ee4f0-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ee4f0-122">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="ee4f0-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
