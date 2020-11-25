---
title: ICorProfilerCallback::RemotingClientInvocationStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
ms.openlocfilehash: 22b9970556dd9d8b5070f38a7712462aa5a4aae2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720164"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a>ICorProfilerCallback::RemotingClientInvocationStarted-Methode

Benachrichtigt den Profiler, dass ein remotingbefehl gestartet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a>Hinweise  

 Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.  
  
 Jedes der folgenden paar Rückrufe findet im gleichen Thread statt:  
  
- `RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: remotingclientinvocationabgeschlossene](icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: remotingserverinvocationzurück gegeben](icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)  
  
 Beachten Sie die folgenden Probleme bei den Remoting-Rückrufen:  
  
- Die Ausführung einer Remoting-Funktion wird von der Profiler-API nicht reflektiert, sodass Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen werden. Der tatsächliche Aufruf erfolgt über ein Proxy Objekt. für den Profiler wird angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.  
  
- Der Profiler empfängt keine genauen Benachrichtigungen für asynchrone Remoting-Ereignisse.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
