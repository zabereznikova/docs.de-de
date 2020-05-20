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
ms.openlocfilehash: d546cda5c68732e75550a3de286089f7df261c91
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420902"
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

## <a name="remarks"></a>Hinweise

Die bereitgestellte Methode ist Teil der- [ `IXCLRDataMethodInstance` Schnittstelle](ixclrdatamethodinstance-interface.md) und entspricht dem 20. Slot der Tabelle der virtuellen Methode.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
