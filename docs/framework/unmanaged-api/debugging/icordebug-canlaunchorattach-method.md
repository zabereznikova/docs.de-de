---
title: ICorDebug::CanLaunchOrAttach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
ms.openlocfilehash: 195c7e1e7c61fd6ac8a21226b52e3782d2f7e421
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723492"
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach-Methode

Gibt ein HRESULT zurück, das angibt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `dwProcessId`  
 in Die ID eines vorhandenen Prozesses.  
  
 `win32DebuggingEnabled`  
 in Übergeben `true` Sie, wenn Sie planen, mit aktiviertem Win32-Debugging zu starten oder mit aktiviertem Win32-Debugging anzufügen. Andernfalls übergeben Sie `false` .  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Debugdienste bestimmen, dass das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess möglich ist, wenn die Informationen über den aktuellen Computer und die Laufzeitkonfiguration angegeben werden. Mögliche HRESULT-Werte sind:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode dient nur zu Informationszwecken. Die-Schnittstelle hindert Sie nicht daran, einen Prozess zu starten oder anzufügen, unabhängig von dem Wert, der von zurückgegeben wird `CanLaunchOrAttach` .  
  
 Wenn Sie planen, mit aktiviertem Win32-Debugging oder Attach mit aktiviertem Win32-Debugging zu starten, geben Sie `true` für an `win32DebuggingEnabled` . Das von zurückgegebene HRESULT `CanLaunchOrAttach` unterscheidet sich möglicherweise, wenn Sie diese Option verwenden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebug-Schnittstelle](icordebug-interface.md)
