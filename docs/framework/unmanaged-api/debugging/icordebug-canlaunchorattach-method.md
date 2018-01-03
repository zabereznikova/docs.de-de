---
title: ICorDebug::CanLaunchOrAttach-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CanLaunchOrAttach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62ebdb178ef7aaa16bcc163e42662e1d69f1f6f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcanlaunchorattach-method"></a>ICorDebug::CanLaunchOrAttach-Methode
Gibt ein HRESULT, das angibt, ob ein neuer Prozess gestartet oder Anhängen an den angegebenen vorhandenen Prozess innerhalb des Kontexts der aktuellen Konfiguration für Computer und die Common Language Runtime möglich ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `dwProcessId`  
 [in] Die ID der eine vorhandene Prozessressource.  
  
 `win32DebuggingEnabled`  
 [in] Übergeben Sie `true` , wenn Sie planen, mit aktiviertem Win32-Debuggen zu starten, oder übergeben Sie eine Verbindung mit der Win32-Debuggen aktiviert ist, andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn der Debugdienste bestimmen, die einen neuen Prozess starten oder Anhängen an den angegebenen Prozess ist möglich, die Informationen zur aktuellen Computer und zur Laufzeit angegeben. HRESULT Werte sind möglich:  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ist ausschließlich zu Informationszwecken. Die Schnittstelle beenden Sie nicht starten oder Anfügen an einen Prozess, unabhängig vom Wert von zurückgegebenen `CanLaunchOrAttach`.  
  
 Wenn Sie beabsichtigen, mit aktiviertem Win32-Debuggen starten oder Anhängen, mit der Win32-Debuggen aktiviert, übergeben Sie `true` für `win32DebuggingEnabled`. Zurückgegebenes HRESULT `CanLaunchOrAttach` unterscheiden, wenn Sie diese Option verwenden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
