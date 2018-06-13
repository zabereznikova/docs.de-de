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
ms.openlocfilehash: 950790b246094c71900a5fb4da7d92be7d24aba2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421615"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks-Methode
Steuert, ob die [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) Rückrufe für dieses Modul aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bClassLoadCallbacks`  
 [in] Legen Sie diesen Wert auf `true` So aktivieren Sie die common Language Runtime (CLR) aufrufen, die `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Methoden, wenn die zugeordneten Ereignisse auftreten.  
  
 Der Standardwert ist `false` für nicht-dynamische Module. Der Wert ist immer `true` bei dynamischen Modulen kann nicht geändert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` Rückrufe werden für dynamische Module immer aktiviert und kann nicht deaktiviert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
    
 
