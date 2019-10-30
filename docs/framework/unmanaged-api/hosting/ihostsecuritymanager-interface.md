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
ms.openlocfilehash: 9b7cc41848e41976f388e38bf22c9ea0f90abbae
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121478"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager-Schnittstelle
Stellt Methoden bereit, mit denen der Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglicht und gesteuert werden kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Ruft den angeforderten [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) vom Host ab.|  
|[ImpersonateLoggedOnUser-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Fordert die Ausführung von Code mit den Anmelde Informationen der aktuellen Benutzeridentität an.|  
|[OpenThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Öffnet das freigegebene Zugriffs Token, das dem aktuellen Thread zugeordnet ist.|  
|[RevertToSelf-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Beendet den Identitätswechsel der aktuellen Benutzeridentität und gibt das ursprüngliche Thread Token zurück.|  
|[SetSecurityContext-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Legt den Sicherheitskontext für den aktuell ausgeführten Thread fest.|  
|[SetThreadToken-Methode](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Legt ein Handle für den aktuell ausgeführten Thread fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den Common Language Runtime (CLR) als auch durch den Benutzercode steuern. Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden. `IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die CLR nicht transparent sind.  
  
 Die CLR verarbeitet den verwalteten Thread Kontext intern. Die prozessspezifischen `IHostSecurityManager` werden in den folgenden Situationen abgefragt:  
  
- Im Finalizerthread während der Ausführung des Finalizers.  
  
- Während der Ausführung von Klassen-und Modulkonstruktoren.  
  
- Bei asynchronen Punkten im Arbeits Thread in Aufrufen der [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) -Methode.  
  
- Bei der Wartung von e/a-Abschlussports.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IHostSecurityContext-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
