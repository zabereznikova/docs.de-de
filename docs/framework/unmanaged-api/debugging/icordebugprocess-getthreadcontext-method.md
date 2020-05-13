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
ms.openlocfilehash: 2bdbf373144e2fb49074cfd035e7b0ffe3c8c291
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212886"
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
 in Die ID des Threads, für den der Kontext abgerufen werden soll.  
  
 `contextSize`  
 [in] Die Größe des `context`-Arrays.  
  
 `context`  
 [in, out] Ein Bytearray, das den Thread Kontext beschreibt.  
  
 Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Der Debugger sollte diese Methode anstelle der Win32-Methode anstelle der Win32- `GetThreadContext` Methode abrufen, da sich der Thread möglicherweise im Zustand "entführt" befindet, in dem der Kontext vorübergehend geändert wurde. Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet. Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code.  
  
 Die zurückgegebenen Daten sind eine Kontext Struktur für die aktuelle Plattform. Genau wie bei der Win32- `GetThreadContext` Methode sollte der Aufrufer den- `context` Parameter vor dem Aufrufen dieser Methode initialisieren.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
