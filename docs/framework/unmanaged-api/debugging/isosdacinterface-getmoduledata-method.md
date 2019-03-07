---
title: ISOSDacInterface::GetModuleData-Methode
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: ed151f998ed7d28ba7ae170839ce2fa3a1ee6135
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490449"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>ISOSDacInterface::GetModuleData-Methode

Die Daten, die für das Modul geladen, die an einer bestimmten Adresse abruft.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Parameter

`moduleAddr`\
[in] Die Adresse des Moduls zum Abrufen von Informationen für.

`data`\
[out] Die [DacpModuleData Struktur](dacpmoduledata-structure.md) , die die Informationen des geladenen Moduls enthalten soll.


## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der `ISOSDacInterface` Schnittstelle, und mit dem 13. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)