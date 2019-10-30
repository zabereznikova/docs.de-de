---
title: ICorDebugRemote::DebugActiveProcessEx-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: 83cc4eadca7c337c06c5fbf9f0e74306c2b9cb99
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131274"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>ICorDebugRemote::DebugActiveProcessEx-Methode
Startet einen Prozess auf einem Remote Computer unter dem Debugger.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pRemoteTarget`  
 in Zeiger auf eine [icordebugremotetarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.  
  
 `id`  
 in Die ID des Prozesses, an den der Debugger angefügt werden soll.  
  
 `win32Attach`  
 [in] `true`, wenn sich der Debugger als Win32-Debugger für den Prozessverhalten soll und die nicht verwalteten Rückrufe versendet. Andernfalls `false`.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Erfolgreich an den Prozess auf dem Remote Computer angefügt.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Das Anfügen an den Prozess auf dem Remote Computer ist nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemote-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
