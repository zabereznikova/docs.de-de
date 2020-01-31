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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792469"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification-Methode
Aktiviert und deaktiviert benutzerdefinierte Debugger-Benachrichtigungen vom angegebenen Typ.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parameters  
 `pClass`  
 in Der Typ, der benutzerdefinierte debuggerbenachrichtigungen angibt.  
  
 `fEnable`  
 [in] `true`, um benutzerdefinierte Debugger-Benachrichtigungen zu aktivieren. `false`, um Benachrichtigungen zu deaktivieren. Der Standardwert ist `false`sein.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `fEnable` auf `true`festgelegt ist, wird durch Aufrufe der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>-Methode ein [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Rückruf auslöst. Benachrichtigungen sind standardmäßig deaktiviert. Daher muss der Debugger alle Benachrichtigungs Typen angeben, die er kennt und verarbeiten soll. Da die [ICorDebugClass](icordebug-interface.md) -Klasse durch die Anwendungsdomäne begrenzt ist, muss der Debugger `SetEnableCustomNotification` für jede Anwendungsdomäne im Prozess aufrufen, wenn die Benachrichtigung über den gesamten Prozess empfangen werden soll.  
  
 Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Thread übergreifende Abhängigkeits Benachrichtigung.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess3-Schnittstelle](icordebugprocess3-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
