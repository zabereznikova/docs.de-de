---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 57eb284bfe39ce92b2d6c03a2aeb4ae84d6aba91
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788664"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode
Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Parameters  
 ppCallStackEnum  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Stapel Verfolgungs Enumerator für ein verwaltetes Ausnahme Objekt handelt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn keine Aufruf Listen Informationen verfügbar sind, gibt die Methode `S_OK`und [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) einen gültigen Enumerator mit einer Länge von 0 (null) zurück. Wenn die Methode keine Stapel Überwachungsinformationen abrufen kann, ist der Rückgabewert `E_FAIL`, und es wird kein Enumerator zurückgegeben.  
  
 Das [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für das Decodieren der Stapel Verfolgungs Daten aus dem `_stackTrace`-Feld des Ausnahme Objekts.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugExceptionObjectValue-Schnittstelle](icordebugexceptionobjectvalue-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
