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
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179186"
---
# <a name="dacpmoduledata-structure"></a>DacpModuleData-Struktur

Definiert einen Transportpuffer für die Laufzeitinformationen eines Moduls.

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

| Member    | Beschreibung                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Adresse des Modulobjekts.                                           |
| `File`    | Ein Zeiger auf die portable ausführbare Datei (PE).                       |
| `ilBase`  | Die Adresse der Basis des geladenen Bildes.                                 |
| `payLoad` | Ein Nutzlastpuffer für zusätzliche Modulinformationen, die von der Laufzeit verwendet werden. |

## <a name="remarks"></a>Bemerkungen

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um sie zu verwenden, definieren Sie die oben angegebene Struktur.

## <a name="requirements"></a>Requirements (Anforderungen)
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Kopfzeile:** nichts  
**Bibliothek:** nichts  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
