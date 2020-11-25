---
title: DacpModuleData-Struktur
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 5d27ba2de9ff6ed184b6ddf50a517d0dae7715f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723050"
---
# <a name="dacpmoduledata-structure"></a>DacpModuleData-Struktur

Definiert einen Transport Puffer für die Laufzeitinformationen eines Moduls.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Member

| Member    | BESCHREIBUNG                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Adresse des Modul Objekts.                                           |
| `File`    | Ein Zeiger auf die portable ausführbare Datei (PE).                       |
| `ilBase`  | Die Adresse der Basis des geladenen Bilds.                                 |
| `payLoad` | Ein Nutz Last Puffer für zusätzliche Modul Informationen, die von der Laufzeit verwendet werden. |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
