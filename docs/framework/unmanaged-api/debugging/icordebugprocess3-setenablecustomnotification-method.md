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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58e50a0c02f15590e5bbbcadaabeaa7e3886b74b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736818"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification-Methode
Aktiviert und deaktiviert benutzerdefinierte Debuggerbenachrichtigungen des angegebenen Typs.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parameter  
 `pClass`  
 [in] Der Typ, der angibt, benutzerdefinierte Debuggerbenachrichtigungen.  
  
 `fEnable`  
 [in] `true` benutzerdefinierte Debuggerbenachrichtigungen; aktivieren `false` um Benachrichtigungen zu deaktivieren. Der Standardwert ist `false`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `fEnable` nastaven NA hodnotu `true`, Aufrufe von der <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode Trigger ein [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) Rückruf. Benachrichtigungen sind standardmäßig deaktiviert. aus diesem Grund muss der Debugger alle Benachrichtigungstypen angeben, die es kennt und behandeln möchte. Da die [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Klasse bezieht sich durch die Anwendungsdomäne, die der Debugger muss Aufrufen `SetEnableCustomNotification` für jede Anwendungsdomäne, in den Prozess, wenn sie die Benachrichtigung für den gesamten Prozess empfangen möchte.  
  
 Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Benachrichtigung threadübergreifenden Abhängigkeit.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugProcess3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
