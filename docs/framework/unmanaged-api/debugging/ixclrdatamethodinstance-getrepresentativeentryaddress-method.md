---
title: IXCLRDataMethodInstance::GetRepresentativeEntryAddress-Methode
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
ms.openlocfilehash: 5c79e916a06e796fc87b57eb949cccda77b8a9bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744666"
---
# <a name="ixclrdatamethodinstancegetrepresentativeentryaddress-method"></a>IXCLRDataMethodInstance::GetRepresentativeEntryAddress-Methode

Ruft die Adresse der repräsentativsten Eintrag für die systemeigene Kompilierung alle möglichen Einstiegspunkte für eine Methode ab.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetRepresentativeEntryAddress(
    [out] CLRDATA_ADDRESS* addr
);
```

## <a name="parameters"></a>Parameter

`addr`\
[out] Die Adresse des dem repräsentativsten systemeigener Einstiegspunkt für die Methode.

## <a name="remarks"></a>Hinweise

Die angegebene Methode ist Teil der [ `IXCLRDataMethodInstance` Schnittstelle](ixclrdatamethodinstance-interface.md) und mit dem 19. Steckplatz der virtuellen Methodentabelle entspricht.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keiner  
**Bibliothek:** Keiner  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)
