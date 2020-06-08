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
ms.openlocfilehash: 157e6bc6cb9603fa9558ad6d39f0b086849fc7b0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499895"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage-Methode
Benachrichtigt den Profiler, dass der Prozess eine Remote Methodenaufruf-oder Aktivierungs Anforderung empfangen hat.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parameter  
 `pCookie`  
 in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) unter den folgenden Bedingungen bereitgestellt wird:  
  
- Remoting-GUID-Cookies sind aktiv.  
  
- Der Kanal hat die Nachricht erfolgreich übertragen.  
  
- GUID-Cookies sind im Client seitigen Prozess aktiv.  
  
 Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.  
  
 `fIsAsync`  
 in Ein-Wert, `true` der ist, wenn der-Aufrufwert asynchron ist, andernfalls `false` .  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die Nachrichten Anforderung asynchron ist, kann die Anforderung von einem beliebigen Thread gewartet werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
