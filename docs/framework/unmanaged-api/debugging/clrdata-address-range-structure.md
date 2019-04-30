---
title: CLRDATA_ADDRESS_RANGE-Struktur
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961304"
---
# <a name="clrdataaddressrange-structure"></a>CLRDATA_ADDRESS_RANGE-Struktur

Definiert einen Adressbereich an.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a>Member

| Member         | Beschreibung                     |
| -------------- | ------------------------------- |
| `startAddress` | Die Startadresse des Bereichs. |
| `endAddress`   | Die letzte Adresse des Bereichs.   |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, in dem `CLRDATA_ADDRESS` ist eine 64-Bit-Ganzzahl ohne Vorzeichen.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
