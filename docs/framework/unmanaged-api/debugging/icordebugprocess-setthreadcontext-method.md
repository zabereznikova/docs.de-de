---
title: ICorDebugProcess::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e281022cd7bc9b2095fdbd3964061b811ef60e0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496962"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext-Methode
Legt den Kontext für den angegebenen Thread in diesem Prozess fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadID`  
 [in] Die ID des Threads für den Kontext festgelegt werden soll.  
  
 `contextSize`  
 [in] Die Größe des `context`-Arrays.  
  
 `context`  
 [in] Ein Array von Bytes, die Kontext des Threads zu beschreiben.  
  
 Der Kontext gibt die Architektur des Prozessors auf dem der Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger sollte diese Methode anstelle der Win32-Aufrufen `SetThreadContext` Funktion, da der Thread tatsächlich "gehackte" sind, möglicherweise in der der Kontext vorübergehend geändert wurde. Diese Methode sollte verwendet werden, nur wenn ein Thread in systemeigenem Code. Verwendung [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code. Sie müssen nicht den Kontext eines Threads während eines Out-of-Band (OOB) Debug-Ereignisses zu ändern.  
  
 Die übergebenen Daten muss ein Context-Struktur für die aktuelle Plattform.  
  
 Diese Methode kann die Laufzeit beschädigt werden, wenn nicht ordnungsgemäß verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
