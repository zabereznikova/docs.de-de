---
title: ICorDebugProcess::GetHelperThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad62b267eb0c49ff8fbefeb45b523c21edc705fe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766042"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID-Methode
Ruft das Betriebssystem (OS)-Thread-ID des im Debugger das interne Hilfsmethode ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pThreadID`  
 [out] Ein Zeiger auf das Betriebssystem thread-ID des internen Hilfsthreads des Debuggers.  
  
## <a name="remarks"></a>Hinweise  
 Beim Debuggen von verwaltetem und nicht verwaltetem ist es die Verantwortung des Debuggers, um sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn ein Haltepunkt eingefügt, die vom Debugger erreicht. Ein Debugger kann auch dieser Thread vom Benutzer ausblenden möchten. Wenn kein Hilfsthread im Prozess noch vorhanden ist die `GetHelperThreadID` Methode gibt 0 (null) in *`pThreadID`.  
  
 Sie können nicht die Thread-ID des Threads Hilfsprogramm, zwischenspeichern, da es im Laufe der Zeit ändern kann. Sie müssen die Thread-ID bei jedem Stoppereignis erneut abfragen.  
  
 Die Thread-ID, Hilfsthreads des Debuggers Hilfsthreads ist für jede nicht verwaltete [ICorDebugManagedCallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) -Ereignis, sodass einen Debugger bestimmen die Thread-ID des Threads Helper und vom Benutzer zu verbergen. Ein Thread, der als ein Helperthread, während eine nicht verwaltete identifiziert wird `ICorDebugManagedCallback::CreateThread` Ereignis nie verwalteter Benutzercode ausgeführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl. CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
