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
ms.openlocfilehash: d0dc301c67d09ebb15bf47cef15e642fb7c78fb9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792604"
---
# <a name="icordebugprocessgethelperthreadid-method"></a>ICorDebugProcess::GetHelperThreadID-Methode
Ruft die ID des Betriebssystems (OS) des internen Hilfsthreads des Debuggers ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pThreadID`  
 vorgenommen Ein Zeiger auf die Betriebssystem Thread-ID des internen Hilfsthreads des Debuggers.  
  
## <a name="remarks"></a>Hinweise  
 Beim verwalteten und nicht verwalteten Debuggen ist es für den Debugger zuständig, sicherzustellen, dass der Thread mit der angegebenen ID weiterhin ausgeführt wird, wenn er einen Haltepunkt erreicht, der vom Debugger platziert wird. Ein Debugger möchte möglicherweise auch diesen Thread vom Benutzer ausblenden. Wenn noch kein Hilfsthread im Prozess vorhanden ist, gibt die `GetHelperThreadID`-Methode in *`pThreadID`NULL zurück.  
  
 Die Thread-ID des hilfsobreads kann nicht zwischengespeichert werden, da Sie sich im Laufe der Zeit ändern kann. Sie müssen die Thread-ID bei jedem anhalteereignis erneut Abfragen.  
  
 Die Thread-ID des Hilfsthreads des Debuggers ist bei jedem nicht verwalteten [ICorDebugManagedCallback:: foratethread](icordebugmanagedcallback-createthread-method.md) -Ereignis richtig, sodass ein Debugger die Thread-ID seines hilfsobreads ermitteln und vom Benutzer ausblenden kann. Ein Thread, der während eines nicht verwalteten `ICorDebugManagedCallback::CreateThread` Ereignisses als Hilfsthread identifiziert wird, führt niemals verwalteten Benutzercode aus.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** "Cordebug. idl". CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
