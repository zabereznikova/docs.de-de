---
title: ICorProfilerCallback::RemotingServerReceivingMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1874b5bea465eb31bcaad2d912b90d35cfc711b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454101"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage-Methode
Benachrichtigt den Profiler, dass der Prozess eine remote-Methode aufrufen oder die Aktivierung der Anforderung empfangen hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCookie`  
 [in] Ein Wert, der entsprechen, wird mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) unter diesen Bedingungen:  
  
-   Remoting-GUID-Cookies sind aktiv.  
  
-   Der Kanal kann erfolgreich sendet die Nachricht.  
  
-   GUID-Cookies werden auf der Clientseite Prozess aktiv.  
  
 Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.  
  
 `fIsAsync`  
 [in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die nachrichtenanforderung asynchron ist, kann die Anforderung von jedem beliebigen Thread bedient werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
