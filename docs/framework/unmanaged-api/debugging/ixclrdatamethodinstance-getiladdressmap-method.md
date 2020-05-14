---
title: 'Ixclrdatamethodinstance:: getiladdressmap-Methode'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7c4dcf59ce159434d5012120043f5bb548d49731
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396818"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a>Ixclrdatamethodinstance:: getiladdressmap-Methode

Ruft die Il zum Adressieren von Zuordnungsinformationen ab

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

## <a name="parameters"></a>Parameter

`mapLen`\
in Die Länge des bereitgestellten Maps-Arrays.

`mapNeeded`\
vorgenommen Die Anzahl der Karten Einträge, die von der Methode benötigt werden.

`maps`\
[out, size_is (maplen)] Das Array zum Speichern der Karten Einträge.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode ist Teil der `IXCLRDataMethodInstance` -Schnittstelle und entspricht dem 15. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
