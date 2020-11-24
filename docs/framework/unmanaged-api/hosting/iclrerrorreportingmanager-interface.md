---
title: ICLRErrorReportingManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
ms.openlocfilehash: d3816c8a3b6204b053505aa888eb28d696f8990b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677843"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager-Schnittstelle

Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte stackdumps für die Fehlerberichterstattung zu konfigurieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[BeginCustomDump-Methode](iclrerrorreportingmanager-begincustomdump-method.md)|Gibt die Konfiguration von benutzerdefinierten stackdumps für die Fehlerberichterstattung an.|  
|[EndCustomDump-Methode](iclrerrorreportingmanager-endcustomdump-method.md)|Löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren-Aufrufsatz festgelegt wurde `BeginCustomDump` .|  
|[GetBucketParametersForCurrentException-Methode](iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Ruft den Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.|  
  
## <a name="remarks"></a>Hinweise  

 Die- `BeginCustomDump` Methode legt die benutzerdefinierte Stapel Sicherungs Konfiguration fest. Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration und gibt jeden zugeordneten Zustand frei. Er sollte aufgerufen werden, nachdem der benutzerdefinierte Dump fertiggestellt wurde.  
  
> [!IMPORTANT]
> Wenn Sie den Vorgang nicht aufzurufen, ist der `EndCustomDump` Speicherfehler  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ECustomDumpItemKind-Enumeration](ecustomdumpitemkind-enumeration.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
