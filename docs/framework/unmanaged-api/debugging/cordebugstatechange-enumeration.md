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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05a29022d3ebad37322aef9826f10689d2b5b06b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723068"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="7af47-102">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="7af47-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="7af47-103">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7af47-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="7af47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7af47-104">Syntax</span></span>

```
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="7af47-105">Member</span><span class="sxs-lookup"><span data-stu-id="7af47-105">Members</span></span>

| <span data-ttu-id="7af47-106">Member</span><span class="sxs-lookup"><span data-stu-id="7af47-106">Member</span></span>            | <span data-ttu-id="7af47-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7af47-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="7af47-108">Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.</span><span class="sxs-lookup"><span data-stu-id="7af47-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="7af47-109">Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="7af47-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7af47-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7af47-110">Remarks</span></span>

 <span data-ttu-id="7af47-111">Ein Mitglied der `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger Ruft die `ProcessStateChanged` Methode entweder mit [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) oder [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="7af47-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="7af47-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7af47-112">Requirements</span></span>

 <span data-ttu-id="7af47-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7af47-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="7af47-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7af47-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="7af47-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7af47-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="7af47-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7af47-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7af47-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7af47-117">See also</span></span>

- [<span data-ttu-id="7af47-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="7af47-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="7af47-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="7af47-119">Debugging</span></span>](index.md)
