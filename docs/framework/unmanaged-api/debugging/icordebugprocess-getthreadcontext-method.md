---
title: ICorDebugProcess::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c137a10d5da94d04509385fc97d71535d33fae93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758740"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext-Methode
Ruft den Kontext für den angegebenen Thread in diesem Prozess ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des Threads, für den zum Abrufen des Kontexts.  
  
 `contextSize`  
 [in] Die Größe des `context`-Arrays.  
  
 `context`  
 [in, out] Ein Array von Bytes, die Kontext des Threads zu beschreiben.  
  
 Der Kontext gibt die Architektur des Prozessors auf dem der Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger sollte diese Methode anstelle der Win32-Aufrufen `GetThreadContext` -Methode, da der Thread tatsächlich "gehackte" sind, möglicherweise in der der Kontext vorübergehend geändert wurde. Diese Methode sollte verwendet werden, nur wenn ein Thread in systemeigenem Code. Verwendung [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code.  
  
 Die zurückgegebenen Daten ist ein Context-Struktur für die aktuelle Plattform. Genau wie bei der Win32 `GetThreadContext` -Methode, die der Aufrufer sollte Initialisieren der `context` -Parameter vor dem Aufrufen dieser Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
