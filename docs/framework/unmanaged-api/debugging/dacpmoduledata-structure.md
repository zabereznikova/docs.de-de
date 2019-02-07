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
ms.openlocfilehash: db3fdaa768e3d1b445f08c3964521570631f0965
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828621"
---
# <a name="dacpmoduledata-structure"></a>DacpModuleData-Struktur

Definiert einen Transport-Puffer für die Runtime-Informationen des Moduls an.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a>Member

| Member    | Beschreibung                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | Die Adresse des Modulobjekts.                                           |
| `File`    | Ein Zeiger auf die Datei (portable Executable)-Datei.                       |
| `ilBase`  | Die Adresse des geladenen Bilds der Basiswert.                                 |
| `payLoad` | Ein Puffer Nutzlast zusätzlicher Module-Informationen, die von der Laufzeit verwendet wird. |


## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.

## <a name="requirements"></a>Anforderungen
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
