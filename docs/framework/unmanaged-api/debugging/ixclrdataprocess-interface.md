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
ms.openlocfilehash: e7e53615e38d0ab76f9e7c0a753be3c13780057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178375"
---
# <a name="ixclrdataprocess-interface"></a>IXCLRDataProcess-Schnittstelle

Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                                                               | Beschreibung                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| [GetAppDomainByUniqueId](ixclrdataprocess-getappdomainbyuniqueid-method.md)                       | Ruft `AppDomain` einen in einem Prozess durch seine eindeutige ID ab.                                              |
| [StartEnumModules](ixclrdataprocess-startenummodules-method.md)                                   | Stellt ein Handle zum Aufzählen der Module eines Prozesses bereit.                                        |
| [EnumModule](ixclrdataprocess-enummodule-method.md)                                               | Zählt die Module dieses Prozesses auf.                                                         |
| [EndEnumModules](ixclrdataprocess-endenummodules-method.md)                                       | Gibt die Ressourcen frei, die von internen Iteratoren verwendet werden, die während der Modulenumeration verwendet werden.               |
| [StartEnumMethodInstancesByAddress](ixclrdataprocess-startenummethodinstancesbyaddress-method.md) | Stellt ein Handle bereit, um die `AppDomain` Methodeninstanzen des Startens an einer bestimmten Adresse aufzuzählen. |
| [EnumMethodInstanceByAddress](ixclrdataprocess-enummethodinstancebyaddress-method.md)             | Zählt die Methodeninstanzen dieses Prozesses auf, beginnend mit einem Adressoffset.                  |
| [EndEnumMethodInstancesByAddress](ixclrdataprocess-endenummethodinstancesbyaddress-method.md)     | Gibt die Ressourcen frei, die von internen Iteratoren verwendet werden, die während der Instanzenumeration verwendet werden.             |

## <a name="remarks"></a>Bemerkungen

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht über Header oder Bibliotheksdateien verfügbar gemacht. Es handelt sich jedoch um eine COM-Schnittstelle, die `IUnknown` mit GUID `5c552ab6-fc09-4cb3-8e36-22fa03c798b7` abstammt und über die üblichen COM-Mechanismen abgerufen werden kann.

## <a name="requirements"></a>Requirements (Anforderungen)

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).
**Kopfzeile:** nichts  
**Bibliothek:** nichts  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Weitere Informationen

- [Debuggen](index.md)
- [Debugschnittstellen](debugging-interfaces.md)
