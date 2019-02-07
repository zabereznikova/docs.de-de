---
title: IXCLRDataMethodInstance-Schnittstelle
ms.date: 02/01/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7185802a3857fcd73c63d097090a2a7809f65279
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825926"
---
# <a name="ixclrdatamethodinstance-interface"></a>IXCLRDataMethodInstance-Schnittstelle

Stellt Methoden zum Abfragen von Informationen zu einer Methodeninstanz bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                                  | Beschreibung                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [GetILAddressMap](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | Ruft den IL-Code mit Adressinformationen für die Zuordnung ab. |
| [GetRepresentativeEntryAddress](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | Ruft die Adresse der repräsentative Eintrag für die systemeigene Kompilierung alle möglichen Einstiegspunkte für eine Methode... |


## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , die über die üblichen Mechanismen der COM-abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
