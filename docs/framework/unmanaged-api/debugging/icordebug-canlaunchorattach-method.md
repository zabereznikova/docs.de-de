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
ms.openlocfilehash: 354df02b27e87550ba602fe102352455c227441b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859686"
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
 in Übergeben Sie `true` , wenn Sie planen, mit aktiviertem Win32-Debugging zu starten, oder wenn Sie das Win32-Debugging aktiviert haben. Andernfalls übergeben `false`Sie.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Debugdienste bestimmen, dass das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess möglich ist, wenn die Informationen über den aktuellen Computer und die Laufzeitkonfiguration angegeben werden. Mögliche HRESULT-Werte sind:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode dient nur zu Informationszwecken. Die-Schnittstelle hindert Sie nicht daran, einen Prozess zu starten oder anzufügen, unabhängig von dem `CanLaunchOrAttach`Wert, der von zurückgegeben wird.  
  
 Wenn Sie planen, mit aktiviertem Win32-Debugging oder Attach mit aktiviertem Win32- `true` Debugging `win32DebuggingEnabled`zu starten, geben Sie für an. Das von `CanLaunchOrAttach` zurückgegebene HRESULT unterscheidet sich möglicherweise, wenn Sie diese Option verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorDebug-Schnittstelle](icordebug-interface.md)
