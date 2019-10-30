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
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133726"
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

| Member            | Beschreibung                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Der Prozess hat einen neuen Speicherstatus über die weitere Ausführung erreicht.            |
| `FLUSH_ALL`       | Den Prozessspeicher könnte sich in irgendeiner Form vom vorherigen Zustand unterscheiden. |

## <a name="remarks"></a>Hinweise

 Ein Member der `CorDebugStateChange` Enumeration wird als Argument bereitgestellt, wenn der Debugger die `ProcessStateChanged`-Methode entweder mit [ICorDebugProcess4::P rocess StateChanged](icordebugprocess4-processstatechanged-method.md) oder [ICorDebugProcess6::P rocess StateChanged](icordebugprocess6-processstatechanged-method.md) aufruft.

## <a name="requirements"></a>Anforderungen

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

 **Header:** CorDebug.idl, CorDebug.h

 **Bibliothek:** CorGuids.lib

 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen von Enumerationen](debugging-enumerations.md)
- [Debuggen](index.md)
