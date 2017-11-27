---
title: ICorConfiguration-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorConfiguration
helpviewer_keywords: ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6bc66abf28e90d858d993bd62e9c67f840af137b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration-Schnittstelle
Stellt Methoden für die common Language Runtime (CLR) konfigurieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddDebuggerSpecialThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Zeigt den Debugdiensten an, dass ein bestimmter Thread fortgesetzt werden, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat darf.|  
|[SetDebuggerThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Legt die Rückrufschnittstelle, die der Debugdienste für das Debuggen aufrufen, wenn CLR-Threads blockiert und freigegeben werden.|  
|[SetGCHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Legt die Rückrufschnittstelle vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.|  
|[SetGCThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Legt die Rückrufschnittstelle für die Planung von Threads für nicht-Runtime-Aufgaben, die andernfalls für eine Garbagecollection blockiert werden würde.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
