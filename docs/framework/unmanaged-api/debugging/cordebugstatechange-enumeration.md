---
title: CorDebugStateChange-Aufzählung
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795689"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="b6b48-102">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="b6b48-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="b6b48-103">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b6b48-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6b48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6b48-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="b6b48-105">Member</span><span class="sxs-lookup"><span data-stu-id="b6b48-105">Members</span></span>

| <span data-ttu-id="b6b48-106">Member</span><span class="sxs-lookup"><span data-stu-id="b6b48-106">Member</span></span>            | <span data-ttu-id="b6b48-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b6b48-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="b6b48-108">Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.</span><span class="sxs-lookup"><span data-stu-id="b6b48-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="b6b48-109">Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b6b48-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b6b48-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6b48-110">Remarks</span></span>

 <span data-ttu-id="b6b48-111">Ein Member der- `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger die `ProcessStateChanged` -Methode entweder mit [ICorDebugProcess4::P rocess StateChanged](icordebugprocess4-processstatechanged-method.md) oder [ICorDebugProcess6::P rocess StateChanged](icordebugprocess6-processstatechanged-method.md) aufruft.</span><span class="sxs-lookup"><span data-stu-id="b6b48-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="b6b48-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6b48-112">Requirements</span></span>

 <span data-ttu-id="b6b48-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b48-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="b6b48-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6b48-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="b6b48-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6b48-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="b6b48-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b48-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6b48-117">See also</span></span>

- [<span data-ttu-id="b6b48-118">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="b6b48-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="b6b48-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b6b48-119">Debugging</span></span>](index.md)
