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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cf0065f1ed12ad3a37819b0a15d734a2b51ff5b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125605"
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach-Methode
Gibt ein HRESULT, der angibt, ob ein neuer Prozess gestartet oder an den angegebenen vorhandenen Prozess anfügen innerhalb des Kontexts der aktuellen Computer und -Runtime-Konfiguration möglich ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwProcessId`  
 [in] Die ID eines vorhandenen Prozesses.  
  
 `win32DebuggingEnabled`  
 [in] Übergeben Sie `true` , wenn Sie, starten Sie mit der Win32-Debuggen aktiviert möchten ist, oder übergeben Sie eine Verbindung mit der Win32-Debuggen aktiviert ist, andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Debuggen von Diensten, die ein neuer Prozess gestartet oder das Anfügen an den Prozess ermitteln kann, erhält die Informationen über die aktuelle Konfiguration für Computer und der Common Language Runtime. HRESULT Werte sind möglich:  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode dient ausschließlich zu Informationszwecken. Die Schnittstelle beenden Sie nicht starten oder Anfügen an einen Prozess, unabhängig vom Wert von zurückgegebenen `CanLaunchOrAttach`.  
  
 Wenn Sie planen, starten Sie mit der Win32-Debuggen aktiviert oder Verbindung mit Win32-Debuggen aktiviert, übergeben Sie `true` für `win32DebuggingEnabled`. Das HRESULT zurückgegeben wird, indem `CanLaunchOrAttach` können abweichen, wenn Sie diese Option verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
