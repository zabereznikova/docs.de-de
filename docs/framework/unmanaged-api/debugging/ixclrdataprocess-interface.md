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
ms.openlocfilehash: 6a6def8fc10f04b89aa8d8c735025b01f9b6ddfb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420759"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess-Schnittstelle

Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                                                               | BESCHREIBUNG                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Ruft ein `AppDomain` in einem Prozess anhand seiner eindeutigen ID ab.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Stellt ein Handle zum Auflisten der Module eines Prozesses bereit.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Listet die Module dieses Prozesses auf.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der modulenumeration verwendet werden.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Stellt ein Handle zum Auflisten der Methoden Instanzen von bereit, `AppDomain` beginnend bei einer angegebenen Adresse. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Listet die Methoden Instanzen dieses Prozesses auf, beginnend bei einem Adress Offset.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Gibt die von internen Iteratoren verwendeten Ressourcen frei, die während der instanzenumeration verwendet werden.             |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` , die über die üblichen com-Mechanismen abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debugschnittstellen](debugging-interfaces.md)
