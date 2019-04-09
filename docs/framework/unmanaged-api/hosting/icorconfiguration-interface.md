---
title: ICorConfiguration-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorConfiguration
helpviewer_keywords:
- ICorConfiguration interface [.NET Framework hosting]
ms.assetid: aaf96116-372b-4538-afb1-9e0fcdac1f98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b24e278b3449d0e17377495cef0f445c1ebed734
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149811"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration-Schnittstelle
Stellt Methoden für die common Language Runtime (CLR) konfigurieren.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddDebuggerSpecialThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Zeigt das Debuggen von Diensten an, dass ein bestimmter Thread darf weiterhin ausgeführt, während der Debugger eine Anwendung, die während des Szenarios des verwalteten oder nicht verwalteten Debuggens beendet hat.|  
|[SetDebuggerThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Legt die Rückrufschnittstelle, die die Debuggen von Diensten für das Debuggen von aufrufen, wenn die CLR-Threads blockiert und freigegeben werden.|  
|[SetGCHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Legt die Rückrufschnittstelle, die vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.|  
|[SetGCThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Legt die Rückrufschnittstelle für die Planung von Threads für nicht-Runtime-Aufgaben, die für eine Garbagecollection andernfalls blockiert würden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
