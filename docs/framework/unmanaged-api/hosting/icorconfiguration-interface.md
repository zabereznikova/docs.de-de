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
ms.openlocfilehash: 80bb68486e555d6c96cf8ee56ed6d60e41c7c5c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127800"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration-Schnittstelle
Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[AddDebuggerSpecialThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-adddebuggerspecialthread-method.md)|Gibt den Debugdiensten an, dass ein bestimmter Thread weiter ausgeführt werden darf, während der Debugger eine Anwendung während verwalteter oder nicht verwalteter debuggingszenarien beendet hat.|  
|[SetDebuggerThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setdebuggerthreadcontrol-method.md)|Legt die Rückruf Schnittstelle fest, die von den Debugdiensten aufgerufen wird, wenn CLR-Threads blockiert und für das Debuggen blockiert werden.|  
|[SetGCHostControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgchostcontrol-method.md)|Legt die Rückruf Schnittstelle fest, die vom Garbage Collector verwendet werden soll, um den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.|  
|[SetGCThreadControl-Methode](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-setgcthreadcontrol-method.md)|Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
