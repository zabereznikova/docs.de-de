---
title: 'Isosdacinterface:: getmethoddescdata-Methode'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421019"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Isosdacinterface:: getmethoddescdata-Methode

Ruft die Daten für den angegebenen methodde-Zeiger ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a>Parameter

`methodDesc`\
in Die Adresse von methoddebug.

`ip`\
in Die IP-Adresse der Methode.

`data`\
vorgenommen Die der methoddebug zugeordneten Daten, die von den internen APIs zurückgegeben werden.

`cRevertedRejitVersions`\
vorgenommen Die Anzahl der zurückgesetzten ReJIT-Versionen.

`rgRevertedRejitData`\
vorgenommen Die Daten, die den wiederhergestellten ReJIT-Versionen zugeordnet sind, die von den internen APIs zurückgegeben werden.

`pcNeededRevertedRejitData`\
vorgenommen Die Anzahl der Bytes, die erforderlich sind, um die Daten zu speichern, die den wiederhergestellten ReJIT-Versionen zugeordnet sind.

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der `ISOSDacInterface` -Schnittstelle und entspricht dem 21. Slot der Tabelle der virtuellen Methode. Um Sie verwenden zu können, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) muss als eine 64-Bit-Ganzzahl ohne Vorzeichen definiert werden.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)
