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
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975965"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack-Methode
Ruft einen Enumerator für die in einem Ausnahme Objekt eingebettete-Aufzählung ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 ppcallstackaufumum  
 vorgenommen Ein Zeiger auf die Adresse eines [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Schnittstellen Objekts, bei dem es sich um einen Stapel Verfolgungs Enumerator für ein verwaltetes Ausnahme Objekt handelt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn keine Aufruf Listen Informationen verfügbar sind, gibt die Methode `S_OK`zurück, und [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) ist ein gültiger Enumerator mit einer Länge von 0. Wenn die Methode keine Stapel Überwachungsinformationen abrufen kann, ist `E_FAIL` der Rückgabewert, und es wird kein Enumerator zurückgegeben.  
  
 Das [icordebugexceptionobjectcallstackenum](icordebugexceptionobjectcallstackenum-interface.md) -Objekt ist verantwortlich für das Decodieren der Stapel Verfolgungs `_stackTrace` Daten aus dem-Feld des Ausnahme Objekts.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugExceptionObjectValue-Schnittstelle](icordebugexceptionobjectvalue-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
