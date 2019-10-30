---
title: ICorDebugModule::EnableClassLoadCallbacks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139221"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks-Methode
Steuert, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bClassLoadCallbacks`  
 in Legen Sie diesen Wert auf `true` fest, damit der Common Language Runtime (CLR) die Methoden `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` aufruft, wenn die zugehörigen Ereignisse eintreten.  
  
 Der Standardwert ist `false` für nicht dynamische Module. Der Wert ist für dynamische Module immer `true` und kann nicht geändert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugManagedCallback::LoadClass`-und `ICorDebugManagedCallback::UnloadClass` Rückrufe sind immer für dynamische Module aktiviert und können nicht deaktiviert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
