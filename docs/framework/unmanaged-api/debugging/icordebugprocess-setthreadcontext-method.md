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
ms.openlocfilehash: 5b4052485a6d420eb83578d135ce51f8a918aab0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724519"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext-Methode

Legt den Kontext für den angegebenen Thread in diesem Prozess fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `threadID`  
 in Die ID des Threads, für den der Kontext festgelegt werden soll.  
  
 `contextSize`  
 [in] Die Größe des `context`-Arrays.  
  
 `context`  
 in Ein Bytearray, das den Thread Kontext beschreibt.  
  
 Der Kontext gibt die Architektur des Prozessors an, auf dem der Thread ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  

 Der Debugger sollte diese Methode anstelle der Win32-Funktion aufzurufen `SetThreadContext` , da der Thread tatsächlich den Zustand "entführt" aufweisen kann, in dem der Kontext vorübergehend geändert wurde. Diese Methode sollte nur verwendet werden, wenn sich ein Thread in nativem Code befindet. Verwenden Sie [ICorDebugRegisterSet](icordebugregisterset-interface.md) für Threads in verwaltetem Code. Sie sollten den Kontext eines Threads nie während eines OOB-Debugereignisses (Out-of-Band) ändern.  
  
 Die Daten, die übermittelt werden, müssen eine Kontext Struktur für die aktuelle Plattform sein.  
  
 Diese Methode kann die Laufzeit beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
