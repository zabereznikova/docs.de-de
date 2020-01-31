---
title: IXCLRDataProcess-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess Interface
helpviewer.keywords:
- IXCLRDataProcess Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a5d707d61513b030e5968af28db3c2a606e4419b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790372"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess-Schnittstelle

Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| -Methode                                                                                                                                               | Beschreibung                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Ruft eine `AppDomain` in einem Prozess anhand der eindeutigen ID ab.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.                                        |
| [Enummodule](ixclrdataprocess-enummodule-method.md)                                               | Listet die Module dieses Prozesses auf.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Stellt ein Handle zum Auflisten der Methoden Instanzen von `AppDomain` beginnend bei einer angegebenen Adresse bereit. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.             |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`5c552ab6-fc09-4cb3-8e36-22fa03c798b7` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).   
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
