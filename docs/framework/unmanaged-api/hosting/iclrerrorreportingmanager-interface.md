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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155986"
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager-Schnittstelle
Bietet Methoden, mit die den Host benutzerdefinierte stapelabbilder für die Fehlerberichterstattung konfigurieren zu können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginCustomDump-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Gibt die Konfiguration des benutzerdefinierten Stapeldumps für die Fehlerberichterstattung.|  
|[EndCustomDump-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Löscht die Konfiguration des benutzerdefinierten Dump der von einem früheren Aufruf festgelegte `BeginCustomDump`.|  
|[GetBucketParametersForCurrentException-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `BeginCustomDump` Methode legt die Konfiguration des benutzerdefinierten Dump fest. Die `EndCustomDump` Methode löscht die benutzerdefinierte Stapeldumpkonfiguration und alle zugeordneten Zustand freigibt. Es sollte aufgerufen werden, nachdem das benutzerdefinierte Abbild abgeschlossen ist.  
  
> [!IMPORTANT]
>  Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ECustomDumpItemKind-Enumeration](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
