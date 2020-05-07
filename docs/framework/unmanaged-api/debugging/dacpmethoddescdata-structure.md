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
ms.openlocfilehash: d623fe862eaf5902fd89d0e512dd07f73a03246f
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860821"
---
# <a name="dacpmethoddescdata-structure"></a>DacpMethodDescData-Struktur

Definiert einen Transport Puffer für die Laufzeitinformationen einer Methode.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
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

## <a name="members"></a>Members

| Member                       | BESCHREIBUNG                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | Gibt an, ob die Laufzeit nativen Code für die angegebene Instanziierung der Methode verfügbar ist. |
| `bIsDynamic`                 | Gibt an, ob die Methode mithilfe der Lightweight-Codegenerierung dynamisch generiert wird.           |
| `wSlotNumber`                | Die Slotnummer der Methode in der Methoden Tabelle.                                                   |
| `NativeCodeAddr`             | Die ursprüngliche Native Adresse der Methode.                                                            |
| `data`                       | Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird.                                             |
| `MethodDescPtr`              | Zeiger auf den `MethodDesc` in der Laufzeit.                                                     |
| `nativeCodeInfo`             | Zeiger auf einen Puffer, der intern von der Laufzeit verwendet wird, um Methoden zu verfolgen.                            |
| `moduleInfo`                 | Zeiger auf einen Puffer, der von der Common Language Runtime für Modul Informationen intern verwendet wird.                      |
| `MDToken`                    | Token, das mit der angegebenen Methode verknüpft ist.                                                         |
| `payloadGC`                  | Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.                          |
| `payloadGC2`                 | Zeiger auf einen Garbage Collection Puffer, der intern von der Laufzeit verwendet wird.                          |
| `managedDynamicMethodObject` | Wenn die Methode dynamisch ist, verwendet die Common Language Runtime diesen Puffer intern für die Informations Verfolgung.     |
| `requestedIP`                | Wird verwendet, um die Struktur pro Anforderung aufzufüllen, wenn eine systemeigene Code Adresse angegeben ist.                    |
| `rejitDataCurrent`           | Informationen zur neuesten instrumentierten Version der-Methode.                                   |
| `rejitDataRequested`         | ReJIT-Informationen für die angeforderte Native Adresse.                                             |
| `cJittedRejitVersions`       | Gibt an, wie oft die Methode durch Instrumentation erneut generiert wurde.                           |

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
- [Allgemeine Datentypen](../common-data-types-unmanaged-api-reference.md)
