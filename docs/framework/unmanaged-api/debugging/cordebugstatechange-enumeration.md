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
ms.openlocfilehash: 676489880cb30ca540cb78d70797dbf4eedf7395
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739586"
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="57b04-102">CorDebugStateChange-Aufzählung</span><span class="sxs-lookup"><span data-stu-id="57b04-102">CorDebugStateChange Enumeration</span></span>

<span data-ttu-id="57b04-103">Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="57b04-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>

## <a name="syntax"></a><span data-ttu-id="57b04-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57b04-104">Syntax</span></span>

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a><span data-ttu-id="57b04-105">Member</span><span class="sxs-lookup"><span data-stu-id="57b04-105">Members</span></span>

| <span data-ttu-id="57b04-106">Member</span><span class="sxs-lookup"><span data-stu-id="57b04-106">Member</span></span>            | <span data-ttu-id="57b04-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57b04-107">Description</span></span>                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | <span data-ttu-id="57b04-108">Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.</span><span class="sxs-lookup"><span data-stu-id="57b04-108">The process reached a new memory state via forward execution.</span></span>            |
| `FLUSH_ALL`       | <span data-ttu-id="57b04-109">Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="57b04-109">The process' memory may be arbitrarily different than it was previously.</span></span> |

## <a name="remarks"></a><span data-ttu-id="57b04-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57b04-110">Remarks</span></span>

 <span data-ttu-id="57b04-111">Ein Mitglied der `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger Ruft die `ProcessStateChanged` Methode entweder mit [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) oder [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="57b04-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the `ProcessStateChanged` method either with [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) or [ICorDebugProcess6::ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span></span>

## <a name="requirements"></a><span data-ttu-id="57b04-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57b04-112">Requirements</span></span>

 <span data-ttu-id="57b04-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57b04-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="57b04-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57b04-114">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="57b04-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57b04-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="57b04-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b04-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="57b04-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57b04-117">See also</span></span>

- [<span data-ttu-id="57b04-118">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="57b04-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="57b04-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="57b04-119">Debugging</span></span>](index.md)
