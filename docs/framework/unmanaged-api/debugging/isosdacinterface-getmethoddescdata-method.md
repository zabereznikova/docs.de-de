---
title: ISOSDacInterface::GetMethodDescData-Methode
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
ms.openlocfilehash: cdbf662c664d6c87b2fa17bcb10d735b0f573dd2
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632318"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>ISOSDacInterface::GetMethodDescData-Methode

Ruft die Daten für den angegebenen MethodDesc-Zeiger.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
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
[in] Die Adresse der MethodDesc.

`ip`\
[in] Die IP-Adresse der Methode.

`data`\
[out] Die Daten, die die MethodDesc zugeordnet, wie die internen APIs zurückgegeben wird.

`cRevertedRejitVersions`\
[out] Die Anzahl der wiederhergestellten Rejit-Versionen.

`rgRevertedRejitData`\
[out] Die Daten, die die wiederhergestellten Rejit-Versionen zugeordnet, wie die internen APIs zurückgegeben wird.

`pcNeededRevertedRejitData`\
[out] Die Anzahl der Bytes, die zum Speichern der Daten verknüpft, die mit den wiederhergestellten ReJit-Versionen ist erforderlich.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle und zum 20. Steckplatz der virtuellen Methodentabelle entspricht. Zu deren Verwendung können [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) muss als eine 64-Bit-Ganzzahl ohne Vorzeichen definiert werden.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)
