---
title: 'Isosdacinterface:: getmethoddescptrfromip-Methode'
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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396927"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a>Isosdacinterface:: getmethoddescptrfromip-Methode

Ruft den Zeiger von MethodDesc entsprechend der Methode ab, die die angegebene Native Anweisungs Adresse enthält.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a>Parameter

`ip`\
in Eine Adresse innerhalb der Methode zur Laufzeit.

`ppMD`\
vorgenommen Die Adresse der `MethodDesc` für die jeweilige Methode.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode ist Teil der- [ `ISOSDacInterface` Schnittstelle](isosdacinterface-interface.md) und entspricht dem 22. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)
