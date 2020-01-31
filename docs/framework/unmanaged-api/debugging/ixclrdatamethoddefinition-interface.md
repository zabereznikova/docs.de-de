---
title: IXCLRDataMethodDefinition-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition Interface
helpviewer.keywords:
- IXCLRDataMethodDefinition Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 708c681a98113a406249a360c2fc81087e5b97f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790429"
---
# <a name="ixclrdatamethoddefinition-interface"></a>IXCLRDataMethodDefinition-Schnittstelle

Stellt Methoden zum Abfragen von Informationen über eine Methoden Definition bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

Die folgenden Methoden sind einige der Methoden, die in der-Schnittstelle verfügbar sind.

| -Methode                                                                                                                          | Beschreibung                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| [StartEnumInstances](ixclrdatamethoddefinition-startenuminstances-method.md) | Stellt ein Handle für die Enumeration von Methoden Instanzen für eine angegebene `IXCLRDataAppDomain`bereit. |
| [Enuminstance](ixclrdatamethoddefinition-enuminstance-method.md)             | Listet die Instanzen dieser Methoden Definition auf.                                         |
| [Enumuminstance](ixclrdatamethoddefinition-endenuminstances-method.md)     | Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.         |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`AAF60008-FB2C-420b-8FB1-42D244A54A97` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
