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
ms.openlocfilehash: 37f606a67bef79936c81b2a36f12a00d24bd82f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680533"
---
# <a name="ihostsecuritymanager-interface"></a>IHostSecurityManager-Schnittstelle

Stellt Methoden bereit, mit denen der Zugriff auf den Sicherheitskontext des aktuell ausgeführten Threads ermöglicht und gesteuert werden kann.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetSecurityContext-Methode](ihostsecuritymanager-getsecuritycontext-method.md)|Ruft den angeforderten [IHostSecurityContext](ihostsecuritycontext-interface.md) vom Host ab.|  
|[ImpersonateLoggedOnUser-Methode](ihostsecuritymanager-impersonateloggedonuser-method.md)|Fordert die Ausführung von Code mit den Anmelde Informationen der aktuellen Benutzeridentität an.|  
|[OpenThreadToken-Methode](ihostsecuritymanager-openthreadtoken-method.md)|Öffnet das freigegebene Zugriffs Token, das dem aktuellen Thread zugeordnet ist.|  
|[RevertToSelf-Methode](ihostsecuritymanager-reverttoself-method.md)|Beendet den Identitätswechsel der aktuellen Benutzeridentität und gibt das ursprüngliche Thread Token zurück.|  
|[SetSecurityContext-Methode](ihostsecuritymanager-setsecuritycontext-method.md)|Legt den Sicherheitskontext für den aktuell ausgeführten Thread fest.|  
|[SetThreadToken-Methode](ihostsecuritymanager-setthreadtoken-method.md)|Legt ein Handle für den aktuell ausgeführten Thread fest.|  
  
## <a name="remarks"></a>Hinweise  

 Ein Host kann den gesamten Code Zugriff auf Thread Token sowohl durch den Common Language Runtime (CLR) als auch durch den Benutzercode steuern. Außerdem kann sichergestellt werden, dass die umfassenden Sicherheitskontext Informationen über asynchrone Vorgänge oder Code Punkte mit eingeschränktem Code Zugriff übermittelt werden. `IHostSecurityContext` kapselt diese Sicherheitskontext Informationen, die für die CLR nicht transparent sind.  
  
 Die CLR verarbeitet den verwalteten Thread Kontext intern. Die prozessspezifische Abfrage wird `IHostSecurityManager` in den folgenden Situationen abgefragt:  
  
- Im Finalizerthread während der Ausführung des Finalizers.  
  
- Während der Ausführung von Klassen-und Modulkonstruktoren.  
  
- Bei asynchronen Punkten im Arbeits Thread in Aufrufen der [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) -Methode.  
  
- Bei der Wartung von e/a-Abschlussports.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IHostSecurityContext-Schnittstelle](ihostsecuritycontext-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
