---
title: IHostSecurityManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44f2272c0f4e1423c222a004559d7bbd58237d82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager-Schnittstelle
Enthält Methoden, die Zugriff auf und die Kontrolle über den Sicherheitskontext des gerade ausgeführten Thread zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Ruft den angeforderten [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host.|  
|[ImpersonateLoggedOnUser-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.|  
|[OpenThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Öffnet das freigegebene Zugriffstoken, das dem aktuellen Thread zugeordnet.|  
|[RevertToSelf-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Beendet den Identitätswechsel der Identität des aktuellen Benutzers und der ursprüngliche Threadtoken zurück.|  
|[SetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Legt den Sicherheitskontext für den gerade ausgeführten Thread fest.|  
|[SetThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Legt einen Handle für den gerade ausgeführten Thread fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host kann alle Codezugriff auf Threadtoken von der common Language Runtime (CLR) und den Benutzercode steuern. Sie können auch sicherstellen, dass vollständige Kontextinformationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird. `IHostSecurityContext`kapselt diese Sicherheitskontextinformationen, die für die CLR nicht transparent ist.  
  
 Die CLR behandelt verwalteten Threadkontext intern. Anschließend fragt es die prozessspezifische `IHostSecurityManager` in den folgenden Situationen:  
  
-   Der Finalizer-Thread, während der Finalizerausführung.  
  
-   Während der Ausführung der Klasse und Module-Konstruktor.  
  
-   Asynchrone Zeitpunkten in der Arbeitsthread in Aufrufen an die [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) Methode.  
  
-   Im Wartungsmodus von e/a-Abschlussports.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
