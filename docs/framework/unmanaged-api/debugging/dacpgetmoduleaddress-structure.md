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
ms.openlocfilehash: e460264e2393858c028ba51aec4a4f2c01649994
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860828"
---
# <a name="dacpgetmoduleaddress-structure"></a>DacpGetModuleAddress-Struktur

Definiert den Container für eine Modul Adress Anforderung.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a>Members

| Member      | BESCHREIBUNG                |
| ----------- | -------------------------- |
| `ModulePtr` | Der Zeiger auf das Modul. |

## <a name="methods"></a>Methoden

| Methode                                                                                               | BESCHREIBUNG                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [Anforderung](dacpgetmoduleaddress-request-method.md) | Führt eine Anforderung aus, um die-Struktur aus der angegebenen Laufzeitstruktur aufzufüllen. |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien verfügbar gemacht. Um es zu verwenden, definieren Sie die Struktur wie oben angegeben `CLRDATA_ADDRESS` , wobei eine 64-Bit-Ganzzahl ohne Vorzeichen ist.

## <a name="requirements"></a>Anforderungen
**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen:

- [Debuggen](index.md)
- [Debuggen von Strukturen](debugging-structures.md)
