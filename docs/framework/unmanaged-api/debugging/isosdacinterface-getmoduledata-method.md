---
title: 'Isosdacinterface:: getmoduledata-Methode'
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
ms.openlocfilehash: 14e0eb812c84a0042150345d039451adf178caf1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396921"
---
# <a name="isosdacinterfacegetmoduledata-method"></a>Isosdacinterface:: getmoduledata-Methode

Ruft die Daten ab, die dem Modul entsprechen, das an einer bestimmten Adresse geladen wurde.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a>Parameter

`moduleAddr`\
in Die Adresse des Moduls, für das Informationen abgerufen werden sollen.

`data`\
vorgenommen Die [dacpmoduledata-Struktur](dacpmoduledata-structure.md) , die die Informationen des geladenen Moduls enthalten soll.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode ist Teil der `ISOSDacInterface` -Schnittstelle und entspricht dem 14. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)
