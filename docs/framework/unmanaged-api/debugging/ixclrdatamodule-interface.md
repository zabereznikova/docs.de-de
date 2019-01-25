---
title: IXCLRDataModule-Schnittstelle
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
ms.openlocfilehash: c8d6e36687fd43bbc59304eee64dd42eb78101e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676522"
---
# <a name="ixclrdatamodule-interface"></a>IXCLRDataModule-Schnittstelle

Stellt Methoden zum Abfragen von Informationen zu einem geladenen Modul bereit.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a>Methoden

| Methode                                                                                                                                | Beschreibung                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [GetMethodDefinitionByToken](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | Ruft die Definition der Methode für einen angegebenen Metadatentoken ab. |
| [Anforderung](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | Anforderungen zum Auffüllen mit Daten für das Modul des angegebenen Puffers.       |
| [GetVersionId](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | Ruft die Modul Versions-ID                                       |

## <a name="remarks"></a>Hinweise

Diese Schnittstelle befindet sich in der Common Language Runtime und nicht über Header oder Bibliotheksdateien verfügbar gemacht. Es ist jedoch eine COM-Schnittstelle, die von abgeleitet `IUnknown` mit GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , die über die üblichen Mechanismen der COM-abgerufen werden kann.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
**Header:** Keine  
**Bibliothek:** Keine  
**.NET Framework-Versionen:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Siehe auch

- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
