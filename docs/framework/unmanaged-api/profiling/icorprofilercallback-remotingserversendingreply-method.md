---
title: ICorProfilerCallback::RemotingServerSendingReply-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
ms.openlocfilehash: 1d876644ae35d13a481b01d9e0e5ff0d0764ca18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713950"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply-Methode

Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remote Methodenaufruf Anforderung abgeschlossen hat und die Antwort über einen Kanal überträgt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a>Parameter  

 `pCookie`  
 in Ein Zeiger auf eine GUID, die dem Wert entspricht, der in [ICorProfilerCallback:: RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) unter diesen Bedingungen bereitgestellt wird:  
  
- Remoting-GUID-Cookies sind aktiv.  
  
- Der Kanal hat die Nachricht erfolgreich übertragen.  
  
- GUID-Cookies sind im Client seitigen Prozess aktiv.  
  
 Dies ermöglicht eine einfache Kopplung von Remote aufrufen und die Erstellung einer logischen Aufruf Stapel.  
  
 `fIsAsync`  
 in Ein-Wert, `true` der ist, wenn der-Aufrufwert asynchron ist, andernfalls `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorProfilerCallback-Schnittstelle](icorprofilercallback-interface.md)
