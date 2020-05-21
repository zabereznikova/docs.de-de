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
ms.openlocfilehash: 3b8c9421dea4040a9f183b886f1ad8575cace780
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762427"
---
# <a name="icorconfiguration-interface"></a>ICorConfiguration-Schnittstelle
Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[AddDebuggerSpecialThread-Methode](icorconfiguration-adddebuggerspecialthread-method.md)|Gibt den Debugdiensten an, dass ein bestimmter Thread weiter ausgeführt werden darf, während der Debugger eine Anwendung während verwalteter oder nicht verwalteter debuggingszenarien beendet hat.|  
|[SetDebuggerThreadControl-Methode](icorconfiguration-setdebuggerthreadcontrol-method.md)|Legt die Rückruf Schnittstelle fest, die von den Debugdiensten aufgerufen wird, wenn CLR-Threads blockiert und für das Debuggen blockiert werden.|  
|[SetGCHostControl-Methode](icorconfiguration-setgchostcontrol-method.md)|Legt die Rückruf Schnittstelle fest, die vom Garbage Collector verwendet werden soll, um den Host zum Ändern der Grenzwerte für den virtuellen Arbeitsspeicher anzufordern.|  
|[SetGCThreadControl-Methode](icorconfiguration-setgcthreadcontrol-method.md)|Legt die Rückruf Schnittstelle für das Planen von Threads für nicht-Lauf Zeit Aufgaben fest, die andernfalls für eine Garbage Collection blockiert werden.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Hostingschnittstellen](hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](corruntimehost-coclass.md)
