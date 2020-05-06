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
# <a name="dacprejitdata-structure"></a>DacpReJitData-Struktur

Definiert die grundlegenden Informationen zu einer bestimmten Profiler-instrumentierten Methode.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

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

## <a name="members"></a>Members

| Member           | BESCHREIBUNG                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | Die ReJIT-Revisionsnummer für eine Methode.                                                          |
| `flags`          | Ein Flag, das den aktuellen Zustand der ReJIT-Instrumentation der Methode für die angegebene Version angibt. |
| `NativeCodeAddr` | Die Basisadresse der neu cotierten Implementierung der Methode.                                         |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben. Die Struktur muss auch mithilfe `ms_struct` von Verpackung definiert werden, wenn die Microsoft-Compiler nicht verwendet werden.

## <a name="requirements"></a>Anforderungen
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen:

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
