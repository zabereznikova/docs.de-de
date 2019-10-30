---
title: ICorDebugProcess3::SetEnableCustomNotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: ec60274648315c4fa38f3832d8d39c1a269956b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129703"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification-Methode
Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parameter  
 `pClass`  
 in Der Typ, der benutzerdefinierte debuggerbenachrichtigungen angibt.  
  
 `fEnable`  
 [in] `true`, um benutzerdefinierte Debugger-Benachrichtigungen zu aktivieren. `false`, um Benachrichtigungen zu deaktivieren. Der Standardwert ist `false`sein.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `fEnable` auf `true`festgelegt ist, wird durch Aufrufe der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>-Methode ein [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) -Rückruf auslöst. Benachrichtigungen sind standardmäßig deaktiviert. Daher muss der Debugger alle Benachrichtigungs Typen angeben, die er kennt und verarbeiten soll. Da die [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Klasse durch die Anwendungsdomäne begrenzt ist, muss der Debugger `SetEnableCustomNotification` für jede Anwendungsdomäne im Prozess aufrufen, wenn die Benachrichtigung über den gesamten Prozess empfangen werden soll.  
  
 Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Thread übergreifende Abhängigkeits Benachrichtigung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
