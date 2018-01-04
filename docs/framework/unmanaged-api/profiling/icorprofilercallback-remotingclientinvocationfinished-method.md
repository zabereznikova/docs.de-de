---
title: ICorProfilerCallback::RemotingClientInvocationFinished-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f0ae2be95b559074ca9dacde493a98008608b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished-Methode
Benachrichtigt den Profiler, dass ein Remotingaufruf auf dem Client bis zum Abschluss ausgeführt wurde.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 War der Remotingaufruf synchron, hat es auch auf dem Server bis zum Abschluss ausgeführt. War der Remoteaufruf asynchrone, möglicherweise eine Antwort noch erwartet werden, wenn der Aufruf verarbeitet wird. Wenn eine Antwort erwartet wird, wird er als Aufruf auftreten [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und ein zusätzlicher Aufruf `RemotingClientInvocationFinished` an, dass die erforderliche zweite Verarbeitung eines asynchronen Aufrufs.  
  
 Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread auftreten:  
  
-   `RemotingClientInvocationStarted`und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
-   [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
-   [ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:  
  
-   Ausführung einer Remotingfunktion wird vom Profiler-API nicht widergespiegelt, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen wurden. Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; der Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.  
  
-   Der Profiler empfängt keine genaue Benachrichtigungen für asynchrone Remoting-Ereignisse.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
