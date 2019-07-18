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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec9b4867ad19f25e35ca31c007c0d238b949abab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762222"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks-Methode
Steuerelemente, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `bClassLoadCallbacks`  
 [in] Legen Sie diesen Wert auf `true` So aktivieren Sie die common Language Runtime (CLR) zum Aufrufen der `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Methoden ein, wenn die zugeordneten Ereignisse auftreten.  
  
 Der Standardwert ist `false` für nicht dynamische Module. Der Wert ist immer `true` bei dynamischen Modulen kann nicht geändert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Rückrufe werden für dynamische Module immer aktiviert und kann nicht deaktiviert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
