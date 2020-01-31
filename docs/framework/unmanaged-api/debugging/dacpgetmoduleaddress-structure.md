---
title: Dacpgetmoduleaddress-Struktur
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
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789208"
---
# <a name="dacpgetmoduleaddress-structure"></a>Dacpgetmoduleaddress-Struktur

Definiert den Container für eine Modul Adress Anforderung.

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

| -Methode                                                                                               | Beschreibung                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Anforderung](dacpgetmoduleaddress-request-method.md) | Führt eine Anforderung aus, um die-Struktur aus der angegebenen Laufzeitstruktur aufzufüllen. |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben, wobei `CLRDATA_ADDRESS` eine 64-Bit-Ganzzahl ohne Vorzeichen ist.

## <a name="requirements"></a>-Anforderungen
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
