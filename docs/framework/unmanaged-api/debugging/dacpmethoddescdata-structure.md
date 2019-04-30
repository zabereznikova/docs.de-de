---
title: DacpMethodDescData-Struktur
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965905"
---
# <a name="dacpmethoddescdata-structure"></a>DacpMethodDescData-Struktur

Definiert einen Transport-Puffer für die Runtime-Informationen von einer Methode an.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a>Member

| Member                       | Beschreibung                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Gibt an, ob es sich bei die Laufzeit systemeigenen Code für die angegebene Instanziierungen der Methode verfügbar ist. |
| `bIsDynamic`                 | Gibt an, wenn die Methode über vereinfachter codegenerierung dynamisch generiert wird.           |
| `wSlotNumber`                | Der Methode die Slotnummer in die Methodentabelle.                                                   |
| `NativeCodeAddr`             | Erste systemeigene Adresse der Methode.                                                            |
| `data`                       | Zeiger auf einen Puffer, die intern von der Laufzeit verwendet.                                             |
| `MethodDescPtr`              | Zeiger auf die `MethodDesc` in der Runtime.                                                     |
| `nativeCodeInfo`             | Zeiger auf einen Puffer, die von der Laufzeit intern verwendet wird, um Methoden zu verfolgen.                            |
| `moduleInfo`                 | Zeiger auf einen Puffer, die von der Runtime für Modulinformationen wird intern verwendet.                      |
| `MDToken`                    | Token, die die angegebene Methode zugeordnet werden.                                                         |
| `payloadGC`                  | Zeiger auf einen Garbage Collection-Puffer, die intern von der Laufzeit verwendet.                          |
| `payloadGC2`                 | Zeiger auf einen Garbage Collection-Puffer, die intern von der Laufzeit verwendet.                          |
| `managedDynamicMethodObject` | Wenn die Methode dynamisch ist, verwendet die Runtime diesen Puffer für die Funktion zur nachverfolgung von intern.     |
| `requestedIP`                | Zum Auffüllen der Struktur pro Anforderung, wenn eine native Adresse verwendet.                    |
| `rejitDataCurrent`           | Informationen über die neuesten instrumentierte Version der Methode.                                   |
| `rejitDataRequested`         | ReJIT-Informationen für die angeforderte systemeigene Adresse.                                             |
| `cJittedRejitVersions`       | Anzahl von Wiederholungen, die die Methode Rejitted durch die Instrumentierung wurde.                           |

## <a name="remarks"></a>Hinweise

Diese Struktur befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Definieren Sie die Struktur wie oben angegeben, um es zu verwenden.

## <a name="requirements"></a>Anforderungen
**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Allgemeine Datentypen](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
