---
title: ICorProfilerCallback::RemotingClientSendingMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4729a8d3ac2c6f7ec51a032a07ebfd1c2838cb9a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782907"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a>ICorProfilerCallback::RemotingClientSendingMessage-Methode
Benachrichtigt den Profiler, dass der Client eine Anforderung an den Server sendet.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCookie`  
 [in] Ein Wert, mit dem Wert im bereitgestellten [ICorProfilerCallback:: RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) unter diesen Bedingungen:  
  
- Remoting-GUID-Cookies sind aktiv.  
  
- Der Kanal ist erfolgreich, bei der Übermittlung der Nachricht.  
  
- GUID-Cookies werden auf den serverseitigen Prozess aktiv.  
  
 Dies ermöglicht die einfache Kopplung der Remotingaufrufe und die Erstellung einer logischen Aufrufliste.  
  
 `fIsAsync`  
 [in] Ein Wert, `true` , wenn der Aufruf asynchron; andernfalls ist `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
