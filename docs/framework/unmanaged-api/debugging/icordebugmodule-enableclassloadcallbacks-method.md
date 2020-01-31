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
ms.openlocfilehash: d552b694787b5d9f0d5adc399eda6f75df93c385
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793027"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>ICorDebugModule::EnableClassLoadCallbacks-Methode
Steuert, ob die Rückrufe [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) und [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) für dieses Modul aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `bClassLoadCallbacks`  
 in Legen Sie diesen Wert auf `true` fest, damit der Common Language Runtime (CLR) die Methoden `ICorDebugManagedCallback::LoadClass` und `ICorDebugManagedCallback::UnloadClass` aufruft, wenn die zugehörigen Ereignisse eintreten.  
  
 Der Standardwert ist `false` für nicht dynamische Module. Der Wert ist für dynamische Module immer `true` und kann nicht geändert werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugManagedCallback::LoadClass`-und `ICorDebugManagedCallback::UnloadClass` Rückrufe sind immer für dynamische Module aktiviert und können nicht deaktiviert werden.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
