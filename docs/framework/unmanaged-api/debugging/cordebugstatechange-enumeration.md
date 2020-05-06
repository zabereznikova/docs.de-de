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
# <a name="cordebugstatechange-enumeration"></a>CorDebugStateChange-Aufzählung

Beschreibt die Menge der zwischengespeicherten Daten, die auf der Grundlage von Änderungen am Prozess verworfen werden müssen.

## <a name="syntax"></a>Syntax

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Member

| Member            | BESCHREIBUNG                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.            |
| `FLUSH_ALL`       | Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden. |

## <a name="remarks"></a>Hinweise

 Ein Member der- `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger die `ProcessStateChanged` -Methode entweder mit [ICorDebugProcess4::P rocess StateChanged](icordebugprocess4-processstatechanged-method.md) oder [ICorDebugProcess6::P rocess StateChanged](icordebugprocess6-processstatechanged-method.md) aufruft.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

 **Header:** CorDebug.idl, CorDebug.h

 **Bibliothek:** CorGuids.lib

 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [Debugenumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
