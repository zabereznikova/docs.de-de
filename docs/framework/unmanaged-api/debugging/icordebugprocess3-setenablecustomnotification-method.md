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
ms.openlocfilehash: 078e5cb03848564b42e30a079101d5a61e0074bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734022"
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
 [in] `true` So aktivieren Sie benutzerdefinierte Debugger-Benachrichtigungen `false` zum Deaktivieren von Benachrichtigungen. Der Standardwert ist `false`.  
  
## <a name="remarks"></a>Hinweise  

 Wenn `fEnable` auf festgelegt ist, wird durch `true` Aufrufe der- <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> Methode ein [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) -Rückruf ausgegeben. Benachrichtigungen sind standardmäßig deaktiviert. Daher muss der Debugger alle Benachrichtigungs Typen angeben, die er kennt und verarbeiten soll. Da die [ICorDebugClass](icordebug-interface.md) -Klasse durch die Anwendungsdomäne begrenzt ist, muss der Debugger `SetEnableCustomNotification` für jede Anwendungsdomäne im Prozess aufrufen, wenn er die Benachrichtigung über den gesamten Prozess empfangen möchte.  
  
 Ab .NET Framework 4 ist die einzige unterstützte Benachrichtigung eine Thread übergreifende Abhängigkeits Benachrichtigung.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugProcess3-Schnittstelle](icordebugprocess3-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
