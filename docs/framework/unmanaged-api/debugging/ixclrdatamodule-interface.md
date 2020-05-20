---
title: IXCLRDataModule Interface-Schnittstelle
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3c2bc771c0a131329b9403c99a33ca7b79023771
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420850"
---
# <a name="ixclrdatamodule-interface"></a>IXCLRDataModule Interface-Schnittstelle

Stellt Methoden zum Abfragen von Informationen über ein geladenes Modul bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                                                | BESCHREIBUNG                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Ruft die Methoden Definition ab, die einem angegebenen Metadatentoken entspricht. |
| [Anforderung](ixclrdatamodule-request-method.md)                                       | Fordert an, den mit den Modul Daten angegebenen Puffer aufzufüllen.       |
| [GetVersionId](ixclrdatamodule-getversionid-method.md)                             | Ruft die Versions-ID des Moduls ab.                                       |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit der GUID abgeleitet ist `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , die über die üblichen com-Mechanismen abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debugschnittstellen](debugging-interfaces.md)
