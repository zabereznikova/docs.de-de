---
title: DacpGetModuleAddress-Struktur
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 145b06f89b45b165b9d6329a4c16ac5739406113
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739181"
---
# <a name="dacpgetmoduleaddress-structure"></a>DacpGetModuleAddress-Struktur

Definiert den Container für eine Anforderung zum modulimport Adresse an.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Member

| Member      | Beschreibung                |
| ----------- | -------------------------- |
| `ModulePtr` | Der Zeiger auf das Modul. |

## <a name="methods"></a>Methoden

| Methode                                                                                               | Beschreibung                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Anforderung](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | Führt eine Anforderung zum Auffüllen der Struktur aus der angegebenen Runtime-Struktur. |

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
