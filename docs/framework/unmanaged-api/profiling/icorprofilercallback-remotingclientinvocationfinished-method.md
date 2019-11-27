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
ms.openlocfilehash: c9a750b941b29047206c98410d4b4673d1101a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445832"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished-Methode
Benachrichtigt den Profiler, dass ein Remotingaufrufe auf dem Client ausgeführt werden muss.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn der remotingbefehl synchron war, kann er auch auf dem Server abgeschlossen werden. Wenn der Remotingaufrufe asynchron war, wird möglicherweise dennoch eine Antwort erwartet, wenn der-Befehl verarbeitet wird. Wenn eine Antwort erwartet wird, wird Sie als Aufrufen von [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und einem zusätzlichen `RemotingClientInvocationFinished` aufgerufen, um die erforderliche sekundäre Verarbeitung eines asynchronen Aufrufs anzugeben.  
  
 Jedes der folgenden paar Rückrufe findet im gleichen Thread statt:  
  
- `RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: remotingclientinvocationabgeschlossene](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: remotingserverinvocationzurück gegeben](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Beachten Sie die folgenden Probleme bei den Remoting-Rückrufen:  
  
- Die Ausführung einer Remoting-Funktion wird von der Profiler-API nicht reflektiert, sodass Benachrichtigungen für Funktionen, die vom Client aufgerufen und auf dem Server ausgeführt werden, nicht ordnungsgemäß empfangen werden. Der tatsächliche Aufruf erfolgt über ein Proxy Objekt. für den Profiler wird angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nie verwendet werden.  
  
- Der Profiler empfängt keine genauen Benachrichtigungen für asynchrone Remoting-Ereignisse.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
