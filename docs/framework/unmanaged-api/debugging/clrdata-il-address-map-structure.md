---
title: CLRDATA_IL_ADDRESS_MAP-Struktur
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179374"
---
# <a name="clrdata_il_address_map-structure"></a>CLRDATA_IL_ADDRESS_MAP-Struktur

Definiert eine IL-zu-Adresszuordnung.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a>Members

| Member         | Beschreibung                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | IL-Offset für den enthaltenen Adressbereich              |
| `startAddress` | Die Startadresse des Bereichs.                        |
| `endAddress`   | Die Endadresse des Bereichs.                          |
| `type`         | Der Typ der Daten. Dieser Wert wird derzeit nicht verwendet. |

## <a name="remarks"></a>Bemerkungen

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um sie zu verwenden, definieren Sie `CLRDATA_ADDRESS` die oben angegebene Struktur, wobei es sich um eine 64-Bit-Ganzzahl ohne Vorzeichen handelt.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Kopfzeile:** nichts  
**Bibliothek:** Keine **.NET Framework-Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [CLRDataSourceType-Enumeration](clrdatasourcetype-enumeration.md)
- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
