---
title: IHostSecurityManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2637f54fcddaf82d30527d7318503a2b9aa740dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565838"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager-Schnittstelle
Enthält Methoden, die Zugriff auf und Kontrolle über den Sicherheitskontext des gerade ausgeführten Threads zu ermöglichen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Ruft die angeforderte [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host.|  
|[ImpersonateLoggedOnUser-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Anforderungen, die Code mit den Anmeldeinformationen der Identität des aktuellen Benutzers ausgeführt werden.|  
|[OpenThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Öffnet das discretionary Access Control-Token, das den aktuellen Thread zugeordnet.|  
|[RevertToSelf-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Beendet den Identitätswechsel der Identität des aktuellen Benutzers und gibt das Threadtoken der ursprüngliche zurück.|  
|[SetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Legt den Sicherheitskontext für den aktuell ausgeführten Thread fest.|  
|[SetThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Legt einen Handle für den aktuell ausgeführten Thread fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host kann alle Codezugriff auf Threadtoken durch die common Language Runtime (CLR) und den Benutzercode steuern. Sie können auch sicherstellen, dass vollständige Informationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird. `IHostSecurityContext` kapselt dieses Sicherheitskontextinformationen, die für die CLR nicht transparent ist.  
  
 Die CLR behandelt die intern verwalteten Thread-Kontext. Die Prozess-spezifischen Abfragen `IHostSecurityManager` in den folgenden Situationen:  
  
-   Der Finalizer-Thread, während der Finalizerausführung.  
  
-   Während der Ausführung der Klasse "und"-Modul-Konstruktor.  
  
-   Auf den Arbeitsthread, in Aufrufen von asynchronen Zeitpunkten der [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) Methode.  
  
-   Im Wartungsmodus von e/a-Abschlussports.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
