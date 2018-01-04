---
title: IHostControl-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl
helpviewer_keywords: IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d0eaecef4cc34549c7d37953a5c8144bdd983692
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrol-interface"></a>IHostControl-Schnittstelle
Stellt Methoden für das Laden von Assemblys zu konfigurieren und um zu bestimmen, welche hosting vom Host unterstützten Schnittstellen bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetHostManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md)|Ruft einen Schnittstellenzeiger auf dem Host-Implementierung der Schnittstelle mit dem angegebenen `IID`.|  
|[SetAppDomainManager-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)|Benachrichtigt den Host an, dass eine Anwendungsdomäne erstellt wurde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppDomainManager>  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [ICLRControl-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
