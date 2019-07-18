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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13371d15c8b29f9ef93cc4af87acf85029404644
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744767"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>ICorDebugRemote::DebugActiveProcessEx-Methode
Startet einen Prozess auf einem Remotecomputer unter dem Debugger.  
  
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
 [in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.  
  
 `id`  
 [in] Die ID des Prozesses, für die der Debugger wird angefügt werden.  
  
 `win32Attach`  
 [in] `true` Wenn der Debugger sollte sich so wie Win32-Debugger für den Prozess Verhalten und die nicht verwalteten Rückrufe; anderenfalls `false`.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse ein "ICorDebugProcess"-Objekt, das den Prozess darstellt, an dem der Debugger angefügt wurde.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Erfolgreich an den Prozess auf dem Remotecomputer angefügt.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Anfügen an den Prozess auf dem Remotecomputer nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemote-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
