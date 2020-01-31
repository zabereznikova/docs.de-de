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
ms.openlocfilehash: c51825433bbc86c897c097475d5c15c855f6ec8b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790408"
---
# <a name="ixclrdatamethodinstance-interface"></a>IXCLRDataMethodInstance-Schnittstelle

Stellt Methoden bereit, mit denen Informationen zu einer Methoden Instanz abgefragt werden.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| -Methode                                                                                                                  | Beschreibung                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [Getiladdressmap](ixclrdatamethodinstance-getiladdressmap-method.md) | Ruft die Il zum Adressieren von Zuordnungsinformationen ab |
| [GetRepresentativeEntryAddress](ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | Ruft die für die systeminterne Kompilierung aller möglichen Einstiegspunkte einer Methode die am meisten repräsentative Einstiegspunkt Adresse ab. |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
