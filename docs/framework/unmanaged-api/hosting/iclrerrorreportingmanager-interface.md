---
title: ICLRErrorReportingManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRErrorReportingManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRErrorReportingManager
helpviewer_keywords: ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590cd87d6a566e9c8c3819fd1b250997938e9c35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrerrorreportingmanager-interface"></a>ICLRErrorReportingManager-Schnittstelle
Enthält Methoden, mit die den Host benutzerdefinierte Stapeldumps für die Fehlerberichterstattung konfigurieren können.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[BeginCustomDump-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|Gibt die Konfiguration des benutzerdefinierten Stapeldumps für die Fehlerberichterstattung.|  
|[EndCustomDump-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|Löscht die Konfiguration des benutzerdefinierten Stapeldumps, die durch einen früheren Aufruf festgelegt wurde `BeginCustomDump`.|  
|[GetBucketParametersForCurrentException-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `BeginCustomDump` Methode legt die Konfiguration des benutzerdefinierten Stapeldumps fest. Die `EndCustomDump` -Methode löscht die benutzerdefinierte Stapeldumpkonfiguration und alle zugeordneten Zustand freigibt. Es sollte aufgerufen werden, nachdem das benutzerdefinierte Speicherabbild abgeschlossen ist.  
  
> [!IMPORTANT]
>  Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ECustomDumpItemKind-Enumeration](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
