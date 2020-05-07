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
ms.openlocfilehash: e10d1792a8dc0b57ddd121ec09854e8e1824cade
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860804"
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

## <a name="members"></a>Members

| Member    | BESCHREIBUNG                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Adresse des Modul Objekts.                                           |
| `File`    | Ein Zeiger auf die portable ausführbare Datei (PE).                       |
| `ilBase`  | Die Adresse der Basis des geladenen Bilds.                                 |
| `payLoad` | Ein Nutz Last Puffer für zusätzliche Modul Informationen, die von der Laufzeit verwendet werden. |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben.

## <a name="requirements"></a>Anforderungen
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen:

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
