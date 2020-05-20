---
title: ISOSDacInterface-Schnittstelle
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420967"
---
# <a name="isosdacinterface-interface"></a>ISOSDacInterface-Schnittstelle

Stellt Hilfsmethoden für den Zugriff auf Daten aus bereit `SOS` .

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                               | BESCHREIBUNG                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [GetMethodDescData](isosdacinterface-getmethoddescdata-method.md) | Ruft die Daten für den angegebenen methodde-Zeiger ab. |
| [GetMethodDescPtrFromIP](isosdacinterface-getmethoddescptrfromip-method.md) | Ruft den Zeiger von MethodDesc entsprechend der Methode ab, die die angegebene Native Anweisungs Adresse enthält. |
| [GetModuleData](isosdacinterface-getmoduledata-method.md)| Ruft die Daten ab, die dem Modul entsprechen, das an einer bestimmten Adresse geladen wurde. |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `436f00f2-b42a-4b9f-870c-e73db66ae930` , die über die üblichen com-Mechanismen abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debugschnittstellen](debugging-interfaces.md)
