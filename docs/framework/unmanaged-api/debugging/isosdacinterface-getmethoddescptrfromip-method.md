---
title: ISOSDacInterface::GetMethodDescPtrFromIP-Methode
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828617"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>ISOSDacInterface::GetMethodDescPtrFromIP-Methode

Ruft ab, der Zeiger für die MethodDesc entspricht die Methode, die mit dem angegebenen systemeigenen Anweisungsadresse.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a>Parameter

`ip` [in] Eine Adresse innerhalb der Methode zur Laufzeit.

`ppMD` [out] Die Adresse der `MethodDesc` für die jeweilige Methode.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und mit dem 21. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [ISOSDacInterface-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
