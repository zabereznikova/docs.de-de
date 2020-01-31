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
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791971"
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
  
## <a name="parameters"></a>Parameters  
 `pRemoteTarget`  
 [in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md). Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.  
  
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
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemote-Schnittstelle](icordebugremote-interface.md)
- [ICorDebug-Schnittstelle](icordebug-interface.md)

- [Debuggen von Schnittstellen](debugging-interfaces.md)
