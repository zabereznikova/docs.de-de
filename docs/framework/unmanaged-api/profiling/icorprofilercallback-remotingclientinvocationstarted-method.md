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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dcb79c4130f6bd163cb807ff92b95db8360a185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461967"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a>ICorProfilerCallback::RemotingClientInvocationStarted-Methode
Benachrichtigt den Profiler, ein Remotingaufruf gestartet hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieses Ereignis ist für synchrone und asynchrone Aufrufe identisch.  
  
 Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread auftreten:  
  
-   `RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:  
  
-   Ausführung einer Remotingfunktion wird vom Profiler-API nicht widergespiegelt, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen wurden. Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; der Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.  
  
-   Der Profiler empfängt keine genaue Benachrichtigungen für asynchrone Remoting-Ereignisse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
