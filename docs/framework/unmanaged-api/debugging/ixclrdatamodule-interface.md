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
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790395"
---
# <a name="ixclrdatamodule-interface"></a>IXCLRDataModule Interface-Schnittstelle

Stellt Methoden zum Abfragen von Informationen über ein geladenes Modul bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| -Methode                                                                                                                                | Beschreibung                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Ruft die Methoden Definition ab, die einem angegebenen Metadatentoken entspricht. |
| [Anforderung](ixclrdatamodule-request-method.md)                                       | Fordert an, den mit den Modul Daten angegebenen Puffer aufzufüllen.       |
| [GetVersionId](ixclrdatamodule-getversionid-method.md)                             | Ruft die Versions-ID des Moduls ab.                                       |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich innerhalb der Laufzeit und wird nicht durch Header oder Bibliotheksdateien offengelegt. Dabei handelt es sich jedoch um eine COM-Schnittstelle, die von `IUnknown` mit GUID-`88E32849-0A0A-4cb0-9022-7CD2E9E139E2` abgeleitet ist, die über die üblichen com-Mechanismen abgerufen werden können.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Gar  
**Bibliothek:** Gar  
**.NET Framework Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](index.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
