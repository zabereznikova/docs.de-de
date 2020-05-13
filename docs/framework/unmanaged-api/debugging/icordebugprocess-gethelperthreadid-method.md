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
ms.openlocfilehash: fc4f4b56552c4db265d2ea123a84c7792ad53094
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213633"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID-Methode
Ruft die ID des Betriebssystems (OS) des internen Hilfsthreads des Debuggers ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pThreadID`  
 vorgenommen Ein Zeiger auf die Betriebssystem Thread-ID des internen Hilfsthreads des Debuggers.  
  
## <a name="remarks"></a>Hinweise  
 Beim verwalteten und nicht verwalteten Debuggen ist es für den Debugger zuständig, sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn er einen Haltepunkt erreicht, der vom Debugger platziert wird. Ein Debugger möchte möglicherweise auch diesen Thread vom Benutzer ausblenden. Wenn noch kein Hilfsthread im Prozess vorhanden ist, `GetHelperThreadID` gibt die Methode NULL in * zurück `pThreadID` .  
  
 Die Thread-ID des hilfsobreads kann nicht zwischengespeichert werden, da Sie sich im Laufe der Zeit ändern kann. Sie müssen die Thread-ID bei jedem anhalteereignis erneut Abfragen.  
  
 Die Thread-ID des Hilfsthreads des Debuggers ist bei jedem nicht verwalteten [ICorDebugManagedCallback:: foratethread](icordebugmanagedcallback-createthread-method.md) -Ereignis richtig, sodass ein Debugger die Thread-ID seines hilfsobreads ermitteln und vom Benutzer ausblenden kann. Ein Thread, der während eines nicht verwalteten Ereignisses als hilfthreadthread identifiziert wird, führt `ICorDebugManagedCallback::CreateThread` niemals verwalteten Benutzercode aus.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** "Cordebug. idl". Cordebug. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
