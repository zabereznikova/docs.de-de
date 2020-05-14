---
title: 'Ixclrdatamethodinstance:: getrepresentativeentryaddress-Methode'
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress
helpviewer.keywords:
- IXCLRDataMethodInstance::GetRepresentativeEntryAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: d9f9e16d243c0f3b45ac24776caea5bb9c32dcc1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395750"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>Ixclrdatamethodinstance:: getrepresentativeentryaddress-Methode

Ruft die für die systeminterne Kompilierung aller möglichen Einstiegspunkte einer Methode die am meisten repräsentative Einstiegspunkt Adresse ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Parameter

`addr`\
vorgenommen Die Adresse des repräsentativsten systemeigenen Einstiegs Punkts für die Methode.

## <a name="remarks"></a>Bemerkungen

Die bereitgestellte Methode ist Teil der- [ `IXCLRDataMethodInstance` Schnittstelle](ixclrdatamethodinstance-interface.md) und entspricht dem 20. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
