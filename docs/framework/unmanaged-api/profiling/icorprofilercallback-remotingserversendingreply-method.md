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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 98563c175f12ad1ff25e1f578270fe1099175487
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453775"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a>ICorProfilerCallback::RemotingServerSendingReply-Methode
Benachrichtigt den Profiler, dass der Prozess die Verarbeitung einer Remotemethode Aufruf-Anforderung abgeschlossen und die Antwort über einen Kanal übertragen wird hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCookie`  
 [in] Ein Zeiger auf eine GUID, die mit dem Wert im bereitgestellten entsprechen wird [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) unter diesen Bedingungen:  
  
-   Remoting-GUID-Cookies sind aktiv.  
  
-   Der Kanal kann erfolgreich sendet die Nachricht.  
  
-   GUID-Cookies werden auf der Clientseite Prozess aktiv.  
  
 Dies ermöglicht eine einfache Verbindung Remoteaufrufe und die Erstellung einer logischen Aufrufliste.  
  
 `fIsAsync`  
 [in] Ein Wert, `true` Wenn der Aufruf asynchron, andernfalls ist `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
