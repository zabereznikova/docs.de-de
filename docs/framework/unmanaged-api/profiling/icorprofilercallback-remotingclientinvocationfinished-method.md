---
title: ICorProfilerCallback::RemotingClientInvocationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c3f7c30518184be70c85ff096915738b1633a01
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64603229"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished-Methode
Benachrichtigt den Profiler an, dass ein Remoteaufrufs bis zum Abschluss, auf dem Client ausgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Remotingaufruf für synchrone war, hat es auch auf dem Server bis zum Abschluss ausgeführt. Wenn der Remotingaufruf für asynchrone war, ggf. eine Antwort immer noch erwartet werden, wenn der Aufruf verarbeitet wird. Wenn eine Antwort erwartet wird, wird er als Aufruf auftreten [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und einen zusätzlichen Aufruf `RemotingClientInvocationFinished` an die sekundären erforderliche Verarbeitung eines asynchronen Aufrufs.  
  
 Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:  
  
- `RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:  
  
- Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden. Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.  
  
- Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
