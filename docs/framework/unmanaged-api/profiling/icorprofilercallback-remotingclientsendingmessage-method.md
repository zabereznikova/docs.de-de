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
ms.openlocfilehash: 820a37c8ca16f4962bf1d72b1f0f404cffd92a1a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499960"
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
 in Ein Wert, der dem Wert entspricht, der in [ICorProfilerCallback:: RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) unter den folgenden Bedingungen bereitgestellt wird:  
  
- Remoting-GUID-Cookies sind aktiv.  
  
- Der Kanal hat die Nachricht erfolgreich übertragen.  
  
- GUID-Cookies sind im serverseitigen Prozess aktiv.  
  
 Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.  
  
 `fIsAsync`  
 in Ein-Wert, `true` der ist, wenn der-Aufrufwert asynchron ist, andernfalls `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
