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
ms.openlocfilehash: 41c5116d23655730f3586dc656aa69c8ae817b6c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792626"
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
  
## <a name="parameters"></a>Parameters  
 `threadID`  
 in Die ID des Threads, für den der Kontext abgerufen werden soll.  
  
 `contextSize`  
 [in] Die Größe des `context`-Arrays.  
  
 `context`  
 [in, out] Ein Bytearray, das den Thread Kontext beschreibt.  
  
 Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger sollte diese Methode anstelle der Win32-`GetThreadContext`-Methode aufzurufen, da der Thread tatsächlich den Zustand "entführt" aufweisen kann, in dem der Kontext vorübergehend geändert wurde. Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet. Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.  
  
 Die zurückgegebenen Daten sind eine Kontext Struktur für die aktuelle Plattform. Ebenso wie bei der Win32-`GetThreadContext` Methode sollte der Aufrufer den `context`-Parameter initialisieren, bevor diese Methode aufgerufen wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
